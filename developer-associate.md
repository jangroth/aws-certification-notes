[toc_start]::
<a name="top"></a>
---
* [AWS Developer Associate](#1)
* [AWS Fundamentals](#2)
  * [Global infrastructure](#2_1)
  * [Storage overview](#2_2)
  * [Security Concepts](#2_3)
* [Services](#3)
  * [IAM](#3_1)
  * [Secure Token Service (STS)](#3_2)
  * [S3](#3_3)
  * [Dynamo DB](#3_4)
  * [Elastic Compute Cloud (EC2)](#3_5)
  * [Elastic Load Balancer (ELB)](#3_6)
  * [SNS](#3_7)
  * [SQS](#3_8)
  * [Cloudformation](#3_9)
  * [Elastic Beanstalk (EB)](#3_10)
  * [Simple Workflow Service (SWF)](#3_11)
  * [Virtual Private Cloud (VPC)](#3_12)
  * [Relational Database Service (RDS)](#3_13)
* [Etc](#4)
---
[toc_end]::
<a name="1"></a>
# [↖](#top)[↑](#)[↓](#2) AWS Developer Associate
> 6/2017 - 8/2017

<a name="2"></a>
# [↖](#top)[↑](#1)[↓](#2_1) AWS Fundamentals

<a name="2_1"></a>
## [↖](#top)[↑](#2)[↓](#2_2) Global infrastructure
* **Region** - grouping of data centers
* **AZ** - indidvidual data center in a region. Redundancy throughout AZs in one region
* **Edge Location** - location to deliver cached data fast -> Use *Cloudfront* CDN to cache data
close to where it's being used

<a name="2_2"></a>
## [↖](#top)[↑](#2_1)[↓](#2_2_1) Storage overview
<a name="2_2_1"></a>
### Instance store volumes
* **Temporary block storage**
* Physically attached to the host computer of the instance
* Useful for often-changing data like caches & buffers
* *Data is lost* when EC2 instance stops or terminates (*ephemeral* data)
<a name="2_2_2"></a>
### Elastic Block Storage (EBS)
* **Permanent block storage**, independent to instance
* Attachable to running EC2 instances (same AZ)
* Only accessible by a *single instance*
* Can take snapshots from
* Can be encrypted
* Stores redundantly in single AZ
* Different volume options:
	* General purpose SSD
	* Provisioned IOPS
	* Magnetic volumes
<a name="2_2_3"></a>
### Elastic File System (EFS)
* **Scalable file storage** for use with *Amazon EC2 instances*
* Elastic storage capacity, growing and shrinking as files are added or removed
* *Multiple EC2 instances* from *multiple AZs* can access an EFS file system at the same time
* Stores redundantly in multiple AZs
<a name="2_2_4"></a>
### Amazon Glacier
* Low cost, very slow retrieval
* Can be intergrated with S3 lifecycle policy
<a name="2_2_5"></a>
### Database Storage
* *DynamoDB*
* *RDS*
* DBs on EC2 instances
* *AWS Redshift* (data warehouse service)
<a name="2_2_6"></a>
### In-memory caching
* *ElastiCache* (Memcached and Redis)
* Software on EC2 instances
<a name="2_2_7"></a>
### Storage gateway
* Integrate existing *on-premises storage* infrastructure and data with the AWS Cloud

<a name="2_3"></a>
## [↖](#top)[↑](#2_2_7)[↓](#3) Security Concepts
* **Shared responsibility** environment
* AWS is responsible for:
	* Server / Host level and below
	* Physical environment security
	* Hardware decommissioning
	* Traffic security (Networks, ACLs, SSL, DDOS-protection)
	* EC2 hypervisor isolation
* User is responsible for:
	* IAM
	* MFA
	* Password/key-rotation
	* Access advisor (shows used permissions)
	* Trusted advisor (validates best practices)
	* Security groups
	* ACL (resource based policy)
	* VPC

<a name="3"></a>
# [↖](#top)[↑](#2_3)[↓](#3_1) Services
<a name="3_1"></a>
## [↖](#top)[↑](#3)[↓](#3_1_1) IAM
IAM is a global service that helps to securely control access to AWS resources.

* **Users** hold credentials
* **Groups** hold users, typically only provides permission to assume a role
* **Roles** hold policies.
	* Can have **trust relationships** with trusted entities that can *assume* this role
* **Policies** can be attached to users, groups or roles (preferred)
* An **instance profile** is a container for an IAM role that you can use to pass role information to an
	EC2 instance when the instance starts.
* Users and / or services assume roles

<a name="3_1_1"></a>
### Policies
* Any actions on resources that are not explicitly allowed are **denied by default**
* Structure
	* **E** - `effect` (*allow* / *deny*)
		* What the effect will be when the user requests the specific action
	* **P** - `prinicpal` (*ARN*)
		* The account or user who is allowed access to the actions and resources in the statement
		* IAM policies do not have a principal (because they are attached to users, groups or roles)
	* **A** - `action` or `notaction`
		* Describes the specific action or actions that will be allowed or denied
	* **R** - `resource` or `notresource`
		* Specifies the object or objects that the statement covers
	* **C** - `condition`
		* Specifies conditions for when a policy is in effect
* Can use **policy variables**
	* `aws:currentTime`, `aws:userid`, ...

```
	{
		"Version": "2012-10-17",
		"Statement": [
			{
				"Effect": "Allow",
				"Action": "s3:ListAllMyBuckets",
				"Resource": "arn:aws:s3:::*"
			},
			{
				"Effect": "Allow",
				"Action": [
						"s3:ListBucket",
						"s3:GetBucketLocation"
				],
				"Resource": "arn:aws:s3:::productionapp"
			},
			{
				"Effect": "Allow",
				"Action": [
					"s3:GetObject",
					"s3:PutObject",
					"s3:DeleteObject"
				],
				"Resource": "arn:aws:s3:::productionapp/*"
			}
		]
	}
```
<a name="3_1_1_1"></a>
#### IAM Policies
* Managed policies (the new way)
	* Can be attached to multiple users, groups and roles
	* AWS managed policies
		* Updated by AWS if new API come out
* Inline policies (the old way)

<a name="3_1_2"></a>
### Limits
.|.
-|-
Groups per account|100
Instance profiles|100
Roles|500
Server certificates|20
Users|5000

<a name="3_2"></a>
## [↖](#top)[↑](#3_1_2)[↓](#3_2_1) Secure Token Service (STS)
* Allows to grant **temporary access** to authenticated users
	* IAM users
	* Web-based identity providers (google, facebook, ...)
	* Organization's existing identity system
* Returns **temporary credentials** that expire after some time:
	* Access key
	* Session token

<a name="3_2_1"></a>
### Terms
* **Federation**
	* Trust relationship between identity provider and AWS
* **Identity broker**
	* Broker in charge of mapping user to the right set of credentials
* **Identity store**
	* Eg Google or Facebook
* **Identities**
	* Users

<a name="3_2_2"></a>
### Scenarios
* Temporary credentials with EC2
	* Assign IAM role to instance
	* Get temp credentials from *instance metadata*
* Temporary credentials with SDK
	* Call `assumeRole`, extract temp credentials
* Options for temporary credentials with API calls
	* *Sign request* with temp credentials
	* Add AC / SK to request (*header* or *query string*)

<a name="3_3"></a>
## [↖](#top)[↑](#3_2_2)[↓](#3_3_1) S3

Amazon Simple Storage Service (S3) is object storage with a simple web service interface to store and
retrieve any amount of data from anywhere on the web. It is designed to deliver 11x9 durability and
scale past trillions of objects worldwide.

* **Key**-**value** storage (folder-like structure is only a UI representation)
* **Bucket** size is unlimited. Objects from 0B to 5TB.
* HA and scalable, transparent data partitioning
* Bucket lifecycle events can trigger *SNS*, *SQS* or *AWS Lambda*
	* New object created events
	* Object removal events
	* Reduced Redundancy Storage (RRS) object lost event
* Bucket names have to be globally unique, should comply with DNS naming conventions.
	* `http://bucket.s3.amazonaws.com`
	* `http://bucket.s3-aws-region.amazonaws.com`
	* `http://s3.amazonaws.com/bucket`
	* `http://s3-aws-region.amazonaws.com/bucket`

<a name="3_3_1"></a>
### Perfomance & Consistency
* Bucket operations **get** - **list** - **put** - **delete** - **head**
	* Implemented through *http* operations: `GET` - `PUT` - `DELETE` - `HEAD`
	* *Read-after-write consistency* for `PUT` of *new* objects.
	* *Eventual consistency* for *overwrite* `PUT` and `DELETE` (stale reads but low latency).
* Can only delete a bucket that is empty.
* *Scales* automatically, up to a certain limit:
	* Consistent:
		* `>100 PUT/LIST/DELETE/s`
		* `>300 GET/s`
	* Bursts:
		* `>300 PUT/LIST/DELETE/s`
		* `>800 GET/s`
* Key names are used to determine which partition to store the object in.
	* Make sure keys are spread out (not sequential)
		* E.g. by adding a random prefix to the key name
* For `GET` requests put *AWS CloudFront* in front of S3 bucket
	* Internal caching
	* Reduced latency - objects are physically closer to the consumer.
* **Multipart upload**
	* Recommended for objects >=100MB, mandatory for >=5GB
	* Supports parallel uploads
	* Can pause & resume
	* Can upload file while it's being created
	* 3 step process:
		* Initiate multipart upload
			* `POST /ObjectName?uploads HTTP/1.1`
		* Upload of all parts
			* `PUT /ObjectName?partNumber=PartNumber&uploadId=UploadId HTTP/1.1`
		* Complete Multipart upload
			* ```
				POST /ObjectName?uploadId=UploadId HTTP/1.1`
				<CompleteMultipartUpload>...
				```

<a name="3_3_2"></a>
### Hosting Static Websites
`<bucket-name>.s3-website-<AWS-Region>.amazonaws.com`
* Bucket name *must* match domain name. Every hosted bucket recieves its own URL
* Use *AWS Route 53* to integrate custom domains (also to automatically fail-over from dynamic website)
* Specify `index` & `error` documents
* In *AWS Route 53*: create hosted zone & record set
* Might need to add CORS configuration to bucket (cross origin resource sharing)

<a name="3_3_3"></a>
### Access Control
* **Effect** – This can be either allow or deny
* **Principal** – Account or user who is allowed access to the actions and resources in the statement
* **Actions** – For each resource, S3 supports a set of operations
* **Resources** – Buckets and objects are the resources
* Authorization works as a *union* of **IAM** & **bucket policies** and **bucket ACLs**
<a name="3_3_3_1"></a>
#### Defaults
* Bucket is *owned* by the AWS account that created it
	* Bucket ownership is not transferable
* Bucket owner gets full permission (ACL)
* The person paying the bills always has full control.
* A person uploading an object into a bucket owns it by default.
<a name="3_3_3_2"></a>
#### IAM
* IAM policies (in general) specify what actions are allowed or denied on what AWS resources
* Defined as JSON
* Attached to IAM users, groups, or roles (so they cannot grant access to anonymous users)
* Use if you’re more interested in *“What can this user do in AWS?”*
<a name="3_3_3_3"></a>
#### Bucket policies
* Specify what actions are allowed or denied for which principals on the bucket that the policy is
attached to
* Defined as JSON
* Attached *only* to S3 buckets. Can however effect object in buckets.
* Contain *principal* element (unnecessary for IAM)
* Use if you’re more interested in *“Who can access this S3 bucket?”*
* Easiest way to grant *cross-account permissions* for all `s3:*` permission. (Cannot do this with ACLs.)
<a name="3_3_3_4"></a>
#### ACLs
* Defined as XML. Legacy, not recomended any more.
* Can
	* be attached to individual objects (bucket policies only bucket level)
	* control access to object uploaded into a bucket from a *different* account.
* Cannot..
	* have conditions
	* cannot explicitely deny actions
	* grant permission to bucket sub-resources (eg. lifecycle or static website configurations)
* Other than *object ACL*s there are *bucket ACL*s as well - only for writing access log objects to a
bucket.
<a name="3_3_3_5"></a>
#### How to specify resources in a policy:
.|.
-|-
`arn:partition:service:region:namespace:relative-id`|`arn:aws:s3:::mybucket`
`arn:aws:s3:::*`|All buckets and objects in account
`arn:aws:s3:::mybucket`|`mybucket`
`arn:aws:s3:::mybucket/*`|All objects in `mybucket`
`arn:aws:s3:::mybucket/mykey`|`mykey` in `mybucket`
`arn:aws:s3:::mybucket/developers/($aws:username)/`|folder matching the accessing user's name
<a name="3_3_3_6"></a>
#### Pre-signed URLs
All objects are private by default. Only the object owner has permission to access these objects.
However, the object owner can optionally share objects with others by creating a **pre-signed URL**,
using their own security credentials, to grant time-limited permission to download the objects.

<a name="3_3_4"></a>
### Logging
* *AWS CloudTrail* logs S3-API calls for bucket-level operations (and many other information) and
stores them in an S3 bucket. Could also send email notifications or trigger *SNS* notifications for
specific events.
* *S3 Server Access Logs* log on object level.

<a name="3_3_5"></a>
### Versioning
* Works on bucket level (for *all* objects)
* Versioning can either be *unversioned* (default), *enabled* or *suspended*
* **Version ids** are automatically assigned to objects
	* Ids cannot changed.
	* As long as versioning is *disabled*, id is set to `null`
	* Once enabled, versioning can only be suspended (but not disabled)
	* `PUT` creates a new version, `GET` returns the latest version. Specific versions can be requested.
	* `DELETE` (without version) marks latest version as deleted and returns a `404` for subsequent `GET`s.
		* Older versions (pre-delete) can still be requested.
		* Restore old version by deleting the new version or by copying the old version on top of the bucket.
	* `DELETE` (with a version) permanently deletes that version.
	* If versioning is *suspendend*, S3 automatically adds a `null` version ID to every subsequent
object stored thereafter
* *Lifecycle Management policies* can automatically handle old versions, e.g. permanently delete or
move to *AWS Glacier*.
* Different versions of the same object can have different permissions.

<a name="3_3_6"></a>
### Encryption
<a name="3_3_6_1"></a>
#### Protecting data in transit
* Using an AWS KMS–Managed Customer Master Key (CMK)
	* Before *uploading* to S3, Client makes request to KMS, receives plain text encryption key and
	cypher blob, to upload to S3 as object metadata. Decrypt by sending cypher blob to KMS, retrieving
	plain text back, use for decryption.
	* Before *downloading* from S3, The client first downloads the encrypted object from Amazon S3 along
	with the cipher blob version of the data encryption key stored as object metadata. The client then
	sends the cipher blob to AWS KMS to get the plain text version of the same, so that it can decrypt
	the object data.
* Using a Client-Side Master Key
	* Clients provides a master key, S3 client generates random data
	key and encrypts with client's master key.
	* *Uploads* material description as part of the object metadata.
	* On *download* S3 client uses metadata to determine the right master key to use for decryption.
* Use *SSL encryption*
<a name="3_3_6_2"></a>
#### Protecting data at rest
* Uses *AES-256* (or others)
* Encryption can be enforced via bucket policy.
* Enable server-side encryption by adding specific header to request (`x-amz-server-side-encryption`).
* Server-Side Encryption with *Amazon S3-Managed Keys* (SSE-S3)
	* Each object is encrypted with a unique key employing strong multi-factor encryption
	* Furthermore it encrypts the key itself with a master key that is rotated regularly
* Server-Side Encryption with *AWS KMS-Managed Keys* (SSE-KMS)
	* Similar to SSE-S3, with extra benefits
	* Separate permissions for the use of an envelope key
	* Has audit trail
* Server-Side Encryption with *Customer-Provided Keys* (SSE-C)
	* Key is not stored with AWS (stores salted HMAC valued instead)

<a name="3_3_7"></a>
### Storage classes
.|.
-|-
S3 Standard|Durability 11x9
 |Availability 4x9
S3 IA (infrequent access)|Durability 11x9
 |Availability 3x9
S3 RRS (reduced redundancy storage)|Durability 4x9
 |Availability 4x9

<a name="3_3_8"></a>
### Request/response headers
Request|Response
-|-
`x-amz-content-sha256`|`x-amz-delete-marker`
`x-amz-date`|`x-amz-id-2 `
`x-amz-security-token`|`x-amz-request-id`
 |`x-amz-version-id `

<a name="3_3_9"></a>
### Error codes
.|.
-|-
400 Bad Request|`ExpiredToken`
400 Bad Request|`InvalidToken`
400 Bad Request|`InvalidArgument`
400 Bad Request|`InvalidRequest`
400 Bad Request|`IncompleteBody`
400 Bad Request|`IncompleteDigest`
400 Bad Request|`InvalidBucketName`
403 Forbidden|`AccessDenied`
403 Forbidden|`InvalidAccessKeyId`
404 Not Found|`NoSuchBucket`
404 Not Found|`NoSuchKey`
409 Conflict|`BucketAlreadyExists`
409 Conflict|`BucketNotEmpty`

<a name="3_3_10"></a>
### Limits
.|.
-|-
Buckets per account|100
Bucket policy max size|20KB
Object size|0B to 5TB
Object size in a single `PUT`|5GB

<a name="3_4"></a>
## [↖](#top)[↑](#3_3_10)[↓](#3_4_1) Dynamo DB

<a name="3_4_1"></a>
### Overview
* Fully managed **NoSQL** database
* *HA* through different AZs, automatically spreads data and traffic accross servers
	* 3 geographically distributed regions per table
* Can scale up and down depending on demand (no downtime, no performance degradation)
* Built-in monitoring
* User controlled read/write capacity (recently added: *auto-scaling*)
* Big data: Integrates with *AWS Elastic MapReduce* and *Redshift*
* No joins - create references to other tables manually (`table1#something`)
* Option between **eventual consistency** or **strongly consistency**
* Conditional updates and concurrency control (**atomic counters**)

<a name="3_4_2"></a>
### Core components
* A **table** is a collection of items.
	* Can be updated through a single `UpdateTable` command at a time (`ACTIVE` -> `UPDATING`)
* An **item** is a group of one or more attributes that is uniquely identifiable among all of the
other items. (*row* in a traditional db)
* An **attribute** is a fundamental data element, something that does not need to be broken down any
further. Can be nested up to 32 levels. (*column* in a traditional db)
* **Primary keys** are used to uniquely identify each item in a table. Apart from that DynamoDB is
*schemaless*, which means that neither the attributes nor their data types need to be defined
beforehand
* **Secondary indexes** are used to provide more querying flexibility
* **Control plane** operations create and manage DynamoDB table
* **Data plane** operations perform CRUD actions on data in a table
* **DynamoDB streams** operations capture data modification events in DynamoDB tables

<a name="3_4_3"></a>
### Keys and indexes
<a name="3_4_3_1"></a>
#### Partion key (PK)
* **Partition key** is also called **hash attribute** or **primary key**
* Must be unique, used for internal hash function (*unordered*)
* Used to retrieve data
<a name="3_4_3_2"></a>
#### PK & Sort key
* **Composite PK**: *index* composed of hashed PK (*unordered*) and SK (*ordered*)
* **Sort key** is also called **range attribute** or **range key**
* Different items can have the same *PK*, must have different *SK*

<a name="3_4_4"></a>
### Secondary indexes
* Associated with exactly one table, from which it obtains its data
* Allows to query or scan data by an *alternate key* (other than PK/SK)
* All secondary indexes are automatically maintained by DynamoDB as sparse objects
	* Items will only appear in an index if they exist in the base table
	* Makes querying very efficient
* Only for `read` operations, `write` is not supported.
* Tables with secondary indexes need to be created sequentially (`LimitExceededException`)
<a name="3_4_4_1"></a>
#### Projected attributes
* Attributes copied from the base table into an *index*
* Makes them queryable
* Different projection types
	* *KEYS_ONLY* - Only the index and primary keys are projected into the index
	* *INCLUDE* - Only the specified table attributes are projected into the index
	* *ALL* - All of the table attributes are projected into the index
<a name="3_4_4_2"></a>
#### Local secondary index
* Uses the *same PK*, but offers different *SK*
* Every partition of a local secondary index is scoped to a base table partition that has the same
partition key value
* Local secondary indexes are extra tables that dynamo keeps in the background
* Cannot be created after the base table has already been created.
* Can choose *eventual consistency* or *strong consistency* at *creation* time
* *Local* as in "co-located on the same partition"
* Can request *not-projected* attributes for query or scan operation
* Consumes read/write throughput from the original table.
<a name="3_4_4_3"></a>
#### Global secondary index
* Uses *different PK* and offers additional *SK* (or none).
* *PK* does not have to be unique (unlike base table)
* Queries on the global index can span all of the data in the base table, across all partitions
* Can be created after the base table has already been created.
* Only support *eventual consistency*
* Have their own provisioned read/write throughput
* Global secondary keys are distributed transactions across multiple partitions
* Global as in "over many partitions"
* Cannot request not-projected attributes for query or scan operation

<a name="3_4_5"></a>
### Capacity provisioning
* Unit for operations:
	* 1 *strongly consistent* `read` per second (up to 4KB/s)
	* 2 *eventual consistent* `read` per second (up to 8KB/s)
	* 1 `write` per second (up to 1KB)
* Algorithm

.|.
-|-
.|*300 strongly consistent reads of 11KB per minute*
Calculate read / writes per second|`300r/60s = 5r/s`
Multiply with payload factor|`5r/s * (11KB/4KB) = 15cu`
If eventual consistent, devide by 2|`15cu / 2 = 8cu`

* More throughput -> more reads / writes per second
* Exceeding allocated throughput may result in throttling of the operation. Check return code.
* Failing to distribute data accross partions can result in `ProvisionedThroughputExceededException`
* Local secondary index
	* `Read`
		* If read only index keys and projected attributes use same calculation
		* If more than index keys and projected attributes add extra latency and read capacity cost
			* Use read capacity from the index *and* for every item from the table
	* `Write` (to items in the base table that are indexed)
		* 1 for adding an item
		* 2 for changing the value of an item
	  * 1 for deleting and item
* Global secondary index
	* Read
		* Only supports eventual consistency, so 8KB/s base unit
		* Calculated the same as in tables, except that the size of the index entries is used instead
		of the size of the entire item
	* Write (to items in the base table that are indexed)
		* Putting, Updating, or Deleting items in a table consumes the index' write capacity units

<a name="3_4_6"></a>
### Query and scan operation
<a name="3_4_6_1"></a>
#### Query
* Finds items based on PK values
* Can *only* query any table or secondary index that have a composite primary key
* *Has* to use PK, *can* specify SK
* Very efficient, only searches index
* Result is orderd by SK
* Returns all attributes or only specified subset
* Eventually consistent per default, can request consistent read
* Can use *conditional attributes*

<a name="3_4_7"></a>
### Scan
* Reads every item in table (much worse performance than queries)
* Can *filter* result (slows down performance)
* The larger the data set in the table the slower the scan
* *Eventual consistent* reads by default, can specify *strongly consistent*
* Try to avoid scans
* Use *Page Size* to limit how much data is retrieved at the same time

<a name="3_4_8"></a>
### Atomic and conditional updates
<a name="3_4_8_1"></a>
#### Atomic Counters
* Increment or decrement the value of an existing attribute without interfering with other writes
* Request are applied in the order they are received
* *Not idempotent*
<a name="3_4_8_2"></a>
#### Conditional updates
* Only proceed if condition is met
* *Idempotent*

<a name="3_4_9"></a>
### How to grant temporary access
* *Web Identity Federation* - use existing OpenId provider, eg. Amazon, Google, Facebook
* *Amazon Cognito* does Web Identity Federation, also synchronizes app data
* *IAM* - contains role for users to assume

<a name="3_4_10"></a>
### API
* Control Plane

Create and manage tables|.
-|-
`CreateTable`|Creates a table and specifies the primary index used for data access
`DescribeTable`|Returns information such as primary key schema, throughput settings, index information
`ListTables`|Returns the names of all of your tables in a list
`UpdateTable`|Modifies the settings of a table or its indexes
`DeleteTable`|emoves a table and all of its dependent objects

* Data Plane

Creating data|.|conditional?
-|-|-
`PutItem`|Creates a new item, or replaces an old item with a new item|yes
`BatchWriteItem`|Puts or deletes multiple items in one or more tables|no
 |Called in a loop it typically checks for unprocesses items and submits a new `BWI` request for those

Reading data|.|conditional?
-|-|-
`GetItem`|Returns a set of Attributes for an item that matches the PK|no
`BatchGetItem`|Returns the attributes for multiple items from multiple tables using their PKs|no
`Query`|Gets one or more items using the table *PK*, or from a secondary index using the index key|no
`Scan`|Gets all items and attributes by performing a full scan across the table or a secondary index|no

Updating data|.|conditional?
-|-|-
`UpdateItem`|Modifies one or more attributes in an item|yes

Deleting data|.|conditional?
-|-|-
`DeleteItem`|Deletes a single item in a table by primary key|yes
`BatchWriteItem`|Puts or deletes multiple items in one or more tables|no
 |Called in a loop it typically checks for unprocesses items and submits a new `BWI` request for those

<a name="3_4_11"></a>
### Limits
.|.
-|-
Tables per account/region|256
Max read / write per table partition|3000 reads / 1000 writes
Partition key|min 1B, max 2048B
Sort key|min 1B, max 1024B
Local secondary index per table|5
Global secondary index per table|5
Item size|1B to 400KB, including name & value
Simultaneous `CreateTable`, `UpdateTable`, `DeleteTable`|up to 10
Single `BatchGetItem`|Max 100 items, must be <16MB
Single `BatchWriteItem`|Up to 25 *PutItem* or *DeleteItem*, must be <16MB
*Query* and *Scan* result set limit|1MB data per call

<a name="3_5"></a>
## [↖](#top)[↑](#3_4_11)[↓](#3_5_1) Elastic Compute Cloud (EC2)
* Resizable **compute capacity** in the cloud
* Amazon Machine Image (AMI)
	* Unit of deployment
	* Packaged-up environment that includes all the necessary bits to set up and boot an instance
	* Can create AMI from configured *EC2* instance

<a name="3_5_1"></a>
### Different options
* Payment models
	* **On-demand instances**
		* Pay for compute capacity by the hour, can be terminated by Amazon
	* **Reserved instances**
		* Provide a significant discount compared to On-Demand pricing and
		provide a capacity reservation when used in a specific Availability Zone
		* Can transfer between AZs
	* **Spot instances**
		* Bid on spare Amazon EC2 computing capacity, not available for all instance types
	* **Dedicated hosts**
		* A physical server with EC2 instance capacity fully dedicated to your use
* Instance sizes & types
	* *Sizes*: nano / micro / small / medium / large
	* *Types*: general purpose / computer optimized / memory optimized / gpu / storage optimized
* Pricing by
	* Compute time
	* Data transfer
	* Storage
	* Elastic IP address
	* Monitoring
	* Elastic load balancer

<a name="3_5_2"></a>
### Instance metadata & userdata
* Data about an instance that can be used to configure or manage the running instance
* Available from *running instance* under `http://169.254.169.254/latest/meta-data/`
* Contains various data about the current instance (static & dynamic)
* Can specify user-data
	* Allows to launch individual instances from same AMI

<a name="3_5_3"></a>
### API
.|.
-|-
`DescribeImages`|Describe an Amazon Machine Image
`RegisterImage`|Final process of creating an AMI

<a name="3_5_4"></a>
### Limits:
.|.
-|-
Elastic IP addresses for EC2-Classic|5

<a name="3_6"></a>
## [↖](#top)[↑](#3_5_4)[↓](#3_6_1) Elastic Load Balancer (ELB)
* **Distributes traffic** between instances that belong to the ELB group
* Stops sending requests to unhealthy instances
* Can store SSL certificates (offloads encryption to load balancer level)
* Can configure session stickyness:
	* *LB issued cookie*
		* Easy to implement, not best balancing
	* *Application issued cookie*
		* Cookies based on application session, marginally better
	* *ElastiCache*
		* Better distribution, requires state to be stored in *DB* or in *EC* memory.
		* EC memory is the much better option
* Relies on DNS / *Route53*
* Can route traffic into instances running in private subnets
	* Needs to be configured with (empty) public subnets though.

<a name="3_6_1"></a>
### Limits:
.|.
-|-
Total load balancers per region (ALB & ELB)|20

<a name="3_7"></a>
## [↖](#top)[↑](#3_6_1)[↓](#3_7_1) SNS
* **Publishes** messages to **subscribers** via topic
* **Pub-Sub-Service** for messaging
	* Scenarios:
		* *Fanout*: Many subsribers process event parallel and asyncronously
		* *Push to SQS*: Services pull from SQS, when they become available
		* *Alert*: Notification triggered by event or threshold
* **Mobile Notifications** to mobile devices
	* Sends *push notifications* to iOS, Android, Fire OS, Windows and Baidu-based devices

<a name="3_7_1"></a>
### Components
* **Publisher** (producer)
	* Communicates asynchronously with subscribers
	* Policies determine which topic(s) publishers can write to
* **Topics**
	* Unique name up to 256 characters
	* Stored redundantly on multitple servers and datacenters
* **Subscribers** (consumer)
	* Subscribes to topic
	* Endpoints like mobile app, web server, email, *AWS SQS*, *AWS Lambda*
		* Email subscriptions need to be confirmed
* **Messages**
	* Json-formatted key-value pairs
		* Fixed set + additional attributes if required
			* `POST`s to https endpoints with specific headers
				* Contains topics- and subscription-ARN
				* To identify messages without parsing the body
		* Up to 10 for SQS.
		* Provider-specific for mobile push notifications
	* Messages can be signed and verified
	* Message data:
		* `Message`, `MessageId`, `Signature`, `SignatureVersion`, `SigningCertURL`, `Subject`,
		`Timestamp`, `TopicArn`, `Type`, `UnsubscribeURL`

<a name="3_7_2"></a>
### Managing access
* Owner creates topic and controls access to it
* Can use own API (Access Control) and / or *IAM*, similar to *S3*
	* Access control policies
		* Default denies, needs explicit allow
		* Can grant access across account (API call: *AddPermission*)
	* IAM
		* More fine grained or very coarse, can include conditions
		* Can grant temporary security credentials

<a name="3_7_3"></a>
### Mobile push notifications
* Does not push to endpoint, but to PN-service (platform/provider specific)
	1. Request *credentials* from mobile platforms (ADM, APNS, etc...)
	2. Request a *token* from mobile platforms (*registrations id* for some platforms)
	3. Create a *platform application object*
	4. Create a *platform endpoint object*
	5. Publish a *message* to the mobile endpoint
* A single message can contain different data for different platforms

<a name="3_7_4"></a>
### API
.|.
-|-
`CreateTopic`|Create a new topic.
`DeleteTopic`|Delete a topic and all its subscriptions.
`Publish`| Publish a new message to the topic.
`ListTopics`|List of topics owned by a particular user (AWS ID).
`ListSubscriptions`|List subscriptions owned by a particular user (AWS ID)
`ListSubscriptionsByTopic`|List of subscriptions for a particular topic
`Subscribe`|Register a new subscription on a topic, will generate a confirmation message from Amazon SNS
`ConfirmSubscription`|Respond to a confirmation message, confirming to receive notifications from the topic
`UnSubscribe`|Cancel a previously registered subscription

<a name="3_7_5"></a>
### Limits:
.|.
-|-
Topics per account|100,000

<a name="3_8"></a>
## [↖](#top)[↑](#3_7_5)[↓](#3_8_1) SQS
* Scalable **message queue** service
* Allows *loose coupling* and *asynchronous processing*
* **Pull** from *SQS* (*Push* to *SNS*)
* PCI compliant
* Allows for asynchronous processing
* Protection against data loss on application failure

<a name="3_8_1"></a>
### Core features
* Redundant infrastructure
* Multiple readers / writers at the same time
* Access control via *SQS policies* (similar to *IAM*)
* **Standard queue**
	* Guarantees message delivery *at least once*
	* *No guarantee on message order*
	* No guarantee on not receiving duplicates (app has to deal with it)
* **FIFO queue**
	* Guaranteed order
	* Exactly-once processing
	* *Message groups* - multiple ordered message groups within a single queue
	* Name ends in `.fifo`
* **Delay queues**
	* Controls when a message becomes available
	* Between 0s and 15min, default 0s
* **Visibility timeout**
	* Controls when a polled message becomes visible again
	* Configurable and extendable for individual messages
	* Between 0s and 12h, default 30s
* **Message retention period**
	* Amount of time a message will live in the queue if it's not deleted
	* Between 1min and 14d, default 4d
* **In flight message**
	* Sent to a client but have not yet been deleted or have not yet reached the end of their
	 visibility window
* **Deadletter queue**
	* Queue that other queues can send messages to when these were not successfully
	processed.
* **Receive message wait time**
	* Value >0 enables *long polling*
	* Between 0s and 20s, default 0s (*short polling*)

<a name="3_8_2"></a>
### Message lifecycle
* Component 1 sends message A to queue
	* `SendMessage`/`SendMessageBatch`
* Component 2 retrieves A from queue.
	* A remains in queue while it's being processed, but is not returned to any other components
	* Message is now considered to be *in flight*.
	* `ReceiveMessage`
* Component 2 deletes A from queue during visibility timeout
	* Otherwise it will get processed again
	* SQS will never delete messages
	* `DeleteMessage`/`DeleteMessageBatch`

<a name="3_8_3"></a>
### Long polling vs short polling
* **Short polling** returns immediately, could be *false empty* (e.g. message not fully propagated yet)
* **Long polling** won't return unless there's a message in the queue or receive message wait time is
exceeded. Also checks *every server* to avoid false empty responses

<a name="3_8_4"></a>
### API
.|.
-|-
`SendMessage`/`SendMessageBatch`|Delivers a message to the specified queue (up to 20, <= 256KB)
`ReceiveMessage`|Retrieves one or more messages (up to 10), `WaitTimeSeconds` for long poll
`ChangeMessageVisibility`/`ChangeMessageVisibilityBatch`|Changes the visibility timeout of a message
`DeleteMessage`/`DeleteMessageBatch`|Deletes the specified message from the specified queue
`SetQueueAttribute`|e.g `DelaySeconds`, `MessageRetentionPeriod`
`GetQueueURL`|
`CreateQueue`|
`DeleteQueue`|
`ListQueues`|

<a name="3_8_5"></a>
### Limits:
.|.
-|-
Max message size|256KB
Max inflight messages|120,000

<a name="3_9"></a>
## [↖](#top)[↑](#3_8_5)[↓](#3_9_1) Cloudformation
* Allows to create and provision **resources** in a reusable **template** fashion
	* A *CloudFormation* template is a `JSON` or `YAML` formatted text file
* Related resources are managed in a single unit called a **stack**
	* All the resources in a stack are defined by the stack's *CloudFormation* template
* Two ways to update a stack
	* *Direct update*
	* Create **change set**
		* Summary of proposed changes
* Will **rollback** stack if it fails to create (can be disabled via API / console)

<a name="3_9_1"></a>
### Anatomy of template
* *AWSTemplateFormatVersion*
* *Description*
* *Metadata*
	* Details about the template
* *Parameters*
	* Values to pass in right before template creation
	* Allows validation per *regular expression*
* *Mappings*
	* Maps keys to values (eg different values for different regions)
* *Conditions*
	* Check values before deciding what to do
* *Resources*
	* Creates resources
* *Outputs*
	* Values to be exposed from the console or from API calls.
	* Can be used in a different stack (*cross stack references*)

<a name="3_9_2"></a>
### Intrinsic Functions
* Used to pass in values that are not available until runtime
* Usable in *resource* properties, *metadata* attributes, and *update policy* attributes (auto-scaling)
* `Fn::GetAtt`
	* Returns the value of an attribute from a resource in the template
* `Fn::FindInMap`
	* Returns the value corresponding to keys in a two-level map that is declared in the *Mappings* section
* `Fn::Join`
	* Appends a set of values into a single value, separated by the specified delimiter
* `Fn::GetAZs`
	* Returns an array that lists *Availability Zones* for a specified region
* `Fn::Select`
	* Returns a single object from a list of objects by index
* `Fn::ImportValue`
	* Returns the value of an *Output* exported by another stack
* `Fn::Split`
	* Split a string into a list of string values so that you can select an element from the resulting
string list
* `Fn::Sub`
	* Substitutes variables in an input string with values that you specify
* `Ref`
	* Returns the value of the specified parameter or resource

<a name="3_9_3"></a>
### Limits:
.|.
-|-
Max stacks per region|200
Max templates per region|unlimited
Parameters|60
Mappings|100
Resources|200
Outputs|60

<a name="3_10"></a>
## [↖](#top)[↑](#3_9_3)[↓](#3_10_1) Elastic Beanstalk (EB)
* **Full stack** that provisions *capacity*, sets up *load balancing* and *auto-scaling* and configures
*monitoring*
* No need to create / manage infrastructure
* Not good if full control of resource configuration is needed
* Not everything fits into the EB model

<a name="3_10_1"></a>
### AWS-Stack
* *EC2* instance
* Instance *Security Group*
* *Elastic Load Balancer*
* *Load Balancer Security Group*
* *Auto Scaling Group*
	* Automatically replaces instances if they become unavailable
* *S3 Bucket*
	* Source code, logs & othe artifacts
* *CloudWatch Alarm*
	* 2 alarms that monitor load on instances & Auto Scaling group scaling up / down
* *Cloudformation stack*
* *Domain name*
	* `subdomain.region.elasticbeanstalk.com`

<a name="3_10_2"></a>
### Supports
* Platform-specific application *source bundle* (e.g. Java `war` for Tomcat)
	* Go
	* Java with Tomcat
	* Java SE
	* .NET on Windows Server with IIS
	* Node.js
	* PHP
	* Python
	* Ruby (Passenger Standalone)
	* Ruby (Puma)
	* Single Container Docker
	* Multicontainer Docker
	* Preconfigured Docker (Glassfish)
	* Preconfigured Docker (Python 3.x)
	* Preconfigured Docker (Go)

<a name="3_10_3"></a>
### Core components
* **Application**
	* Logical collection of *Elastic Beanstalk* components, including *environments*, *versions*, and
	*environment configurations*. In Elastic Beanstalk an application is conceptually similar to a
	folder.
* **Application version**
	* An *application version* refers to a specific, labeled iteration of deployable code for a web
	application
* **Environment**
	* An environment is a version that is deployed onto AWS resources
	* Runs only a single application version at a time
	* Can run the same version or different versions in many environments at the same time
* **Environment Configuratoin**
	* Collection of parameters and settings that define how an environment and its associated resources behave
	* Updating a configuration will cause AWS to automatically apply the changes
* **Configuration template**
	* Starting point for creating unique environment configurations

<a name="3_10_4"></a>
### Limits:
.|.
-|-
Applications|75
Application Versions|1000
Environments|200

<a name="3_11"></a>
## [↖](#top)[↑](#3_10_4)[↓](#3_11_1) Simple Workflow Service (SWF)
* **Task coordination** and **state management** service
* Distributed, scales up and down depending on task
* Works with *on-premise* and *cloud* apps
* Allows for *synchronous* or *asynchronous* processing
* Can contain human events
* Guaranteed order of execution
* Tasks can live up to one year (`31,536,000 seconds`)

<a name="3_11_1"></a>
### Core components
* **Workflow**
	* A workflow is a set of *activities* that carry out some objective, together with logic that
	coordinates the activities.
* **Domain**
	* Scope of a *workflow*
	* An account can have multiple *domains*, each of which can contain multiple *workflows*
	* *Workflows* in different *domains* cannot interact
* **Workflow Starter**
	* Any application that can initiate workflow executions
* **Activity**
	* Things carried out by a *workflow*
* **Activity Task**
	* Represents one invocation of an *activity*
	* Can run synchronously or asynchronously
	* Gets assigned to worker
	* *Decision task* tells decider that state of workflow has changed
* **Activity Worker**
	* Is a program that receives *activity tasks*, performs them, and provides results back
	* Might be used by a person
	* Can live on *EC2* or on-premise
* **Decider**
	* Coordination logic in a *workflow*
	* Schedules *activity tasks*, provides input data to the *activity workers*, processes events that
		arrive while the *workflow* is in progress, and ultimately ends (or closes) the *workflow* when the
		objective has been completed.

<a name="3_11_2"></a>
### Limits:
.|.
-|-
Maximum registered domains|100

<a name="3_12"></a>
## [↖](#top)[↑](#3_11_2)[↓](#3_12_1) Virtual Private Cloud (VPC)
* Provisions a logically isolated section of the AWS cloud
* Spans over all AZs in a region
* Allows to create layered architecture
* Shared or dedicated tenancy (exclusive hardware or not)
* *Security groups* and subnet *network ACLs*
* Ability to extend on-premise network to cloud

<a name="3_12_1"></a>
### Overview
<a name="3_12_1_1"></a>
#### Default VPC (Amazon specific)
* Gives easy access to a VPC without having to configure it from scratch
* Has different subnets in different AZs and an internet gateway per AZ
* Each instance launched automatically receives a *public IP* (very different to non-default VPC)
* Cannot be restored if deleted
<a name="3_12_1_2"></a>
#### Non-default VPC (regular VPC)
* Only has private IP addresses
* Resources *only* accessible through *Elastic IP*, *VPN* or *internet gateways*
<a name="3_12_1_3"></a>
#### VPC Peering
* Connect VPCs through direct network routing
* Can occur between different accounts and VPCs, but must be  in the same region
* Allows instances to communicate with each other as if they were in the same network
<a name="3_12_1_4"></a>
#### VPC Scenarios
* VPC with private subnet only -> single tier apps
* VPC with public and private subnets -> layered apps
* VPC with public, private subnets and hardware connected VPN -> extending apps to on-premise
* VPC with private subnets and hardware connected VPN -> extended VPN

<a name="3_12_2"></a>
### Components
* **Subnet**
	* In exactly one AZ
	* If traffic is routed to an Internet gateway, the subnet is known as a public subnet
	* If a subnet doesn't have a route to the Internet gateway, it's known as a private subnet
	* EC2 instances are launched into subnets
	* Use ssh-agent forwarding to connect from public to private instances
	* Sometimes grouped into Subnet Groups, e.g. for caching or DB. Typically across AZs
* **Route Table**
	* Contains a set of rules, called routes that determine where network traffic is directed to
	* Each VPC automatically comes with a main route table that can be configured
	* Each subnet in a VPC must be associated with a route table; the table controls the routing
	for the subnet. A subnet can only be associated with one route table at a time, but multiple
	subnets can be associated with the same route table
	* Each route in a table specifies a destination CIDR and a target
	* Every route table contains a local route for communication within the VPC
	* Can have a *default route* 0.0.0.0/0 to route everything that doesn't have a specific rule
* **Elastic IP**
	* Static IPv4 address mapped to an instance or network interface
	* If attached to network interface it's decoupled from the instance's lifecycle
	* Routes to private IP address of instance
	* Can be remapped in case of failure.
	* For use in a specific region only
	* Can only map to instances in public subnets
* **Gateways**
	* *Internet Gateway*
		* Horizontally scaled, redundant, and highly available VPC component that allows communication
		between instances in a VPC and the internet
		* Provides a target in VPC route tables for internet-routable traffic
		* Performs network address translation (NAT) for instances that have been assigned public
		IPv4 addresses
	* *Virtual Private Gateway*
		* Has VPN connection to customer gateway attached
		* Serves as VPN concentrator on the Amazon side of the VPN connection
	* *Customer Gateway*
		* A physical device or software application on your side of the VPN connection
* **NAT**
	* *NAT Instances*
		* Manually configured instance from an NAT AMI
	* *NAT Gateway*
		* AWS-mananged service
<a name="3_12_2_1"></a>
#### Structure & package flow
* VPC (has *CIDR*)
	* Gateway (Internet or VPN)
	* Routes (one per subnet, can be shared)
	* Network ACL (one per subnet, can be shared)
	* Subnets (CIDRs match VPC's CIDR)
	* Security Group (on VPC level)
	* Instance (needs public IP for internet communication, either ELB or Elastic IP)

<a name="3_12_3"></a>
### Security
<a name="3_12_3_1"></a>
#### Network ACL
* Subnet level, acting as firewall
* Rules for inbound and outbound traffic
* Rules have numbers and are evaluated from low to high
* *Stateless*
<a name="3_12_3_2"></a>
#### Security Groups
* Acts as a virtual firewall to control inbound and outbound traffic to instances
* Acts on instance level, not subnet level
* Rules for inbound and outbound traffic
* *Stateful* - will always allow response to (allowed) outbound traffic
* Can refer to other security group, e.g. allow traffic from there

<a name="3_12_4"></a>
### Limits:
.|.
-|-
VPCs per region|5
Subnets per VPC|200
Customer gateways per region|50
Gateway per region|5 Internet
Elastic IPs per account per region|5
VPN connections per region|50
Route tables per region|200
Security groups per region|500

<a name="3_13"></a>
## [↖](#top)[↑](#3_12_4)[↓](#4) Relational Database Service (RDS)
* Set up, operate, and scale a **relational database** in the cloud
* Supports
	* Amazon Aurora
	* MySQL
	* MariaDB
	* Oracle
	* SQL Server
	* PostgreSQL
* Automates common administrative tasks such as performing **backups** and software **patching**
	* *Automated backups*
		* Performs a full daily snapshot
		* Enables point-in-time recovery
	* *DB Snapshots*
		* User-initiated
		* As frequent as desired
* Supports *encryption at rest* for all database engines
* **DB instance**
	* Database environment in the cloud with specified *compute* and *storage* resources
* **Multi-AZ deployments**
	* Provide enhanced availability and durability for DB Instances, making them a natural fit for
	production database workloads
* **DB subnet group**
	* Collection of subnets that you are designated for the RDS DB Instances in a VPC
* **Maintenance window**
	* Needs to be specified (or defaults to weekly) for maintenance events like scaling and patching
* **DB Parameter group**
	* Acts as a “container” for engine configuration values that can be applied to one or more DB
	Instances

<a name="4"></a>
# [↖](#top)[↑](#3_13)[↓](#) Etc
* *us-east-1* is the default region for all SDKs
* *Penetration tests* need to be anounced
