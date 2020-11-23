[toc_start]::
<a name="top"></a>
---
* [AWS-Solutions-Architect](#1)
* [10000 Feet Overview ](#2)
* [IAM ](#3)
  * [Overview](#3_1)
  * [Policies](#3_2)
  * [Limits](#3_3)
* [STS ](#4)
  * [Overview](#4_1)
  * [Scenarios](#4_2)
* [KMS ](#5)
  * [Overview](#5_1)
  * [Benfits](#5_2)
* [S3 ](#6)
  * [Overview](#6_1)
  * [Getting Data In And Out](#6_2)
  * [Access Control](#6_3)
  * [Encryption](#6_4)
  * [Etc](#6_5)
* [Glacier ](#7)
  * [Overview](#7_1)
* [CloudFront ](#8)
  * [Overview](#8_1)
* [Storage Gateway ](#9)
  * [Overview](#9_1)
  * [Gateway types](#9_2)
* [Snowball ](#10)
* [Elastic Compute Cloud (EC2) ](#11)
  * [Overview](#11_1)
  * [Storage Options](#11_2)
  * [Payment model](#11_3)
  * [Instance metadata & userdata](#11_4)
  * [AMIs](#11_5)
  * [Autoscaling](#11_6)
  * [Placement Groups](#11_7)
  * [Load Balancers](#11_8)
  * [Limits:](#11_9)
* [Elastic Block Storage (EBS) ](#12)
  * [Volume options](#12_1)
* [Elastic File System (EFS) ](#13)
  * [Overview](#13_1)
* [CloudWatch ](#14)
  * [Key metrics for EC2](#14_1)
* [Lambda ](#15)
  * [Overview](#15_1)
* [Route53 ](#16)
  * [DNS Overview](#16_1)
* [Relational Database Service (RDS) ](#17)
  * [RDS Backup](#17_1)
  * [Multi-AZ deployments](#17_2)
  * [Replicating RDS](#17_3)
  * [Etc](#17_4)
* [Dynamo DB ](#18)
  * [Overview](#18_1)
  * [Keys and indexes](#18_2)
  * [Secondary indexes](#18_3)
  * [Capacity provisioning](#18_4)
  * [Pricing](#18_5)
* [Amazon Redshift ](#19)
  * [Overview](#19_1)
  * [Pricing](#19_2)
* [ElastiCache ](#20)
  * [Overview](#20_1)
* [Aurora ](#21)
  * [Overview](#21_1)
  * [Scaling](#21_2)
  * [Replicas](#21_3)
* [Athena ](#22)
  * [Overview](#22_1)
* [Virtual Private Cloud (VPC) ](#23)
  * [Overview](#23_1)
  * [Components](#23_2)
  * [Structure & Package Flow](#23_3)
  * [VPC Endpoints](#23_4)
  * [Limits:](#23_5)
* [Simple Queue Service (SQS) ](#24)
  * [Overview](#24_1)
  * [Core features](#24_2)
  * [Limits:](#24_3)
* [Simple Workflow Service (SWF) ](#25)
  * [Overview](#25_1)
  * [Core components](#25_2)
  * [Limits:](#25_3)
* [Simple Notification Service (SNS) ](#26)
  * [Overview](#26_1)
  * [Components](#26_2)
  * [Limits](#26_3)
* [Elastic Transcoder](#27)
  * [Overview](#27_1)
* [API Gateway](#28)
  * [Overview](#28_1)
* [Kinesis](#29)
  * [Overview](#29_1)
* [Elastic Map Reduce](#30)
  * [Overview](#30_1)
* [Direct Connect](#31)
  * [Overview](#31_1)
* [ECS](#32)
  * [Overview](#32_1)
  * [Components](#32_2)
* [Workspaces](#33)
  * [Overview](#33_1)
* [OpsWorks](#34)
  * [Overview](#34_1)
* [AWS Organizations](#35)
  * [Overview](#35_1)
  * [Limits:](#35_2)
* [Resource Groups](#36)
  * [Overview](#36_1)
* [The Well Architected Framework](#37)
  * [Overview](#37_1)
  * [Security](#37_2)
  * [Reliability](#37_3)
  * [Performance Efficiency](#37_4)
  * [Cost efficiency](#37_5)
  * [Operational excellence](#37_6)
---
[toc_end]::
<a name="1"></a>
# [↖](#top)[↑](#)[↓](#2) Solutions Architect Associate

> 9/2018 - 2/2019

---

<a name="2"></a>
# [↖](#top)[↑](#1)[↓](#3) 10000 Feet Overview 

Area|Covered|Other
-|-|-
**Compute**||EKS
.||Lightsail
.||Batch
.|.|ECR
.|.|Elastic Beanstalk
**Storage**||FSx
.||AWS Backup
.||.
.||.
**Database**||Neptune
.||Amazon DocumentDB
.||.
.||.
**Migration**||AWS Migration Hub
.|.|Application Discovery Service
.|.|Database Migration Service
.|.|Server /Migration Service
.|.|AWS Transfer for SFTP
.|.|DataSync
**Networking & Content Delivery**||Global Accelerator
.||AWS Cloud Map
.||.
.||.
.||.
**Tools**|.|CodeStar
.|.|CodeCommit
.|.|CodeBuild
.|.|CodeDeploy
.|.|CodePipeline
.|.|Cloud9
.|.|X-Ray
**Robotics**|.|AWS RoboMaker
**Blockchain**|.|Amazon Managed Blockchain
**Satellite**|.|Ground Station
**Management Tools**||AWS Auto Scaling
.|**CloudFormation**|Service Catalog
.|**CloudTrail**|Systems Manager
.|**Config**|Managed Services
.||Control Tower
.|**Trusted Advisor**|AWS License Manager
.|.|AWS Well-Architected Tool
.|.|Personal Health Dashboard
**Media Services**||Kinesis Video Streams
.|.|MediaConvert
.|.|MediaLive
.|.|MediaPackage
.|.|MediaStore
.|.|MediaTailor
**Machine Learning**|.|Amazon SageMaker
.|.|Amazon Comprehend
.|.|AWS DeepLens
.|.|Amazon Lex
.|.|Machine Learning
.|.|Amazon Polly
.|.|Rekognition
.|.|Amazon Transcribe
.|.|Amazon Translate
.|.|Amazon Personalize
.|.|Amazon Forecast
.|.|Amazon Textract
**Analytics**||MKS
.||CloudSearch
.|**Data Pipeline**|Elasticsearch Service
.||QuickSight
.|.|AWS Glue
**Security, Identity & Compliance**||Cognito
.|**Inspector**|Secrets Manager
.|**Certificate Manager**|GuardDuty
.|**Directory Service**|Amazon Macie
.||Security Hub
.||AWS Single Sign-On
.|.|CloudHSM
.|.|WAF & Shield
.|.|Artifact
.|.|Resource Access Manager
.|.|AWS Organizations
**AWS Cost Management**|.|AWS Cost Explorer
.|.|AWS Budgets
.|.|AWS Marketplace Subscriptions
**Mobile**|.|Mobile Hub
.|.|AWS AppSync
.|.|Device Farm
.|.|AWS Amplify
**AR & VR**|.|Amazon Sumerian
**Application Integration**||Step Functions
.||Amazon MQ
.||.
**Customer Engagement**|**Simple Email Service**|Amazon Connect
.|.|Pinpoint
**Business Applications**|.|Alexa for Business
.|.|Amazon Chime
.|.|WorkMail
**End User Computing**|.|WorkSpaces
.|.|AppStream 2.0
.|.|WorkDocs
.|.|WorkLink
**Internet of Things**|.|IoT Core
.|.|IoT 1-Click
.|.|IoT Device Management
.|.|IoT Analytics
.|.|Greengrass
.|.|Amazon FreeRTOS
.|.|IoT Device Defender
.|.|IoT Events
.|.|IoT SiteWise
.|.|IoT Things Graph
**Game Development**|.|Amazon GameLift

---

<a name="3"></a>
# [↖](#top)[↑](#2)[↓](#3_1) IAM 

<a name="3_1"></a>
## [↖](#top)[↑](#3)[↓](#3_2) Overview
IAM is a *global* service that helps to securely control access to AWS resources.

* **Users** - end users
  * Hold credentials
* **Groups** - collection of users under one set of permissons
  * Typically only provides permission to assume a role
* **Roles** - assigned to AWS resources
  * Users and / or services assume roles
	* Can have **trust relationships** with trusted entities that can *assume* this role
* **Policies** - defines one or more permissions
  * Can be attached to users, groups or roles (preferred)
* An **instance profile** is a container for an IAM role that you can use to pass role information to an
	EC2 instance when the instance starts.

<a name="3_2"></a>
## [↖](#top)[↑](#3_1)[↓](#3_2_1) Policies
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
<a name="3_2_1"></a>
### IAM Policies
* Managed policies (the new way)
	* *Customer managed* policies
	* *AWS managed* policies
		* Updated by AWS if new APIs come out
	* Both can be attached to multiple users, groups and roles
* Inline policies (the old way)
  * Cannot be reused

<a name="3_3"></a>
## [↖](#top)[↑](#3_2_1)[↓](#4) Limits
.|.
-|-
Groups per account|100
Instance profiles|100
Roles|500
Server certificates|20
Users|5000

---

<a name="4"></a>
# [↖](#top)[↑](#3_3)[↓](#4_1) STS 

<a name="4_1"></a>
## [↖](#top)[↑](#4)[↓](#4_2) Overview
The *AWS Security Token Service* (STS) is a global web service that enables you to request temporary,
limited-privilege credentials for AWS Identity and Access Management (IAM) users or for users that
you authenticate (federated users).

<a name="4_2"></a>
## [↖](#top)[↑](#4_1)[↓](#5) Scenarios
* Identity Federation
  * Enterprise Identity Federation
    * SAML or custom federation broker
      * *Identity Broker* (needs to be developed) communicates with AD
      * Identity broker always authenticates LDAP first, then AWS STS
      * Application then gets temporary access to AWS resources
  * Web Identity Federation
    * Third party ID provider like Google, OpenID Connect
* Roles for Cross-account Access
* Roles for Amazon EC2

---

<a name="5"></a>
# [↖](#top)[↑](#4_2)[↓](#5_1) KMS 

<a name="5_1"></a>
## [↖](#top)[↑](#5)[↓](#5_2) Overview
AWS Key Management Service (KMS) makes it easy for you to create and manage keys and control the
use of encryption across a wide range of AWS services and in your applications. AWS KMS is a
secure and resilient service that uses FIPS 140-2 validated hardware security modules to protect
your keys. AWS KMS is integrated with AWS CloudTrail to provide you with logs of all key usage to
help meet your regulatory and compliance needs.

<a name="5_2"></a>
## [↖](#top)[↑](#5_1)[↓](#6) Benfits
* Fully managed
* Centralized key management
* Manage Encryption for AWS services
* Encrypt data in your application
* Built-in auditing
* Low cost
* Secure
* Compliance

---

<a name="6"></a>
# [↖](#top)[↑](#5_2)[↓](#6_1) S3 

<a name="6_1"></a>
## [↖](#top)[↑](#6)[↓](#6_2) Overview
Amazon Simple Storage Service (S3) is object storage with a simple web service interface to store and
retrieve any amount of data from anywhere on the web. It is designed to deliver 11x9 *durability* and
scale past trillions of objects worldwide.

* **Key**-**value** storage (folder-like structure is only a UI representation)
* **Bucket** size is unlimited. Objects from 0B to 5TB.
* HA and scalable, transparent data partitioning
  * Data is automatically replicated to at least 3 separate data centers in the same region
* Bucket lifecycle events can trigger *SNS*, *SQS* or *AWS Lambda*
	* New *object created* events
	* *Object removal* events
	* Reduced Redundancy Storage (RRS) *object lost* event
* Buckets are *per region*, but AWS console is *global* (displaying all bucket for that account)
* Bucket names have to be *globally* unique, should comply with DNS naming conventions.
  * Virtual-hosted-style:
    * `http://<bucket-name>.s3.amazonaws.com`
    * `http://<bucket-name>.s3-<aws-region>.amazonaws.com`
  * Path-style:
    * `http://s3.amazonaws.com/<bucket-name>`
    * `http://s3-<aws-region>.amazonaws.com/<bucket-name>`

<a name="6_2"></a>
## [↖](#top)[↑](#6_1)[↓](#6_2_1) Getting Data In And Out

<a name="6_2_1"></a>
### Perfomance & Consistency
* Bucket operations **get** - **list** - **put** - **delete** - **head**
	* Implemented through *http* operations: `GET` - `PUT` - `DELETE` - `HEAD`
	* *Read-after-write consistency* for `PUT` of *new* objects.
	* *Eventual consistency* for *overwrite* `PUT` and `DELETE` (stale reads but low latency).
* Can only delete a bucket that is empty.
* *Scales* automatically, up to a certain limit:
	* Consistent:
		* `>3500 PUT/LIST/DELETE/s`
		* `>5500 GET/s`
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

<a name="6_2_2"></a>
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
* Can enable *MFA delete* for an extra layer of security.
* Versioning integrates with lifecycle rules.

<a name="6_2_3"></a>
### Logging
* *AWS CloudTrail* logs S3-API calls for bucket-level operations (and many other information) and
  stores them in an S3 bucket. Could also send email notifications or trigger *SNS* notifications for
  specific events.
* *S3 Server Access Logs* log on object level.
  * Provide detailed records for the requests that are made to a bucket
  * Needs to be enabled on bucket level

<a name="6_2_4"></a>
### Transfer Acceleration
*Amazon S3 Transfer Acceleration* enables fast, easy, and secure transfers of files over long distances
between your client and an S3 bucket. Transfer Acceleration takes advantage of Amazon CloudFront’s globally
distributed edge locations. As the data arrives at an edge location, data is routed to Amazon S3 over an
optimized network path.
* File upload through an Edge location via a dedicated CloudFront endpoint

<a name="6_2_5"></a>
### Cross-Region Replication
* Buckets *must* be in different regions
  * Can replicate cross-account
* *Must* have versioning enabled
* Only new / changed objects will be replicated
* Cannot chain replications
* Can replicate complete buckets or subfolder ('prefix')
* Deleting of individual versions or delete markers is *not* replicated
* Best way to copy existing objects over is using AWS CLI

<a name="6_2_6"></a>
### Hosting Static Websites
`<bucket-name>.s3-website-<AWS-Region>.amazonaws.com`
* Bucket name *must* match domain name. Every hosted bucket recieves its own URL
* Use *AWS Route 53* to integrate custom domains (also to automatically fail-over from dynamic website)
* Specify `index` & `error` documents
* In *AWS Route 53*: create hosted zone & record set
* Might need to add CORS configuration to bucket (cross origin resource sharing)

<a name="6_2_7"></a>
### Storage classes
.|Durability|Availability|AZs|Costs per GB|Retrieval Fee|.
-|-|-|-|-|-|-
S3 Standard|**11x9**|**4x9**|**>=3**|$0.023|**No**|.
S3 Intelligent Tiering|**11x9**|3x9|**>=3**|$0.023|**No**|Automatically moves objects between two access tiers based on changing access patterns
S3 IA (infrequent access)|**11x9**|3x9|**>=3**|$0.0125|Yes|For data that is accessed less frequently, but requires rapid access when needed
S3 One Zone IA (infrequent access)|**11x9**|99.5|1|**$0.01**|Yes|For data that is accessed less frequently, but requires rapid access when needed
Glacier|**11x9**|.|**>=3**|.|Yes|For archival only, comes as *expedited*, *standard* or *bulk*
Glacier Deep Archive|**11x9**|.|**>=3**|.|Yes|Longer time span to retrieve
~~S3 RRS (reduced redundancy storage)~~|4x9|4x9|>=3|$0.024|.|Deprecated

<a name="6_3"></a>
## [↖](#top)[↑](#6_2_7)[↓](#6_3_1) Access Control
* **Effect** – This can be either allow or deny
* **Principal** – Account or user who is allowed access to the actions and resources in the statement
* **Actions** – For each resource, S3 supports a set of operations
* **Resources** – Buckets and objects are the resources
* Authorization works as a *union* of **IAM** & **bucket policies** and **bucket ACLs**
<a name="6_3_1"></a>
### Defaults
* Bucket is *owned* by the AWS account that created it
  * Ownership refers to the identity and email address used to create the account
	* Bucket ownership is not transferable
* Bucket owner gets full permission (ACL)
* The person paying the bills always has full control.
* A person uploading an object into a bucket owns it by default.
<a name="6_3_2"></a>
### IAM
* IAM policies (in general) specify what actions are allowed or denied on what AWS resources
* Defined as JSON
* Attached to IAM users, groups, or roles (so they cannot grant access to anonymous users)
* Use if you’re more interested in *“What can this user do in AWS?”*
<a name="6_3_3"></a>
### Bucket policies
* Specify what actions are allowed or denied for which principals on the bucket that the policy is
attached to
* Defined as JSON
* Attached *only* to S3 buckets. Can however effect object in buckets.
* Contain *principal* element (unnecessary for IAM)
* Use if you’re more interested in *“Who can access this S3 bucket?”*
* Easiest way to grant *cross-account permissions* for all `s3:*` permission. (Cannot do this with ACLs.)
<a name="6_3_4"></a>
### ACLs
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
<a name="6_3_5"></a>
### How to specify resources in a policy:
.|.
-|-
`arn:partition:service:region:namespace:relative-id`|`arn:aws:s3:::mybucket`
`arn:aws:s3:::*`|All buckets and objects in account
`arn:aws:s3:::mybucket`|`mybucket`
`arn:aws:s3:::mybucket/*`|All objects in `mybucket`
`arn:aws:s3:::mybucket/mykey`|`mykey` in `mybucket`
`arn:aws:s3:::mybucket/developers/($aws:username)/`|folder matching the accessing user's name
<a name="6_3_6"></a>
### Pre-signed URLs
All objects are private by default. Only the object owner has permission to access these objects.
However, the object owner can optionally share objects with others by creating a **pre-signed URL**,
using their own security credentials, to grant time-limited permission to download the objects.

<a name="6_4"></a>
## [↖](#top)[↑](#6_3_6)[↓](#6_4_1) Encryption

<a name="6_4_1"></a>
### Protecting data in transit
* Using an AWS KMS–Managed Customer Master Key (CMK)
	* Before *uploading* to S3, Client makes request to KMS, receives plain text encryption key and
	cypher blob, to upload to S3 as object metadata. Decrypt by sending cypher blob to KMS, retrieving
	plain text back, use for decryption.
	* Before *downloading* from S3, The client first downloads the encrypted object from Amazon S3 along
	with the cipher blob version of the data encryption key stored as object metadata. The client then
	sends the cipher blob to AWS KMS to get the plain text version of the same, so that it can decrypt
	the object data.
* Using a client-Side Master Key
	* Clients provides a master key, S3 client generates random data
	key and encrypts with client's master key.
	* *Uploads* material description as part of the object metadata.
	* On *download* S3 client uses metadata to determine the right master key to use for decryption.
* Use *SSL encryption*
<a name="6_4_2"></a>
### Protecting data at rest
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

<a name="6_5"></a>
## [↖](#top)[↑](#6_4_2)[↓](#6_5_1) Etc

<a name="6_5_1"></a>
### Pricing
Charged by
  * Storage
  * Requests
  * Storage management pricing
    * Tags
  * Data transfer
    * For cross-region transfers only
  * Transfer acceleration (feature)

<a name="6_5_2"></a>
### Limits
.|.
-|-
Buckets per account|100
Bucket policy max size|20KB
Object size|0B to 5TB
Object size in a single `PUT`|5GB

---

<a name="7"></a>
# [↖](#top)[↑](#6_5_2)[↓](#7_1) Glacier 

<a name="7_1"></a>
## [↖](#top)[↑](#7)[↓](#8) Overview
*Amazon S3 Glacier* is a secure, durable, and extremely low-cost cloud storage service for data
archiving and long-term backup. It is designed to deliver 99.999999999% durability, and provides
comprehensive security and compliance capabilities that can help meet even the most stringent
regulatory requirements. Amazon S3 Glacier provides query-in-place functionality, allowing you to
run powerful analytics directly on your archive data at rest. Customers can store data for as
little as $0.004 per gigabyte per month, a significant savings compared to on-premises solutions.
To keep costs low yet suitable for varying retrieval needs, Amazon S3 Glacier provides three
options for access to archives, from a few minutes to several hours.

---

<a name="8"></a>
# [↖](#top)[↑](#7_1)[↓](#8_1) CloudFront 

<a name="8_1"></a>
## [↖](#top)[↑](#8)[↓](#9) Overview
* A *content delivery network* (CDN) is a system of distributed servers (network) that delivers
  web pages and other web content to a user based on the geographic location of the user, the
  origin of the webpage and a content delivery server.
* The content is delivered from an **edge location**
  * Content can be *dynamic*
  * Objects are cached for TTL
  * Can invalidate manually, but this costs money
  * Typically for READ, but can PUT as well
* A collection of edge locations is called a *distribution*
  * *Web* distribution for web content
  * *RTMP* distribution for Flash content
* AWS CloudFront can be used to deliver an entire website using a global network of edge locations
  * Requests for content are automatically routed to the nearest edge location
  * Optimized to work with S3, EC2, ELB and Route53
  * Can configure geo-restrictions if required
  * Can serve from *custom origin* like on-prem servers

---

<a name="9"></a>
# [↖](#top)[↑](#8_1)[↓](#9_1) Storage Gateway 

<a name="9_1"></a>
## [↖](#top)[↑](#9)[↓](#9_2) Overview
*AWS Storage Gateway* is a hybrid cloud storage service that connects your existing on-premises
environments with the AWS Cloud. Its features make it easy for you to run hybrid cloud workloads at
any stage of your cloud adoption, whether it's getting started with cloud backups, running cloud
processing workflows for data generated by on-premises machines, or performing a one-time migration
of block volume data or databases.

The gateway connects to AWS storage services, such as Amazon S3, Amazon Glacier, Amazon EBS, and
AWS Backup, providing storage for files, volumes, snapshots, and virtual tapes in AWS.

* Download as VM image, install on host in datacenter

<a name="9_2"></a>
## [↖](#top)[↑](#9_1)[↓](#9_2_1) Gateway types

<a name="9_2_1"></a>
### File gateway (NFS, SMB)
The *File Gateway* presents a file interface that enables you to store files as objects in Amazon S3
using the industry-standard NFS and SMB file protocols, and access those files via NFS and SMB
from your datacenter or Amazon EC2, or access those files as objects with the S3 API.
* Can be managed as S3 native objects (bucket policies, cross-region replication etc)
* File gateway offers SMB or NFS-based access to data in Amazon S3 with local caching.

<a name="9_2_2"></a>
### Volume gateway (iSCSI)
The *Volume Gateway* presents your applications storage volumes using the iSCSI block protocol. Data
written to these volumes can be asynchronously backed up as point-in-time snapshots of your volumes,
and stored in the cloud as Amazon EBS snapshots. You can set the schedule for when snapshots occur or
create them via the AWS Management Console or service API. Snapshots are incremental backups that
capture only changed blocks. All snapshot storage is also compressed to minimize your storage charges.
* *Stored* volumes (all data on-prem, EBS snapshots in cloud, stored on S3)
* *Cached* volumes (only recently used data on-prem, EBS volumes in cloud, stored on S3)

<a name="9_2_3"></a>
### Tape gateway (VTL)
The *Tape Gateway* presents itself to your existing backup application as an industry-standard
iSCSI-based virtual tape library (VTL), consisting of a virtual media changer and virtual tape drives.
You can continue to use your existing backup applications and workflows while writing to a nearly
limitless collection of virtual tapes. Each virtual tape is stored in Amazon S3. When you no longer
require immediate or frequent access to data contained on a virtual tape, you can have your backup
application move it from the Storage Gateway Virtual Tape Library into an archive tier that sits on
top of Amazon Glacier cloud storage, further reducing storage costs.

---

<a name="10"></a>
# [↖](#top)[↑](#9_2_3)[↓](#11) Snowball 

Snowball is a petabyte-scale data transport solution that uses devices designed to be secure to transfer
large amounts of data into and out of the AWS Cloud. Using Snowball addresses common challenges with
large-scale data transfers including high network costs, long transfer times, and security concerns.
Customers today use Snowball to migrate analytics data, genomics data, video libraries, image repositories,
backups, and to archive part of data center shutdowns, tape replacement or application migration projects.
Transferring data with Snowball is simple, fast, more secure, and can be as little as one-fifth the cost of
transferring data via high-speed Internet.

This replaces *Import Export* which was a manual service to ship drives to AWS.

* Snowball
  * Import/export to S3
* Snowball Edge
  * With onboard compute
* Snowmobile
  * The thing on the truck

---

<a name="11"></a>
# [↖](#top)[↑](#10)[↓](#11_1) Elastic Compute Cloud (EC2) 

<a name="11_1"></a>
## [↖](#top)[↑](#11)[↓](#11_2) Overview
* Resizable **compute capacity** in the cloud
* Amazon Machine Image (AMI)
	* Unit of deployment
	* Packaged-up environment that includes all the necessary bits to set up and boot an instance
	* Can create AMI from configured *EC2* instance
* Can have _termination protection_ enabled (`off` by default)

<a name="11_2"></a>
## [↖](#top)[↑](#11_1)[↓](#11_2_1) Storage Options
* **Instance Store** (ephemeral)
  * Located on disks that are physically attached to the host computer
  * Will preserve data over *reboot*
  * Will *loose* data over *stop*, *termination* or *failure* of the underlaying host
  * Cannot detach
  * Cannot opt for non-deletion of root volume if instance get deleted
* 
* 
* 

<a name="11_2_1"></a>
### S3 vs EFS vs EBS Comparison

Amazon S3|Amazon EBS|Amazon EFS
-|-|-
Can be publicly accessible|Accessible only via the given EC2 Machine|Accessible via several EC2 machines and AWS services
Web interface|File system interface|Web and file system interface
Object Storage|Block storage|Object storage
Scalable|Hardly scalable|Scalable
Slowest|Fastest|Faster than S3, slower than EBS
Good for storing backups|Is meant to be EC2 drive|Good for shareable applications and workloads
Elastic, only pay for used storage|Fixed, pay for provisioned storage|Elastic, only pay for used storage
<a name="11_3"></a>
## [↖](#top)[↑](#11_2_1)[↓](#11_3_1) Payment model
* **On-demand instances**
	* Pay for compute capacity by the hour, instance can be terminated by Amazon
* **Reserved instances**
	* Provide a significant discount compared to On-Demand pricing and provide a capacity reservation
    when used in a specific Availability Zone
  * Up to 50% cheaper than a *fully utilized* on-demand instance (because we commit upfront to a
    certain usage)
  * Guarantees to *not* run into '*insufficent instance capacity*' issues if AWS is unable to
    provision instances in that AZ
  * Can resell reserved capacity on *Reserved Instance Marketplace*
	* Can transfer between AZs
  * Types:
    * *Standard* reserved instances (fixed instance type)
    * *Convertible* reserved instances (can be exchanged against another convertible instance type)
    * *Scheduled* reserved instances (purchased by the hour on a set schedule with a set instance type)
* **Spot instances**
	* Bid on spare Amazon EC2 computing capacity, not available for all instance types
* **Dedicated instance**
  * Run on dedicated hardware, but no need to purchase the whole host
* **Dedicated hosts**
	* A physical server with EC2 instance capacity fully dedicated to your use

<a name="11_3_1"></a>
### Pricing by
* Instance Type
* Compute time
* Data transfer
* Storage
* Elastic IP address
* Monitoring
* Elastic load balancer

<a name="11_3_2"></a>
### Instance Types
Family|Mnemomic|Description
-|-|-
**F**|FPGA|Can be reprogrammed on the fly and be tuned for  specific applications, making them faster than traditional CPU/GPU combinations
**I**|IOPS|(NVMe) SSD-backed instance storage optimized for low latency
**G**|Graphics|GPU optimized
**H**|High disk throughput|HDD-based local storage
**T**|Cheap general purpose|Balance of computer, memory and networking
**D**|Density|Lowest price per disk throughput performance
**R**|RAM|Lowest prize for *memory* performance
**M**|Main choice for general purpose apps|Balance of computer, memory and networking
**C**|Compute|Lowest prize for *compute* performance
**P**|Graphics (pics)|GPU optimized
**X**|eXtreme memory|Lowest prize for *memory* performance

<a name="11_4"></a>
## [↖](#top)[↑](#11_3_2)[↓](#11_5) Instance metadata & userdata
* Data about an instance that can be used to configure or manage the running instance
* Contains various data about the current instance (static & dynamic)
* Can specify user-data
	* Allows to launch individual instances from same AMI
* Available from *running instance*
  * `http://169.254.169.254/latest/meta-data/`
  * `http://169.254.169.254/latest/user-data/`

<a name="11_5"></a>
## [↖](#top)[↑](#11_4)[↓](#11_6) AMIs
Choose by
* Region
* OS
* Architecture
* Launch permissions
* Storage for root device
Need to manually copy
* User-defined tags
* Launch permission
* S3 bucket permissions

<a name="11_6"></a>
## [↖](#top)[↑](#11_5)[↓](#11_7) Autoscaling
**Auto Scaling** distributes load across multiple instances
* *Scheduled Scaling* allows to scale or shrink on a schedule
* Relatively complex to set up
* Applications need to be designed to benefit from multiple instances
* Components
  * *Launch Configuration*
  * *Autoscaling Group*
  * *Scaling Policy*
  * *Cloudwatch Alarms*

<a name="11_7"></a>
## [↖](#top)[↑](#11_6)[↓](#11_8) Placement Groups
* Determine how instances are placed on underlying hardware
* **Cluster**
  * Clusters instances into a low-latency group in a single Availability Zone
  * Oldest/orignal placement group
  * Only certain instances can be launched into a clustered placement group
* **Spread**
  * Spreads instances across underlying hardware
  * Minimizes risk as instances are spread
  * Opposite of clustered placement group
  * Up to 7 instances per AZ
* Recommendation to stick to one instance family
* Cannot move existing instance into placement group

<a name="11_8"></a>
## [↖](#top)[↑](#11_7)[↓](#11_9) Load Balancers
.|**ALB**|**NLB**|**ELB**
-|-|-|-
.|Active Load Balancer|Network Load Balancer|Classic Load Balancer
Layer|7 (application layer)|4 (transport layer)|EC2-classic network (deprecated)
Protocoll|HTTP, HTTPS|TCP|TCP, SSL, HTTP, HTTPS

* `x-forwarder-for` header has IP address of end user
* ELBs don't have ipv4 address, need to be resolved by DNS name
* ALBs now supports host-based and path-based routing
  * `api.example.com/production`, `mobile.example.com/test`

<a name="11_9"></a>
## [↖](#top)[↑](#11_8)[↓](#12) Limits:
.|.
-|-
Elastic IP addresses for EC2-Classic|5

---

<a name="12"></a>
# [↖](#top)[↑](#11_9)[↓](#12_1) Elastic Block Storage (EBS) 
* **Permanent block storage**, independent to instance
* Attachable to running EC2 instances (same AZ)
* Only accessible by a *single instance*
* Can be encrypted
* Can be stopped, data will persist
* Stores redundantly in *single* AZ
* Only root volumes are terminated if instance gets terminate
* Can be striped together to RAID

<a name="12_1"></a>
## [↖](#top)[↑](#12)[↓](#12_1_1) Volume options
.|.|.
-|-|-
**General purpose SSD**|GP2|`<= 10,000 IOPS`
**Provisioned IOPS**|I01|`> 10,000 IOPS`
**Magnetic volumes, throughput optimized**|ST1, HS1|* Frequently accessed workload<br/>* Cannot be boot volume
**Magnetic volumes, cold**|SC1|* Less frequently accessed workload<br/>* Cannot be boot volume
**Magnetic volumes, standard**|.|Can be boot volume

* Can change volume size on the fly, also storage type

<a name="12_1_1"></a>
### Snaphosts
* Stored incrementally on S3
* Should stop instance if taking a snapshot of root volume
* Snaphots of encrypted volumes are encrypted automatically
* Snapshots can be shared with other account or made public - only if unencrypted
* Can create AMIs from EBS-backed instances and snapshots
* In order to take snapshots from RAID arrays, make sure all applications are stopped and caches are flushed to disk
* Lifecycle policies have been introduced for snapshots

<a name="12_1_2"></a>
### Moving Instances/Volumes To A Different AZ/Region
* Create snapshot in AZ1
* Use that to create volume in AZ2
* Also could have *copied* snapshot into different region

* TODO: Look into moving instances into different regions / AZs

<a name="12_1_3"></a>
### Encrypting root volumes
* Stop instance
* Create snapshot
* Copy to different region
  * Can encrypt while copying, resulting in an encrypted snapshot in the target region
* Create image from snapshot
* Launch instance from that image

---

<a name="13"></a>
# [↖](#top)[↑](#12_1_3)[↓](#13_1) Elastic File System (EFS) 

<a name="13_1"></a>
## [↖](#top)[↑](#13)[↓](#14) Overview
* **Scalable file storage** for use with *Amazon EC2 instances*
* Elastic storage capacity, growing and shrinking as files are added or removed
* *Multiple EC2 instances* from *multiple AZs* can access an EFS file system at the same time
* Stores redundantly in multiple AZs
* 2 Storage classes
  * Standard
  * Infrequent access
    * Can use lifecylce rules to move object over

---

<a name="14"></a>
# [↖](#top)[↑](#13_1)[↓](#14_1) CloudWatch 
Monitoring service that plugs into many other services

* **Metrics**
  * Based on currently used service
  * Not everything is available out of the box, e.g. no data on memory usage of EC2 instances
* **Alarms**
  * Based on thresholds defined on metrics
  * Can be added to dashboard
  * Invoke *Lambda*, *SNS*, email, ...
  * Takes place once, at a specific point in time
    * Disable with `mon-disable-alarm-actions` via CLI
* **Logs**
  * Log into *log groups*
* **Events**
  * Define actions on things that happened
  * Define `cron`-based events
  * Events are recorded constantly over time

<a name="14_1"></a>
## [↖](#top)[↑](#14)[↓](#15) Key metrics for EC2
* EC2 metrics are based on what is exposed to the hypervisor.
* *Basic Monitoring* (default) submits values every 5 minutes, *Detailed Monitoring* every minute
* Can install Cloudwatch agent (new)
  * Provides access to more metrics
* Can use Cloudwatch monitoring scripts (old) to provide more metrics
  * Perl-scripts provided by AWS, need to manually install on instance
  * Use `cron` to automate sending data to CloudWatch

Metric|Effect
-|-
`CPUUtilization`|The total CPU resources utilized within an instance at a given time.
`DiskReadOps`,`DiskWriteOps`|The number of read (write) operations performed on all instance store volumes. This metric is applicable for instance store-backed AMI instances.
`DiskReadBytes`,`DiskWriteBytes`|The number of bytes read (written) on all instance store volumes. This metric is applicable for instance store-backed AMI instances.
`NetworkIn`,`NetworkOut`|The number of bytes received (sent) on all network interfaces by the instance
`NetworkPacketsIn`,`NetworkPacketsOut`|The number of packets received (sent) on all network interfaces by the instance
`StatusCheckFailed`,`StatusCheckFailed_Instance`,`StatusCheckFailed_System`|Reports whether the instance has passed both/instance/system status check in the last minute.

* Can **not** monitor **memory usage**, **available disk space**, **swap usage**

---

<a name="15"></a>
# [↖](#top)[↑](#14_1)[↓](#15_1) Lambda 

<a name="15_1"></a>
## [↖](#top)[↑](#15)[↓](#16) Overview
*AWS Lambda* lets you run code without provisioning or managing servers. You pay only for the
compute time you consume - there is no charge when your code is not running. With Lambda, you can
run code for virtually any type of application or backend service - all with zero administration.
Just upload your code and Lambda takes care of everything required to run and scale your code with
high availability. You can set up your code to automatically trigger from other AWS services or
call it directly from any web or mobile app.

* Features
  * No servers
  * Continuous scaling
    * Cold Start - if no idle container is available to run the lambda
  * Very cheap
  * Can give more RAM which will proportionaly increase CPU as well
* Supported languages
  * nodejs
  * Java
  * C#
  * Python
  * Golang
  * Ruby
  * Powershell
* Priced by
  * Number or requests, first 1 mio requests are free
  * Duration (max time 5 min)
* Concurrency
  * `invocations/s * runtime` (eg. 10/s * 4s = 40)
  * Initial concurrency burst, eg. 500
  * Max concurrency burst limit: 1000

---

<a name="16"></a>
# [↖](#top)[↑](#15_1)[↓](#16_1) Route53 

<a name="16_1"></a>
## [↖](#top)[↑](#16)[↓](#16_1_1) DNS Overview
Domain Name System (**DNS**) is a system for naming computers and network services that is organized
into a hierarchy of domains. DNS naming is used in TCP/IP networks, such as the Internet, to locate
computers and services with user-friendly names. When a user enters a DNS name in an application,
DNS services can resolve the name to other information that is associated with the name, such as
an IP address.

<a name="16_1_1"></a>
### Terminology
* **Hosts** - Computers or services accessible within a domain
* **Name Server** - Translates domain names into IP addresses
* **Zone File** - Text file that contains mappings between domain names and IP addresses
* **Records** - Entries in zone file, mappings beween resources and names

<a name="16_1_1_1"></a>
#### Basic Flow
Root Server -> TLD Server -> Domain-Level Name Server -> Zone File

<a name="16_1_1_2"></a>
#### Zone File & Records
Zone file stores records. Various records exists:

Type|Definition|Example
-|-|-
**SOA**|State of Authority - Mandatory first entry, defines various things,<br/>eg name servers & admin contact|`ns1.dnsimple.com admin.dnsimple.com 2013022001 86400 7200 604800 300`
**A**|Map host name to ip4 address|`px01.vc.example.com.  198.51.100.40`
**AAAA**|Map host name to ip6 address|`px01.vc.example.com.  2a00:1450:4014:80c:0:0:0:2004`
**CNAME**|Defines alias for host name<br/>(maps one domain name to another)|`www.dnsimple.com. dnsimple.com.`
**MX**|Defines mail exchange|`example.com.  1800  MX  mail1.example.com.  10`
**PTR**|Maps ip4 address to host name (inverse to A record)|`10.27/1.168.192.in-addr.arpa.  1800  PTR mail.example.com.`
**SVR**|Points one domain to another domain name using a specific destination port|`_sip._tcp.example.com. 86400 IN SRV 0 5 5060 sipserver.example.com.`

<a name="16_1_2"></a>
### Route53 specifics
* Global service
* **Alias** record
  * Amazon Route 53 alias records provide a Route 53–specific extension to DNS functionality.
  Alias records let you route traffic to selected AWS resources, such as CloudFront distributions
  and Amazon S3 bucket. They also let you route traffic from one record in a hosted zone to another
  record.
  * Unlike a CNAME record, you can create an alias record at the top node of a DNS namespace, also
  known as the *zone apex*. For example, if you register the DNS name example.com, the zone apex is
  example.com. You can't create a CNAME record for example.com, but you can create an alias record
  for example.com that routes traffic to www.example.com
  * Preferred choice over CNAME (TODO: why?)

<a name="16_1_3"></a>
### Route53 Routing Policies
  * **Simple**
    * Default policy, typically used if only a single resource performs functionality
  * **Weighted**
    * Control distribution of traffic with DNS entries
      * This can be based on a certain percentage
      * Set *routing policy* to weighted (instead of failover)
  * **Latency**
    * Control distribution of traffic based on latency.
  * **Failover**
    * Can set up *health checks* for endpoints or domains from within *Route53*
      * Route 53 has health checkers in locations around the world. When you create a health check that
        monitors an endpoint, health checkers start to send requests to the endpoint that you specify
        to determine whether the endpoint is healthy.
      * `evaluate target health`
    * DNS entries are then being associated with health checks and can be configured to failover as
      well (1 primary and n secondary recordsets)
  * **Geolocation**
    * Geolocation routing lets you choose the resources that serve your traffic based on the geographic
      location of your users, meaning the location that DNS queries originate from. For example, you
      might want all queries from Europe to be routed to an ELB load balancer in the Frankfurt region.
  * **Geoproximity Routing (Traffic Flow Only)**
    * Geoproximity routing lets Amazon Route 53 route traffic to your resources based on the geographic
      location of your users and your resources. You can also optionally choose to route more traffic or
      less to a given resource by specifying a value, known as a bias. A bias expands or shrinks the
      size of the geographic region from which traffic is routed to a resource.
  * **Multivalue Answer Routing**
    * Multivalue answer routing lets you configure Amazon Route 53 to return multiple values, such as
    IP addresses for your web servers, in response to DNS queries. You can specify multiple values for
    almost any record, but multivalue answer routing also lets you check the health of each resource,
    so Route 53 returns only values for healthy resources. It's not a substitute for a load balancer,
    but the ability to return multiple health-checkable IP addresses is a way to use DNS to improve
    availability and load balancing.

---

<a name="17"></a>
# [↖](#top)[↑](#16_1_3)[↓](#17_1) Relational Database Service (RDS) 
* Set up, operate, and scale a **relational database** in the cloud
* Supports
	* Amazon Aurora
	* MySQL
	* MariaDB
	* Oracle
	* SQL Server
	* PostgreSQL
	* MS SQL-Server
* Supports *encryption at rest* for all database engines
  * Can only be applied to a *new* instance
  * This could be created from an existing snapshot
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

<a name="17_1"></a>
## [↖](#top)[↑](#17)[↓](#17_2) RDS Backup
* Two types of backups
  * Automated backups
    * Enabled by default
    * Allow to recover database within a *retention period* (1d - 35d)
      * *Transactional* storage engine recommended as DB engine
      * Will take daily snapshot and use transaction logs
      * PITR down to 1 second (within retention period)
    * Backups are taken within defined window
      * Degrades performance if *multi-AZ* is not enabled!
      * Taken from slave if *multi-AZ* is enabled
    * Backups are stored internaly on S3
      * Free storage space equal to DB size
      * Deleting an instance deletes all *automated* backups
  * Database Snapshots
    * Only manually, always user initiated
    * Won't be deleted with DB instance
* Restoring
  * When restoring, only default parameters and security groups are associated with instance
  * Can change to different storage engine if closely related and enough space available
  * Restored version will always be a *new* RDS instance with a *new* DNS endpoint

<a name="17_2"></a>
## [↖](#top)[↑](#17_1)[↓](#17_3) Multi-AZ deployments
Amazon RDS Multi-AZ deployments provide enhanced availability for database instances within a
single AWS Region.

* Meant for *disaster recover*, not for performance improvement (-> Read Replica)
* Configure RDS for **multi-AZ-deployments** and turn replication on
  * Keeps a **synchronous** standby replica in a different AZ
    * Recommendation is use of Provisioned IOPS
  * Automatic failover in case of planned or unplanned outage of the first AZ
    * Most likely still has downtime
    * Can *force* failover by *rebooting*
  * Other benefits
    * Patching
    * Backups
  * *Aurora* can replicate accross 3 AZs

<a name="17_3"></a>
## [↖](#top)[↑](#17_2)[↓](#17_4) Replicating RDS
* Using **read replicas**
  * Read queries are routed to *read replicas*, reducing load on primary db instance
    (*source instance*)
    * Table indexes can be created on read replicas directly (and not on the master)
    * Some use cases (e.g. data analytics) can be performed exclusively against read replicas
  * To create read replicas, AWS initally creates a snapshot of the source instance
    * Multi-AZ failover instance (if enabled) is used for snapshotting
    * After that all read queries are then **asynchronously** copied to read replica
    * Implies data latency, which typically is acceptable.
      * `ReplicaLag` can be monitored and *Cloudwatch* alarms can be configured
    * No AWS charges for data replication
  * A single master can have **up to 5** read replicas
    * Can be in different regions
    * Can have Multi-AZ enabled themselves
  * *Read replicas* are **not** the same as *multi-AZ failover* instances which
    * are *synchronously* updated
    * are designed to handle failover
    * don't receive any load unless failover actually happens
  * Often it is beneficial to have both read replicas and multi-AZ failover instances
* Setting up a read replica
  * Configure from master instance or other read replica
    * Requires 'automated backups' to be enabled on source instance
  * Choice of db engine matters, because internal engine features are being used
  * Usually pick same database instance type as source instance uses
  * AWS provisiones different *endpoint* for read replica
  * Configure use of endpoint on application level
* Read replicas can be promoted to normal instances
  * E.g. use read replica to implement bigger changes on db level, after these have been finished
  promote to master instance
  * This will break replication
  * Useful for database sharding, could create replicas for each shard

<a name="17_4"></a>
## [↖](#top)[↑](#17_3)[↓](#18) Etc
* *DB security groups* are used with DB instances that are not in a VPC and on the EC2-Classic platform.
  * Don't need to specify a destination port number when you create DB security group rules
* *RDS Reserved instances* are available for multi-AZ deployments.
* Cannot SSH into an RDS instance

---

<a name="18"></a>
# [↖](#top)[↑](#17_4)[↓](#18_1) Dynamo DB 

<a name="18_1"></a>
## [↖](#top)[↑](#18)[↓](#18_2) Overview
* Fully managed **NoSQL** database
* Always stored on SSD
* *HA* through different AZs, automatically spreads data and traffic accross servers
	* 3 geographically distributed regions per table
* Can scale up and down depending on demand (no downtime, no performance degradation)
* Built-in monitoring
* User controlled read/write capacity (recently added: *auto-scaling*)
* Big data: Integrates with *AWS Elastic MapReduce* and *Redshift*
* No joins - create references to other tables manually (`table1#something`)
* Option between **eventual consistency** or **strongly consistency**
* Conditional updates and concurrency control (**atomic counters**)

<a name="18_2"></a>
## [↖](#top)[↑](#18_1)[↓](#18_2_1) Keys and indexes

<a name="18_2_1"></a>
### Partion key (PK)
* **Partition key** is also called **hash attribute** or **primary key**
* Must be unique, used for internal hash function (*unordered*)
* Used to retrieve data
* You should design your application for uniform activity across all logical partition keys in the
  Table and its secondary indexes.

<a name="18_2_2"></a>
### PK & Sort key
* **Composite PK**: *index* composed of hashed PK (*unordered*) and SK (*ordered*)
* **Sort key** is also called **range attribute** or **range key**
* Different items can have the same *PK*, must have different *SK*

<a name="18_3"></a>
## [↖](#top)[↑](#18_2_2)[↓](#18_3_1) Secondary indexes
* Associated with exactly one table, from which it obtains its data
* Allows to query or scan data by an *alternate key* (other than PK/SK)
* Only for `read` operations, `write` is not supported.

<a name="18_3_1"></a>
### Projected attributes
* Attributes copied from the base table into an *index*
* Makes them queryable
* Different projection types
	* *KEYS_ONLY* - Only the index and primary keys are projected into the index
	* *INCLUDE* - Only the specified table attributes are projected into the index
	* *ALL* - All of the table attributes are projected into the index

<a name="18_3_2"></a>
### Local secondary index
* Uses the *same PK*, but offers different *SK*
* Every partition of a local secondary index is scoped to a base table partition that has the same
  partition key value
* Local secondary indexes are extra tables that dynamo keeps in the background
* Cannot be created after the base table has already been created.
* Can choose *eventual consistency* or *strong consistency* at *creation* time
* *Local* as in "co-located on the same partition"
* Can request *not-projected* attributes for query or scan operation
* Consumes read/write throughput from the original table.

<a name="18_3_3"></a>
### Global secondary index
* Uses *different PK* and offers additional *SK* (or none).
* *PK* does not have to be unique (unlike base table)
* Queries on the global index can span all of the data in the base table, across all partitions
* Can be created after the base table has already been created.
* Only support *eventual consistency*
* Have their own provisioned read/write throughput
* Global secondary keys are distributed transactions across multiple partitions
* Global as in "over many partitions"
* Cannot request not-projected attributes for query or scan operation

<a name="18_4"></a>
## [↖](#top)[↑](#18_3_3)[↓](#18_5) Capacity provisioning
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

<a name="18_5"></a>
## [↖](#top)[↑](#18_4)[↓](#19) Pricing
* Storage cost
  * Per GB per month
* Provisioned throughput capacity *per table*
  * *Write* throughput per 10 units
  * *Read* throughput per 50 units
  * -> Expensive for writes, cheap for reads

---

<a name="19"></a>
# [↖](#top)[↑](#18_5)[↓](#19_1) Amazon Redshift 

<a name="19_1"></a>
## [↖](#top)[↑](#19)[↓](#19_2) Overview
Amazon Redshift is a fully managed, petabyte-scale data warehouse service in the cloud. You can
start with just a few hundred gigabytes of data and scale to a petabyte or more.

* Start with Single Node (160Gb)
* Extend to Multi-Node
  * *Leader-Node* (1)
  * *Compute-Node* (up to 128)
  * Utitlizes MPP (*Massively Parallel Processing*)
* Data encryption in transit and at rest.
* Only available in 1 AZ. (Not designed for HA)

Data is stored in colums, not in rows. This is better for data-analytics (*OLAP*) as a row-based
approach (which would be better for transaction-processing (*OLTP*)):
* Better I/O throughput because of sequential reads
* Advanced compression because of sequential storage on medium
* Also, does not require indexes or materialized views
  * Uses less disk space

Redshift is a good answer if your database is feeling stress because it's running OLAP transactions.

<a name="19_2"></a>
## [↖](#top)[↑](#19_1)[↓](#20) Pricing
* Compute-Node hours
* Backup
* Data transfer

---

<a name="20"></a>
# [↖](#top)[↑](#19_2)[↓](#20_1) ElastiCache 

<a name="20_1"></a>
## [↖](#top)[↑](#20)[↓](#21) Overview
Amazon ElastiCache offers fully managed *Redis* and *Memcached*. Seamlessly deploy, run, and scale
popular open source compatible in-memory data stores.

* Memcached
  * A widely adopted memory object caching system. ElastiCache is protocol compliant with Memcached,
    so popular tools that you use today with existing Memchached environments willwork seamlessly with
    the service.

* Redis
  * A popular open-source in-memory key-value store that supports data structures such as sorted sets
    and lists. ElastiCache supports master/slave replication and multi-AZ which can be used to achieve
    cross-AZ-redundancy.
  * Also offers Pub/Sub, Sorted Sets and In-Memory Data Store

ElastiCache is a good choice if database is read-heavy and not prone to frequent changing.

---

<a name="21"></a>
# [↖](#top)[↑](#20_1)[↓](#21_1) Aurora 

<a name="21_1"></a>
## [↖](#top)[↑](#21)[↓](#21_2) Overview
*Amazon Aurora* is a MySQL and PostgreSQL-compatible relational database built for the cloud, that
combines the performance and availability of traditional enterprise databases with the simplicity
and cost-effectiveness of open source databases.

Amazon Aurora is up to five times faster than standard MySQL databases and three times faster than
standard PostgreSQL databases. It provides the security, availability, and reliability of
commercial databases at 1/10th the cost. Amazon Aurora is fully managed by Amazon Relational
Database Service (RDS), which automates time-consuming administration tasks like hardware
provisioning, database setup, patching, and backups.

Amazon Aurora features a distributed, fault-tolerant, self-healing storage system that auto-scales
up to 64TB per database instance. It delivers high performance and availability with up to 15 low
latency read replicas, point-in-time recovery, continuous backup to Amazon S3, and replication
across three Availability Zones (AZs).

* *Multi-Master*
  * Is a new feature of the Aurora MySQL-compatible edition that adds the ability to scale out
    write performance across multiple Availability Zones.
* *Continuous Backups*
  * Backups are continuous and incremental so you can quickly restore to any point within the
    backup retention period.
<a name="21_2"></a>
## [↖](#top)[↑](#21_1)[↓](#21_3) Scaling
* Starts with 10GB, scales in 10GB increments (storage scaling)
* Compute resources scale up to 32vCPUs and 244GB of memory
* 2 copies of data is contained in each AZ, with a minimum of 3 AZs (6 copies of data in total)
  * Designed to transparently handle the loss of up to 2 copies without affecting *write*
  * Up to 3 copies without affecting *read*
  * (this is storage only, it still has the DB engine has a single point of failure)

<a name="21_3"></a>
## [↖](#top)[↑](#21_2)[↓](#22) Replicas
* 2 types
  * Up to 15 *Aurora replicas*
  * Up to 5 *MySQL read replicas*

---

<a name="22"></a>
# [↖](#top)[↑](#21_3)[↓](#22_1) Athena 

<a name="22_1"></a>
## [↖](#top)[↑](#22)[↓](#23) Overview

Amazon Athena is an interactive query service that makes it easy to analyze data in Amazon S3
using standard SQL. Athena is serverless, so there is no infrastructure to manage, and you pay
only for the queries that you run.

Athena is easy to use. Simply point to your data in Amazon S3, define the schema, and start
querying using standard SQL. Most results are delivered within seconds. With Athena, there’s no
need for complex ETL jobs to prepare your data for analysis. This makes it easy for anyone with
SQL skills to quickly analyze large-scale datasets.

Supports different formats
* CSV
* JSON
* ORC
* Avro
* Parquet

---

<a name="23"></a>
# [↖](#top)[↑](#22_1)[↓](#23_1) Virtual Private Cloud (VPC) 

<a name="23_1"></a>
## [↖](#top)[↑](#23)[↓](#23_1_1) Overview
* Provisions a logically isolated section of the AWS cloud
* Spans over all AZs in a region
* Allows to create layered architecture
* Shared or dedicated tenancy (exclusive hardware or not)
  * Cannot be changed after VPC creation
* *Security groups* and subnet-level *network ACLs*
* Ability to extend on-premise network to cloud

<a name="23_1_1"></a>
### Default VPC (Amazon specific)
* Gives easy access to a VPC without having to configure it from scratch
* Has different subnets in different AZs and an internet gateway (HA, spread out to all AZs)
* Each instance launched automatically receives a *public IP* (and a private IP), this is
  usually not the case for non-default VPCs)
* Cannot be restored if deleted
* Comes with default NACL that allows all inbound/outbound traffic
<a name="23_1_2"></a>
### Non-default VPC (regular VPC)
* Only has private IP addresses
* Resources *only* accessible through *Elastic IP*, *VPN* or *internet gateways*
<a name="23_1_3"></a>
### VPC Peering
* Connect VPCs through direct network routing
* Can occur between different accounts and regions
* Cannot have matching or overlapping CIDR blocks
* Allows instances to communicate with each other as if they were in the same network
* Peering is in star configuration with 1 central VPC. No transitive peering.
* Only routes traffic between source and destination VPC
  * Does not support edge to edge routing
  * Does not share VPN connection into datacenter
<a name="23_1_4"></a>
### VPC Scenarios
* VPC with private subnet only -> single tier apps
* VPC with public and private subnets -> layered apps
* VPC with public, private subnets and hardware connected VPN -> extending apps to on-premise
* VPC with private subnets and hardware connected VPN -> extended VPN

<a name="23_2"></a>
## [↖](#top)[↑](#23_1_4)[↓](#23_3) Components
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
  * *Egress-Only* Gateway
    * Allows outbound communication over IPv6 from instances in your VPC to the Internet
    * Prevents the Internet from initiating an IPv6 connection with your instances.
    * (IPv6 addresses are globally unique, and are therefore public by default)
	* *Virtual Private* Gateway
    * AWS side of Site-to-site VPN
		* Has VPN connection to customer gateway attached
		* Serves as VPN concentrator on the Amazon side of the VPN connection
	* *Customer Gateway*
    * Customer side of Site-to-site VPN
		* A physical device or software application on your side of the VPN connection
* **NAT**
	* *NAT Instances*
		* Manually configured instance from an NAT AMI
    * Need to manually disable *source/destination check* on the instance
	* *NAT Gateway*
		* AWS-mananged service
    * HA per AZ, create one gateway per AZ
* **Network ACL**
  * Subnet level, acting as firewall
  * One subnet can (and must) only ever be associated to one NACL, however, one NACL can be
    associated to many subnets
  * Rules for inbound and outbound traffic
  * Rules have numbers and are evaluated from low to high
  * Default is to deny everything in and out
  * *Stateless*
  * Support *allow* and *deny* rules
  * Can block IP addresses (Security groups can't)
* **Security Groups**
  * Acts as a virtual firewall to control inbound and outbound traffic to instances
  * Acts on instance level, not subnet level
  * 'Allow rules' for inbound and outbound traffic (*no* explicite deny rules)
    * All outbound traffic is allowed by default
    * All inbound traffic is denied per default
  * Support *allow* rules only
  * *Stateful* - will always allow response to (allowed) outbound traffic
  * Can refer to other security group, e.g. allow traffic from there
  * Can have mulitple security groups attached to an instance
  * Can have any number of instances within a security group
  * Cannot block individual IP adresses (use NACL for that)

<a name="23_3"></a>
## [↖](#top)[↑](#23_2)[↓](#23_3_1) Structure & Package Flow
<a name="23_3_1"></a>
### Package flow through VPC components
* VPC (has *CIDR*)
	* Gateway (Internet or VPN)
  * Router
	* Route table (one per subnet, can be shared)
	* Network ACL (one per subnet, can be shared)
	* Subnets (CIDRs match VPC's CIDR)
	* Security Group (on VPC level)
	* Instance (needs public IP for internet communication, either ELB or Elastic IP)

<a name="23_3_2"></a>
### VPC Flow Logs
VPC Flow Logs is a feature that enables you to capture information about the IP traffic going to
and from network interfaces in your VPC. Flow log data can be published to Amazon CloudWatch Logs
and Amazon S3. After you've created a flow log, you can retrieve and view its data in the chosen
destination.

Can be created at 3 levels:
* VPC
* Subnet
* Network interface

<a name="23_4"></a>
## [↖](#top)[↑](#23_3_2)[↓](#23_5) VPC Endpoints
Allows instances with a VPC to connect to services without going via public internet.

Supported by:
Amazon API Gateway, AWS CloudFormation, Amazon CloudWatch, Amazon CloudWatch Events, Amazon
CloudWatch Logs, AWS CodeBuild, AWS Config, Amazon EC2 API, Elastic Load Balancing API, Amazon
Elastic Container Registry, Amazon Elastic Container Service, AWS Key Management Service, Amazon
Kinesis Data Streams, Amazon SageMaker and Amazon SageMaker Runtime, Amazon SageMaker Notebook
Instance, AWS Secrets Manager, AWS Security Token Service, AWS Service Catalog, Amazon SNS, Amazon
SQS, AWS Systems Manager, Endpoint services hosted by other AWS accounts, Supported AWS
Marketplace partner services


<a name="23_5"></a>
## [↖](#top)[↑](#23_4)[↓](#24) Limits:
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

TODO: Build own VPC from memory

---

<a name="24"></a>
# [↖](#top)[↑](#23_5)[↓](#24_1) Simple Queue Service (SQS) 

<a name="24_1"></a>
## [↖](#top)[↑](#24)[↓](#24_2) Overview
* Oldest AWS service
* Scalable **message queue** service
* Allows *loose coupling* and *asynchronous processing*
* **Pull** from *SQS* (*Push* to *SNS*)
* PCI compliant
* Allows for asynchronous processing
* Protection against data loss on application failure

<a name="24_2"></a>
## [↖](#top)[↑](#24_1)[↓](#24_3) Core features
* Redundant infrastructure
* Multiple readers / writers at the same time
* Access control via *SQS policies* (similar to *IAM*)
* **Standard queue**
  * Default queue
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

<a name="24_3"></a>
## [↖](#top)[↑](#24_2)[↓](#25) Limits:
.|.
-|-
Max message size|256KB
Max inflight messages|120,000

---

<a name="25"></a>
# [↖](#top)[↑](#24_3)[↓](#25_1) Simple Workflow Service (SWF) 

<a name="25_1"></a>
## [↖](#top)[↑](#25)[↓](#25_2) Overview
* **Task coordination** and **state management** service
* Distributed, scales up and down depending on task
* Works with *on-premise* and *cloud* apps
* Allows for *synchronous* or *asynchronous* processing
* Can contain human events
* Guaranteed order of execution
* Tasks can live up to one year (`31,536,000 seconds`)

<a name="25_2"></a>
## [↖](#top)[↑](#25_1)[↓](#25_3) Core components
* **Workflow**
	* A workflow is a set of *activities* that carry out some objective, together with logic that
	coordinates the activities.
* **Domain**
	* Scope of a *workflow*
	* An account can have multiple *domains*, each of which can contain multiple *workflows*
	* *Workflows* in different *domains* cannot interact
* **Activity**
	* Things carried out by a *workflow*
* **Activity Task**
	* Represents one invocation of an *activity*
	* Can run synchronously or asynchronously
	* Gets assigned to worker
  * Guaranteed to be assigned only once and to never be duplicated
	* *Decision task* tells decider that state of workflow has changed
* **Actors**
  * **Workflow Starter**
    * Any application that can initiate workflow executions
  * **Activity Worker**
    * Is a program that receives *activity tasks*, performs them, and provides results back
    * Might be used by a person
    * Can live on *EC2* or on-premise
  * **Decider**
    * Coordination logic in a *workflow*
    * Schedules *activity tasks*, provides input data to the *activity workers*, processes events that
      arrive while the *workflow* is in progress, and ultimately ends (or closes) the *workflow* when the
      objective has been completed.

<a name="25_3"></a>
## [↖](#top)[↑](#25_2)[↓](#26) Limits:
.|.
-|-
Maximum registered domains|100


---

<a name="26"></a>
# [↖](#top)[↑](#25_3)[↓](#26_1) Simple Notification Service (SNS) 

<a name="26_1"></a>
## [↖](#top)[↑](#26)[↓](#26_2) Overview
* **Publishes** messages to **subscribers** via topic
* **Pub-Sub-Service** for messaging
	* Scenarios:
		* *Fanout*: Many subsribers process event parallel and asyncronously
		* *Push to SQS*: Services pull from SQS, when they become available
		* *Alert*: Notification triggered by event or threshold
* **Mobile Notifications** to mobile devices
	* Sends *push notifications* to iOS, Android, Fire OS, Windows and Baidu-based devices

<a name="26_2"></a>
## [↖](#top)[↑](#26_1)[↓](#26_3) Components
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
  * Messages are stored redundantly across multiple AZs

* *Amazon MQ* can send messages as well (to Apache ActiveMQ)

<a name="26_3"></a>
## [↖](#top)[↑](#26_2)[↓](#27) Limits
.|.
-|-
Subscibers per topic|10 mio

---

<a name="27"></a>
# [↖](#top)[↑](#26_3)[↓](#27_1) Elastic Transcoder

<a name="27_1"></a>
## [↖](#top)[↑](#27)[↓](#28) Overview

*Amazon Elastic Transcoder* is media transcoding in the cloud. It is designed to be a highly scalable,
easy to use and a cost effective way for developers and businesses to convert (or “transcode”)
media files from their source format into versions that will playback on devices like smartphones,
tablets and PCs.

---

<a name="28"></a>
# [↖](#top)[↑](#27_1)[↓](#28_1) API Gateway

<a name="28_1"></a>
## [↖](#top)[↑](#28)[↓](#29) Overview

*Amazon API Gateway* is a fully managed service that makes it easy for developers to create, publish,
maintain, monitor, and secure APIs at any scale. With a few clicks in the AWS Management Console,
you can create REST and WebSocket APIs that act as a “front door” for applications to access data,
business logic, or functionality from your backend services, such as workloads running on Amazon
Elastic Compute Cloud (Amazon EC2), code running on AWS Lambda, any web application, or real-time
communication applications.

* *API Caching*
  * Caches responses from internal endpoints for a specific time-to-live (TTL)

* *Scaling*
  * Happens transparently
  * Could also be throttled to prevent attacks

---

<a name="29"></a>
# [↖](#top)[↑](#28_1)[↓](#29_1) Kinesis

<a name="29_1"></a>
## [↖](#top)[↑](#29)[↓](#30) Overview

*Amazon Kinesis* makes it easy to collect, process, and analyze real-time, streaming data so you can
get timely insights and react quickly to new information. Amazon Kinesis offers key capabilities
to cost-effectively process streaming data at any scale, along with the flexibility to choose the
tools that best suit the requirements of your application. With Amazon Kinesis, you can ingest rea
-time data such as video, audio, application logs, website clickstreams, and IoT telemetry data
for machine learning, analytics, and other applications. Amazon Kinesis enables you to process and
analyze data as it arrives and respond instantly instead of having to wait until all your data is
collected before the processing can begin.

*Streaming Data* is data that is generated continuuously by thousands of data sources, which
typically send in the data records simulataneously, and in small sizes

* Core Services:
  * *Kinesis Streams* (*video*/*data*)
    * Data is stored in *Shards*, can have multiple shards per stream
    * The total stream capacity is sum of the capacities of the shard
    * Allows to retain data from 2h up to 7 days
    * Allows custom procesing of data
  * *Kinesis Firehose*
    * Similar to *Streams*, but more automated and fully managed
    * Simply ingests data into S3, RedShift or ElasticSearch
  * *Kinesis Analytics*
    * Allows to run SQL queries on data from Streams or Firehose


---

<a name="30"></a>
# [↖](#top)[↑](#29_1)[↓](#30_1) Elastic Map Reduce

<a name="30_1"></a>
## [↖](#top)[↑](#30)[↓](#31) Overview

*Amazon EMR* provides a managed Hadoop framework that makes it easy, fast, and cost-effective to
process vast amounts of data across dynamically scalable Amazon EC2 instances. You can also run
other popular distributed frameworks such as Apache Spark, HBase, Presto, and Flink in EMR, and
interact with data in other AWS data stores such as Amazon S3 and Amazon DynamoDB. EMR Notebooks,
based on the popular Jupyter Notebook, provide a development and collaboration environment for ad
hoc querying and exploratory analysis.

EMR securely and reliably handles a broad set of big data use cases, including log analysis, web
indexing, data transformations (ETL), machine learning, financial analysis, scientific simulation,
and bioinformatics.

---

<a name="31"></a>
# [↖](#top)[↑](#30_1)[↓](#31_1) Direct Connect

<a name="31_1"></a>
## [↖](#top)[↑](#31)[↓](#32) Overview
*AWS Direct Connect* is a cloud service solution that makes it easy to establish a *dedicated* network
connection from your premises to AWS. Using AWS Direct Connect, you can establish private
connectivity between AWS and your datacenter, office, or colocation environment, which in many
cases can reduce your network costs, increase bandwidth throughput, and provide a more consistent
network experience than Internet-based connections.

* Reduces bandwith costs
* Consistent network performance
* Compatible with all AWS services
* Private connectivity to your VPC
* Elastic

---

<a name="32"></a>
# [↖](#top)[↑](#31_1)[↓](#32_1) ECS

<a name="32_1"></a>
## [↖](#top)[↑](#32)[↓](#32_2) Overview
*Amazon Elastic Container Service* (Amazon ECS) is a highly scalable, fast, container management
service that makes it easy to run, stop, and manage Docker containers on a cluster. You can host
your cluster on a serverless infrastructure that is managed by Amazon ECS by launching your
services or tasks using the Fargate launch type. For more control you can host your tasks on a
cluster of Amazon Elastic Compute Cloud (Amazon EC2) instances that you manage by using the EC2
launch type.

<a name="32_2"></a>
## [↖](#top)[↑](#32_1)[↓](#33) Components

* **Task Definition**
  * The task definition is a text file, in JSON format, that describes one or more containers, up
    to a maximum of ten, that form your application
  * Specify various parameters, eg:
    * Containes to use
    * Port to be opened
    * Data volumes
* **Task**
  * A *task* is the instantiation of a task definition within a cluster
  * ECS allows to run and maintain a specified number of instances of a task definition
  * If a task should fail or stop, the ECS scheduler launches another instance of the task
    definition to replace it and to maintain the desired count of tasks in service
* **Service**
  * Runs and maintains a specified number of tasks simultaneously
* **Clusters**
  * Logical grouping of container instances that you can place tasks on

---

<a name="33"></a>
# [↖](#top)[↑](#32_2)[↓](#33_1) Workspaces

<a name="33_1"></a>
## [↖](#top)[↑](#33)[↓](#34) Overview
*Amazon WorkSpaces* is a managed, secure cloud desktop service. You can use Amazon WorkSpaces to
provision either Windows or Linux desktops in just a few minutes and quickly scale to provide
thousands of desktops to workers across the globe. You can pay either monthly or hourly, just for
the WorkSpaces you launch, which helps you save money when compared to traditional desktops and on
premises VDI solutions. Amazon WorkSpaces helps you eliminate the complexity in managing hardware
inventory, OS versions and patches, and Virtual Desktop Infrastructure (VDI), which helps simplify
your desktop delivery strategy. With Amazon WorkSpaces, your users get a fast, responsive desktop
of their choice that they can access anywhere, anytime, from any supported device.

* Windows 7 experience, provided by Windows Server 2008
* No AWS account required to log in

---

<a name="34"></a>
# [↖](#top)[↑](#33_1)[↓](#34_1) OpsWorks

<a name="34_1"></a>
## [↖](#top)[↑](#34)[↓](#35) Overview
* Orchestration services that uses Chef
* Components
  * *Stack*
  * *Layer*
  * *Instance*
  * *Application*
* Runs *recipes* to maintain a consitent state

---

<a name="35"></a>
# [↖](#top)[↑](#34_1)[↓](#35_1) AWS Organizations

<a name="35_1"></a>
## [↖](#top)[↑](#35)[↓](#35_2) Overview
*AWS Organizations* offers policy-based management for multiple AWS accounts. With Organizations,
you can create groups of accounts, automate account creation, apply and manage policies for those
groups. Organizations enables you to centrally manage policies across multiple accounts, without
requiring custom scripts and manual processes.

Using AWS Organizations, you can create Service Control Policies (SCPs) that centrally control AWS
service use across multiple AWS accounts. You can also use Organizations to help automate the
creation of new accounts through APIs. Organizations helps simplify the billing for multiple
accounts by enabling you to setup a single payment method for all the accounts in your
organization through consolidated billing. AWS Organizations is available to all AWS customers at
no additional charge.

* Benefits
  * Centrally manage policies across multiple accounts
  * Control access to AWS services
  * Automate AWS account creation and management
  * *Consolidated billing*
    * One *paying account* linked to many *linked accounts*
    * Pricing benefits (Volumes, Storage, Instances)

<a name="35_2"></a>
## [↖](#top)[↑](#35_1)[↓](#36) Limits:
.|.
-|-
Maximum linked accounts|20

TODO: Look at AWS Organization in root account

---

<a name="36"></a>
# [↖](#top)[↑](#35_2)[↓](#36_1) Resource Groups

<a name="36_1"></a>
## [↖](#top)[↑](#36)[↓](#37) Overview
* **Classic**
  * In AWS, a resource is an entity that you can work with. Examples include an Amazon EC2 instance,
    an AWS CloudFormation stack, and an Amazon S3 bucket. If you work with multiple resources, you
    might find it useful to manage them as a group rather than move from one AWS service to another
    for each task.
  * *Resource Groups* helps you do just that. By default, the AWS Management Console is organized by
    AWS service. But with the Resource Groups tool, you can create a custom console that organizes
    and consolidates information based on your project and the resources that you use. If you manage
    resources in multiple regions, you can create a resource group to view resources from
    different regions on the same page.
  * Global or per region
* **New**
  * Sits within System Manager
  * Per region
  * More control, allows automation and inspections.


---

<a name="37"></a>
# [↖](#top)[↑](#36_1)[↓](#37_1) The Well Architected Framework

<a name="37_1"></a>
## [↖](#top)[↑](#37)[↓](#37_2) Overview
* Security
* Reliability
* Performance Efficiency
* Cost Optimization
* Operational Excellence

<a name="37_2"></a>
## [↖](#top)[↑](#37_1)[↓](#37_3) Security
* Data protection
  * Encrypting and Protecting data at rest
  * Encrypting and Protecting data in transit (SSL)
* Privilege management
  * Protecting access to and use of root account credentials
  * Definining roles and responsibilities of human users
  * Limiting automated access of system users
  * How are you using keys and credentials?
* Infrastructure protection
  * How are you enforcing network and host-level boundaries?
  * How are you enforcing AWS service level protection?
  * How are you protecting the integrity of operating systems on instances?
* Detective Controls
  * How are you capturing and analysing AWS logs?

<a name="37_3"></a>
## [↖](#top)[↑](#37_2)[↓](#37_4) Reliability
* Foundations
  * How do you manage AWS service limits for your account?
  * How are you planning your network topology?
  * Do you have an escalation path to deal with technical issues?
* Change managements
  * How does your system adopt to changes in demand?
  * How are you monitoring AWS resources?
  * How are you executing change managements?
* Failure management
  * How are you backing up your data?
  * How does your system withstand component failures?
  * How are you planning for recovery?

<a name="37_4"></a>
## [↖](#top)[↑](#37_3)[↓](#37_5) Performance Efficiency
* Compute
  * How do you select the appropriate instance type for your system?
  * How do you ensure to continue to use the most appropriate instance type?
  * How do you monitor your instances post launch?
  * How do you ensure the quantity of your instances matches demand
* Storage
  * How do you select the appropriate storage solution for your system?
  * How do you ensure to continue to use the most appropriate storage solution?
  * How do you monitor your storage solution post launch?
  * How do you ensure the quantity of your storage solution matches demand
* Databases
  * How do you select the appropriate database solution for your system?
  * How do you ensure to continue to use the most appropriate database solution?
  * How do you monitor your database solution post launch?
  * How do you ensure the quantity of your database solution matches demand
* Space-time trade-off
  * How do you select the appropriate proximity and caching solution for your system?
  * How do you ensure to continue to use the most appropriate proximity and caching solution?
  * How do you monitor your proximity and caching solution post launch?
  * How do you ensure the quantity of your proximity and caching solution matches demand

<a name="37_5"></a>
## [↖](#top)[↑](#37_4)[↓](#37_6) Cost efficiency
* Matched supply and demand
  * How do you make sure your capacity matches your demand, but does not substantially exceed it?
  * How are you optimizing your usage of AWS services?
* Cost-effective resources
  * Have you selected the appropriate resource type to meet your cost targets?
  * Have you selected the appropriate pricing model to meet your cost targets?
  * Are there managed services that you can use to improve your ROI?
* Expenditure awareness
  * What access control and procedure do you have in place to govern AWS costs?
  * How are you monitoring usage and spending?
  * How do you decommision or stop resources you no longer need?
* Optimizing over time
  * How do you manage and/or consider the adoption of new services?

<a name="37_6"></a>
## [↖](#top)[↑](#37_5)[↓](#) Operational excellence
* Preparation
  * What best practices of cloud oprations are you using
  * How are you doing configuration management for your workload?
* Operations
  * How are you evolving your workload while minimizing the impact of change?
  * How are you monitoring your workload?
* Responses
  * How do you respond to an unplanned operational event?
  * How is escalation managed when responding to an unplanned operational event?g

