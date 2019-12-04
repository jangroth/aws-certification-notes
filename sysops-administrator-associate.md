[toc_start]::
<a name="top"></a>
---
* [AWS-SysOps-Administrator-Associate](#1)
* [Monitoring And Metrics](#2)
  * [Virtualization Types](#2_1)
  * [EC2 Instance Types](#2_2)
  * [EC2 Monitoring](#2_3)
  * [EBS Monitoring](#2_4)
  * [EFS Monitoring](#2_5)
  * [CloudWatch](#2_6)
* [Costs](#3)
  * [Consolidated Billing](#3_1)
  * [Billing Metrics & Alarms](#3_2)
  * [Costs Optimization](#3_3)
  * [Cost Explorer](#3_4)
* [High Availability](#4)
  * [Scalability & Elasticity Fundamentals](#4_1)
  * [Reserved Instances](#4_2)
  * [Autoscaling vs Resizing](#4_3)
  * [Load Balancers](#4_4)
  * [RDS HA](#4_5)
  * [HA for IP-based Applications](#4_6)
  * [HA/Fault Tolerance for Bastion Hosts](#4_7)
* [Analysis](#5)
  * [Optimize the environment to ensure maximum performance](#5_1)
  * [Identify Performance Bottlenecks and Implement Remedies](#5_2)
  * [Identify Potential Issues on a Given Application Deployment](#5_3)
* [OpsWorks](#6)
  * [Overview and components](#6_1)
  * [Cloudformation](#6_2)
* [Backups & Recovery](#7)
  * [AWS Services with automated backups](#7_1)
  * [Disaster Recovery Scenarios](#7_2)
  * [Storing log files and backups](#7_3)
* [Security](#8)
  * [Implement and Manage Security Policies](#8_1)
  * [Ensure Data Integrity and Access Controls when Using the AWS Platform](#8_2)
  * [Share responsibility model](#8_3)
  * [AWS and IT Audits](#8_4)
* [Networking](#9)
  * [Route53 Routing Policies](#9_1)
  * [VPC Essentials](#9_2)
  * [Limits:](#9_3)
* [Etc](#10)
  * [Accessing the OS](#10_1)
  * [SQS](#10_2)
  * [DynamoDb](#10_3)
---
[toc_end]::
<a name="1"></a>
# [↖](#top)[↑](#)[↓](#2) SysOps Administrator Associate
> 5/2018 - 9/2018

---

<a name="2"></a>
# [↖](#top)[↑](#1)[↓](#2_1) Monitoring And Metrics

<a name="2_1"></a>
## [↖](#top)[↑](#2)[↓](#2_2) Virtualization Types

Linux Amazon Machine Images use one of two types of virtualization:

AMI|Type|Effect
-|-|-
**PV**|Paravirtual|Historically better performance than HVM, but no longer the case
**HVM**|Hardware virtual machine|More modern, same or better performance than PV

<a name="2_2"></a>
## [↖](#top)[↑](#2_1)[↓](#2_3) EC2 Instance Types

**General Purpose**|Balance of computer, memory and networking
-|-
**M5**<br/>(2017)|* Require HVM AMIs<br/> * Instance store via EBS or NVMe SSD (physically connected to to the host server)
**M4**<br/>(2015)|* Allows *enhanced networking*<br/> * EBS-optimized
**M3**<br/>(2012)|* SSD (instance) store
**T3**<br/>(2018)|* 30% better price performance
**T2**<br/>(2014)|* Intented for workloads that do not use the full CPU constantly (e.g. web server)<br/> * Allows *burstable performance* <br/>* Burst credits allow to 'burst' past the baseline performance up to 100%<br/> * 1 credit = 100% load per core per minute<br/> * Credits are earned per hour, expire after 24h<br/> * EBS storage only

**Compute optimized**|Lowest prize for *compute* performance
-|-
**C5**<br/>(2016)| * Intel Skylake<br/> * Use Nitro, Amazon’s lightweight hardware accelerated hypervisor<br/> * Better performance and pricing than C4
**C4**<br/>(2015)| * Intel Haswell<br/> * Optimized for EC2<br/> * Allows *enhanced networking* and *clustering*<br/> * EBS-optimized
**C3**<br/>(2013)| * SSD (instance) store<br/> * Allows *enhanced networking* and *clustering*

**Memory optimized**|Lowest prize for *memory* performance
-|-
**Z1d**<br/>(2018)| * Offer both high compute capacity and a high memory footprint<br/> * Ideal for workloads with high per-core licensing costs
**X1**<br/>(2016)| * One of the lowest price per GiB of RAM<br/> * SSD storage and EBS-optimized by default<br/> * **X1e** has even more RAM
**R5**<br/>(2018)| * Use Nitro, Amazon’s lightweight hardware accelerated hypervisor
**R4**<br/>(2016)| * Improved networking and EBS performance
**R3**<br/>(2014)| * SSD (instance) store<br/> * High memory capacity<br/> * Allows *enhanced networking*

**GPU optimized**|.
-|-
**P3**<br/>(2017)| * Faster than P2
**P2**<br/>(2016)| * Intended for general-purpose GPU compute applications
**G3**<br/>(2017)| * Optimized for graphics-intensive applications<br/>* Faster then G2
**G2**<br/>(2013)| * High frequency processors<br/> * High-performce NVIDIA GPUs


**Storage optimized**|Very fast SSD-backed instance storage optimized for high random I/O and high IOPS
-|-
**H1**<br/>(2017)| * HDD-based local storage<br/> * deliver high disk throughput<br/> * Balance of compute and memory
**I3**<br/>(2016)| * (NVMe) SSD-backed instance storage optimized for low latency<br/> * very high random I/O performance
**D2**<br/>(2015)| * Lowest price per disk throughput performance
**I2**<br/>(2013)| * SSD (instance) store<br/> * Allows *enhanced networking*<br/> * Supports *TRIM* (more efficient SSD operations)

**RDS instance types**|Optimized to fit different relational database use cases
-|-
**db.**|General purpose, memory optimized, burstable performance

.*

<a name="2_3"></a>
## [↖](#top)[↑](#2_2)[↓](#2_3_1) EC2 Monitoring

<a name="2_3_1"></a>
### EC2 Status Checks
* AWS performs automated checks on every running EC2 instance
* Performed every minute
* Each returns a pass or a fail status

**System Status Check**
* Loss of network connectivity
* Loss of system power
* Hardware/software issues on physical host
* Solution
  * Stop and start instance
  * Terminate and re-launch instance
  * Contact AWS
* Can configure for *auto-recovery*
  * Instance will be rebooted and retain instance id, (e)ip address, EBS volumes et al

**Instance Status Check**
* Failed system status check
* Network/startup configuration issues
* Memory/disk problems
* Kernel compatability issues
* Solution
  * Fix problem
  * Stop and start instance
  * Terminate and re-launch instance, potentially with more memory/network/disk/...

<a name="2_4"></a>
## [↖](#top)[↑](#2_3_1)[↓](#2_4_1) EBS Monitoring

<a name="2_4_1"></a>
### EBS Status Checks
* Run every 5 minutes
  * `insufficient data` if checks a running
  * `ok` if all checks pass
  * `warning` typically has to do with performance **degradation** from provisioned IOPS
  * `impaired` is a check fails, eg. the volume is **stalled** or not available

* If Amazon EBS finds that data on a volume might be inconsistent, it disables I/O to that volume.
  * Changes status to `impaired`
  * This behaviour can be disabled

<a name="2_4_2"></a>
### EBS Performance Essentials
**IOPS** (Input/Output Operations Per Second) is a common performance measurement used to benchmark
computer storage devices like hard disk drives (HDD), solid state drives (SSD), and storage area
networks (SAN).
* I/O size is capped at 256 KiB for SSD volumes and 1,024 KiB for HDD volumes because SSD volumes handle
  small or random I/O much more efficiently than HDD volumes.
* SSDs deliver constant performance for both random and sequential I/O
* HDDs have optimal performance for large and sequential I/O
* HDD can deliver more throughput put drastically less IOPS

.|`gp2`|`io1`|`st1`|`sc1`
-|-|-|-|-
Volume type|General purpose SSD|Provisioned IOPS SSD|Throughput optimized HDD|Cold HDD
Purpose|Balances price and performance|For mission-critical low-latency or high-throughput workloads|Low cost HDD volume designed for frequently accessed, throughput-intensive workloads |Lowest cost HDD volume designed for less frequently accessed workloads
Volume Size|1 GiB - 16 TiB|4 GiB - 16 TiB|500 GiB - 16 TiB|500 GiB - 16 TiB
Max. IOPS(1)/Volume|10,000|32,000|500|250
Max. Throughput/Volume|160 MiB/s|500 MiB/s|500 MiB/s|250 MiB/s
IOPS|* 3 IOPS per GB (larger volume means more IOPS)<br/>* 100 IOPS <-> 10,000 IOPS<br/>* Can burst to 3,000 IOPS if volume size is < 1TB<br/>* Requires credits that are acquired per 3 IOPS/GB/second<br/>* Max 5.4 miilion credit (also intitial value), enough for 3,000 IOPS for 30min<br/>* Running out of credits reverts volume back to baseline performance|* 30 IOPS per GB (larger volume means more IOPS), up to 20,000<br/>* Does not burst, delivers consistent IOPS rate instead|.|.

> (1) gp2/io1 based on 16 KiB I/O size, st1/sc1 based on 1 MiB I/O size

* Using *EBS optimized* instances guarantees optimal networking between EBS and EC2
* Pre-warming/intialization
  * No longer needed for new EBS volumes
  * Storage blocks on volumes restored from snapshots do need to be initialized (read from)

<a name="2_5"></a>
## [↖](#top)[↑](#2_4_2)[↓](#2_5_1) EFS Monitoring

* Two throughput modes to choose from for your file system
  * **Bursting** Throughput - throughput on Amazon EFS scales as your file system grows
  * **Provisioned** Throughput - you can instantly provision the throughput of your file system (in MiB/s) independent of the amount of data stored.

<a name="2_5_1"></a>
### Performance comparison
.|Amazon EFS|Amazon EBS Provisioned IOPS (`io1`)
-|-|-
Per-operation latency|Low, consistent latency.|Lowest, consistent latency.
Throughput scale|10+ GB per second.|Up to 2 GB per second.

<a name="2_5_2"></a>
### Storage Characteristics Comparison

.|Amazon EFS|Amazon EBS Provisioned IOPS
-|-|-
Availability and durability|Data is stored redundantly across multiple AZs.|Data is stored redundantly in a single AZ.
Access|Up to thousands of Amazon EC2 instances, from multiple AZs, can connect concurrently to a file system.|A single Amazon EC2 instance in a single AZ can connect to a file system.
Use cases|Big data and analytics, media processing workflows, content management, web serving, and home directories.|Boot volumes, transactional and NoSQL databases, data warehousing, and ETL.

<a name="2_5_3"></a>
### S3 vs EFS vs EBS Comparison

Amazon S3|Amazon EBS|Amazon EFS
-|-|-
Can be publicly accessible|Accessible only via the given EC2 Machine|Accessible via several EC2 machines and AWS services
Web interface|File System interface|Web and file system interface
Object Storage|Block Storage|Object storage
Scalable|Hardly scalable|Scalable
Slower than EBS and EFS|Faster than S3 and EFS|Faster than S3, slower than EBS
Good for storing backups|Is meant to be EC2 drive|Good for shareable applications and workloads

<a name="2_6"></a>
## [↖](#top)[↑](#2_5_3)[↓](#2_6_1) CloudWatch
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

<a name="2_6_1"></a>
### Key metrics for EC2

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

<a name="2_6_2"></a>
### Key metrics for EBS
Metric|Effect
-|-
`VolumeReadBytes`,`VolumeWriteBytes`|`sum` reports total bytes transferred, `average` also useful
`VolumeReadOps`,`VolumeWriteOps`|total number of IO operations
`VolumeQueueLength`|Number of read/write operation requests waiting to finish
`VolumeTotalReadTime`,`VolumeTotalWriteTime`|Total number of seconds spent by all operations in a given time
`VolumeThroughputPercentage`|Percentage of IOPS that was achieved out of total provisioned IOPS
`VolumeConsumedReadWriteOps`|Total amount of r/w operations consumed within a specific time period

* Can **not** monitor **disk usage percentage**

<a name="2_6_3"></a>
### Key metrics for EFS
Metric|Effect
-|-
`BurstCreditBalance`|The number of burst credits that a file system has.
`ClientConnections`|The number of client connections to a file system.
`DataReadIOBytes`,`DataWriteIOBytes`|The number of bytes for each file system read(write) operation.
`MetadataIOBytes`|The number of bytes for each metadata operation.
`PercentIOLimit`|Shows how close a file system is to reaching the I/O limit of the General Purpose performance mode.
`PermittedThroughput`|The maximum amount of throughput a file system is allowed.
`TotalIOBytes`|The number of bytes for each file system operation, including data read, data write, and metadata operations.

<a name="2_6_4"></a>
### Key metrics for ELB (classic load balancer)
Metric|Effect
-|-
`Latency`|Time it takes to receive an response. Measure `max` and `average`
`BackendConnectionErrorr`|Number of not successfully established connections to registered instances, measure `sum` and look at difference between `min` and `max`
`SurgeQueueLength`|Total number of request waiting to get routed, look at `max` and `average`
`SpilloverCount`|Dropped requests because of exceeded surge queue. Look at `sum`
`HTTPCode_ELB_3XX_Count`<br/>`HTTPCode_ELB_4XX_Count`<br/>`HTTPCode_ELB_5XX_Count`|The number of HTTP XXX server error codes that originate from the *load balancer*. This count does *not* include any response codes generated by the targets.
`RequestCount`|Number of completed requests
`HealthyHostCount`,`UnhealthyHostCount`|Self explainatory

* In case of sudden and very large increases in traffic it's possible to contact AWS and have them
'pre-warm' the *ELB*.

> spillover and surge queue give an indication of the ELB being overloaded

* Typically this means that the backend system cannot process requests as fast as they are coming in
  * Ideally load balance into an autoscaling group.

<a name="2_6_5"></a>
### Key metrics for ALB (active load balancer)
Metric|Effect
-|-
`RequestCount`|Number of completed requests
`HealthyHostCount`,`UnhealthyHostCount`|Self explainatory
`TargetResponseTime`|The time elapsed after the request leaves the load balancer until a response from the target is received.
`HTTPCode_ELB_3XX_Count`<br/>`HTTPCode_ELB_4XX_Count`<br/>`HTTPCode_ELB_5XX_Count`|The number of HTTP XXX server error codes that originate from the *load balancer*. This count does *not* include any response codes generated by the targets.

<a name="2_6_6"></a>
### Key metrics for NLB (network load balancer)
Metric|Effect
-|-
`processedbyte `|The total number of bytes processed by the load balancer, including TCP/IP headers.
`tcp_client_reset_count`|the total number of reset (rst) packets sent from a client to a target.
`tcp_elb_reset_count`|the total number of reset (rst) packets generated by the load balancer.
`tcp_target_reset_coun`|the total number of reset (rst) packets sent from a target to a client.

<a name="2_6_7"></a>
### Key metrics for elasticache
Supports *memcached* and *redis*

Metric|**memcached**|**redis**
-|-|-
.|Designed for simplicity|Supports a much richer set of features. can be backed up if in *cluster* mode
`cpu utilization`|* multithreaded<br/>* stay under 90%/#cores<br/>* -> increase # read replicase or use larger cache instance|* single threaded<br/>* stay under 90%<br/>* -> increase size of node or add more nodes
`evictions`|* -> increase size or add nodes to cluster|* -> increase node size
`concurrent connections`|* -> check application logic|* -> check application logic
`swap usage`|* avoid swapping<br/> -> increase `memcached_connections_overhead`|avoid swapping<br/>* -> increase node size<br/>* -> increase `memory connection overhead` (will decrease memory available for cache)

.*

<a name="2_6_8"></a>
### Key metrics for RDS
Metric|Effect
-|-
`CPUUtilization`|Percentage of CPU utilization
`DatabaseConnections`|Number of connections that we have at a given point in time
`DiskQueueDepth`|Number of read/write requests waiting to access the disk
`FreeableMemory`|Amount of available RAM
`FreeStorageSpace`|Amount of available storage space
`SwapUsage`|When data is stored in memory on disk
`Increase`|In this usually has to do with running out of available RAMReadIOPS/WriteIOPS
`IOPS`|Represent the number of I/O operations completed per secondIf we don’t have enough IOPS, performance will slow down
`ReadLatency/WriteLatency`|* Average amount of time taken per disk I/O operation (input/output)<br/>* High latency can be solved with more IOPSReadThroughput/WriteThroughput<br/>* `Average` is number of bytes read or written to or from disk per second

.*

* Also look at *RDS Events*

---

<a name="3"></a>
# [↖](#top)[↑](#2_6_8)[↓](#3_1) Costs

<a name="3_1"></a>
## [↖](#top)[↑](#3)[↓](#3_2) Consolidated Billing
Set up a **billing account** to pay for multiple **linked accounts** at the same time.

* Allows for **consolidated billing**. Does *not* give IAM visibility into linked accounts.
* Enables **volume discounts** across linked accounts.
* If one account uses *reserved instances*, other accounts running on  similar *on demand* instances
will be billed under the reserved instance price. Similar for *RDS* instances.
* All *credits* earned while linked will be applied to consolidated bill.

Limits:
* Up to 20 linked accounts

<a name="3_2"></a>
## [↖](#top)[↑](#3_1)[↓](#3_3) Billing Metrics & Alarms
* Only shows metrics of services that have been used.
* Set up *billing alarms* based on billing metrics.
  * *Overall* billing alarm, or *service-specific* alarms
  * Can still be account-specific, even with consolidated billing

<a name="3_3"></a>
## [↖](#top)[↑](#3_2)[↓](#3_4) Costs Optimization
* Purchase **EC2 Reserved Instances**
  * Commit for 1-3 years and get a discount
* Minimize the number of running instances
  * Set up *CloudWatch* alarms to spin down underutilized instances
  * Find balance between acceptable downtime & costs to eleminate this downtime
* Remove unused **Load Balancers**
* Look for idle (unattached) **EBS** volumes
  * Delete unused volumes
    * Take a *snapshot* to keep the data
  * Downsize volumes that aren't near full capacity
  * Look for over-provisoned **IOPS**
* Look for unassociated **Elastic IP** addresses
* Look for idle **RDS** instances
  * Check for 0 connections

<a name="3_4"></a>
## [↖](#top)[↑](#3_3)[↓](#4) Cost Explorer
* Costs per *time frame* per *service*, various grouping and filtering options
* Provides forecasts
* **Pricing API** allows to download pricing information for specific services

---

<a name="4"></a>
# [↖](#top)[↑](#3_4)[↓](#4_1) High Availability

<a name="4_1"></a>
## [↖](#top)[↑](#4)[↓](#4_2) Scalability & Elasticity Fundamentals
* Pay only for *what* you need *when* you need it
  * Define minimum capacity
  * Define what needs to stretch out

.|**Elasticity**|**Scalability**
-|-|-
.|*Scaling up/down on demand*|*Scaling for growth in order to meet long term requirements<br/>typically does not focus on shrinking back*
*DynamoDb*|Can provision more or less throughput|Stores as much data as we like, scales transparently
*EC2*|Use autoscaling|More instances or bigger instance types
*RDS*|./.|Bigger instances, more read replicas

<a name="4_2"></a>
## [↖](#top)[↑](#4_1)[↓](#4_3) Reserved Instances
* *Reserve* instances for a specific period of time
  * *Standard* reserved instances (fixed instance type)
  * *Convertible* reserved instances (can be exchanged against another convertible instance type)
  * *Scheduled* reserved instances (purchased by the hour on a set schedule with a set instance type)
* Up to 50% cheaper than a *fully utilized* on-demand instance (because we commit upfront to a certain usage)
* Guarantees to *not* run into '*insufficent instance capacity*' issues if AWS is unable to provision instances in that AZ
* Can resell reserved capacity on *Reserved Instance Marketplace*
* Available for:
  * EC2
  * RDS (*reserved instances*)
  * DynamoDB (*reserved capacity*)
  * ElastiCache (*reserved nodes*)
  * CloudFront (*reserved capacity*)
  * Elastic MapReduce (*reserved EC2 instances*)
  * ECR (*reserved EC2 instances*)

<a name="4_3"></a>
## [↖](#top)[↑](#4_2)[↓](#4_4) Autoscaling vs Resizing
* **Auto Scaling** distributes load across multiple instances
  * *Scheduled Scaling* allows to scale or shrink on a schedule
  * Relativly complex to set up
  * Applications need to be designed to benefit from multiple instances
  * Components
    * *Launch Configuration*
    * *Autoscaling Group*
    * *Scaling Policy*
    * *Cloudwatch Alarms*

* **Changing instance size** increases/decreases available resources to the running application
  * *EBS* backed instances need to be stopped before resizing
  * *Instance storage* need to be migrated across
  * Not as flexible as auto scaling. Not elastic
  * Within an autoscaling group the to-be-resized instance might be treated as unhealthy

<a name="4_4"></a>
## [↖](#top)[↑](#4_3)[↓](#4_4_1) Load Balancers

.|**ALB**|**NLB**|**ELB**
-|-|-|-
.|Active Load Balancer|Network Load Balancer|Classic Load Balancer
Layer|7 (application layer)|4 (transport layer)|EC2-classic network (deprecated)
Protocoll|HTTP, HTTPS|TCP|TCP, SSL, HTTP, HTTPS
Health checks|✔|✔|✔
Cloudwatch metrics|✔|✔|✔
Logging|✔|✔|✔
Zone failover|✔|✔|✔
Connection draining|✔|✔|✔
Load balancing to different ports on the same instance|✔|✔|.
WebSockets|✔|✔|.
IP Addresses as targets|✔|✔|.
Load balancing deletion protection|✔|✔|.
Path-based routing|✔|.|.
Host-based routing|✔|.|.
Native http/2|✔|.|.
Configurable idle connection timeout|✔|.|✔
Cross zone load-balancing|✔|✔|✔
SSl-offloading|✔|.|✔
Server-name indication|✔|.|✔
Sticky-sessions|✔|.|✔
Backend server encryption|✔|.|✔
Static IP|.|✔|.
Elastic IP|.|✔|.
Preserve source IP address|.|✔|.
Resource-based IAM permissions|✔|✔|✔
Tag-based IAM permissions|✔|✔|.
Slow start|✔|.|.
User authenticaion|✔|.|.
Redirects|✔|.|.
Fixed responses|✔|.|.

<a name="4_4_1"></a>
### Elastic Load Balancer ('Classic LB')

<a name="4_4_2"></a>
### Overview
* *External* load balancer
  * Public facing
  * Often used to distribute load between web servers
  * Provides public DNS host name
* *Internal* load balancer
  * Often used to Distribute load between backend servers
  * Provides internal DNS host name
* Configure (in AWS console)
  * Internal and external load balancer
  * Subnets for each AZ that traffic should be routed to
    * Can route into private subnets
  * Cross-zone load balancing
  * Connection draining (maximum time for the load balancer to keep connections alive before reporting the instance as
    de-registered)

<a name="4_4_3"></a>
### Sticky Sessions
* Need to make sure that session is maintained between instances
  * Load Balancer generated stickiness (*duration based* session stickiness)
  * Application generated stickiness (*application based* session stickiness)
  * For HA, use *ElastiCache* to persist and share session state. So maintaining
    stickiness doesn't matter any more

<a name="4_5"></a>
## [↖](#top)[↑](#4_4_3)[↓](#4_6) RDS HA
* Create *subnets* in different AZs
* Create *subnet group* in RDS dashboard
  * Collection of subnets (typically private) in a VPC that is desgnated for DB instances
  * Should have subnets in at least two Availability Zones in a given region
* Configure RDS for **multi-AZ-deployments** and turn replication on
  * Keeps a *synchronous* standby replica in a different AZ
    * Recommendation is use of Provisioned IOPS
  * Automatic failover in case of planned or unplanned outage of the first AZ
    * Most likely still has downtime
    * Can *force* failover by *rebooting*
  * Other benefits
    * Patching
    * Backups
  * *Aurora* can replicate accross 3 AZs
* Failover process is automated
  * AWS detects an issue and starts the failover process
  * DNS records are modified to point to the standby instance
  * Application re-establishes existing DB connections

<a name="4_6"></a>
## [↖](#top)[↑](#4_5)[↓](#4_7) HA for IP-based Applications
* If the application requires specific IPs (that are hardcoded somewhere), autoscaling cannot be used
* Use *Elastic IP* and standby instances in different AZs instead
  * Cannot use Elastic IP across different regions though
  * Scale by increasing instance size (vertical scaling)

<a name="4_7"></a>
## [↖](#top)[↑](#4_6)[↓](#5) HA/Fault Tolerance for Bastion Hosts
* Assign Elastic IP to bastion host in AZ 1
  * This IP can also be whitelisted to comply with corporate regulations
* Have another instance on standby in different AZ
* Could be in *ASG* (min/max 1), so that it gets immediately replaced
* Place 2 instances behind ELB and enable *SSH Keep Alive*
* Place 1 instance behind ELB, configure *auto recovery*

---

<a name="5"></a>
# [↖](#top)[↑](#4_7)[↓](#5_1) Analysis

<a name="5_1"></a>
## [↖](#top)[↑](#5)[↓](#5_1_1) Optimize the environment to ensure maximum performance

<a name="5_1_1"></a>
### Offloading database workload
* Using **read replicas**
  * Read queries are routed to *read replicas*, reducing load on primary db instance
    (*source instance*)
    * Table indexes can be created on read replicas directly (and not on the master)
    * Some use cases (e.g. data analytics) can be performed exclusively against read replicas
  * To create read replicas, AWS initally creates a snapshot of the source instance
    * Multi-AZ failover instance (if enabled) is used for snapshotting
    * After that all read queries are then *asynchronously* copied to read replica
    * Implies data latency, which typically is acceptable.
      * `ReplicaLag` can be monitored and *Cloudwatch* alarms can be configured
  * *Read replicas* are **not** the same as *multi-AZ failover* instances which
    * are *synchronously* updated
    * are designed to handle failover
    * don't receive any load unless failover actually happens
  * Often it is beneficial to have both read replicas and multi-AZ failover instances
    * Read replicas themselves can not use the Multi-AZ feature
  * A single master can have **up to 5** read replicas
    * Can be in different regions

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
  * Useful for database sharding, could create replicas for each shard

<a name="5_1_2"></a>
### Looking at EBS volumes
* EBS *pre-warming*
  * Used to be required for maximum performance
  * Performance is reduced the very first time each block is accessed
  * Has been renamed to *initialization* and is no longer required if new EBS volumes are used
  * Still required for volumes that are restored from snapshots
    * Storage blocks must be initialized (pulled down from Amazon S3 and written to the volume)
    * Use `dd` or `fio` to *read* from every block
    * Only required if performance matters, obviously

<a name="5_1_3"></a>
### Prewarming ELBs
* ELB is designed to increase its resource capacity gradually
* Prevents `http 503` (ELB cannot handle anymore requests)
* Can contact AWS to `pre-warm` ELB
  * This should not really be required. Maybe if TV ads are running or so.
  * Use load testing tools to get a rough estimate of what the current ELB can handle
    * Increase at a rate no more than 50% per 5min.

<a name="5_2"></a>
## [↖](#top)[↑](#5_1_3)[↓](#5_2_1) Identify Performance Bottlenecks and Implement Remedies

<a name="5_2_1"></a>
### Resizing or changing EBS root volumes
* If EBS is at capacity
  * Either upgrade volume size to increase the amount of IOPS available
  * Or switch to provisiones IOPS volumes (`io1`)
* Resizing
  * Create snapshot of EBS volume first
    * Incrementally stored on S3
    * Can continue to use EBS volume while the snapshot is taking place
  * Create new volume from snapshot
  * Stop instance
  * Attach new volume

<a name="5_2_2"></a>
### Setting up certificates for Elastic Load Balancers
* Offloading overhead from the instances behind the ELB
  * Create ELB and configure https
  * Certificate from
    * ACM (AWS managed)
    * IAM (for external certificiates)
    * Upload directly

<a name="5_2_3"></a>
### Network bottlenecks
* Primary network bottlenecks
  * EC2 instances
    * Instances in different AZs or regions
    * Different instance types get different bandwith capacities
      * No absolute numbers communicated by AWS though
    * Not using *enhanced network capabilities* (not supported by some instance types)
    * Check for performance issues with` iperf3` (github)
      * Measures performance for ip-based networks
    * Use VPC Peering to create a reliable connection
      * No single point of failure
  * Connection to on-prem networks
    * Use `Direct Connect`

<a name="5_3"></a>
## [↖](#top)[↑](#5_2_3)[↓](#5_3_1) Identify Potential Issues on a Given Application Deployment

<a name="5_3_1"></a>
### EBS Root Devices on Terminated Instances - Ensuring Data Durability
* *EBS root volumes* will be deleted on instance termination as per default option
  * Could create snapshot before termination to backup data
  * Could change default settings
* *Instance store root volumes* will be left untouched on instance termination

<a name="5_3_2"></a>
### Troubleshooting Auto Scaling Issues
* Attempting to use wrong subnet
* AZ no longer available or supported (outage)
* Security group does not exist
* Associated keypair does not exist
* Auto scaling configuration is not working correctly
* Instance type specification does not exist in that AZ
* Auto scaling is not enabled on that subnet
* Invalid EBS device mapping
* Attempt to attach EBS block device to instance-store AMI
* AMI issues
* Attempt to use *placement groups* with instance types that don't support that
* AWS running out of capacity in that AZ
* If an instance is stopped, e.g. for updating it, autoscaling will consider it unhealthy and
  terminate - restart it. Need to suspend autoscaling first.

---

<a name="6"></a>
# [↖](#top)[↑](#5_3_2)[↓](#6_1) OpsWorks

<a name="6_1"></a>
## [↖](#top)[↑](#6)[↓](#6_1_1) Overview and components
* Declarative desired state engine
  * Automate, monitor and maintain deployments
* **Cookbooks** define **recipes**
* AWS' implementation of *Chef*
	* Original Chef
	* AWS-bespoke orchestration components
* Components
	* **Stack**
    * Set of resources that is managed as a group
		* Whole service stack
	* **Layer**
    * Represent and configure components of a stack
		* E.g. loadbalancer layer, app layer, db layer
		* Share common configuration elements
	* **Instance**
		* Units of compute within the platform
    * Must be associated with at least one layer
    * Can run
      * 24/7
      * Load-based
      * Time-based
	* **Application**
		* Applications that are deployed on one or more instances
    * Deployed through source code repo or S3
* Recipes
  * Created in ruby, used to customize different layers
  * Run at stack lifecycle events
    * `setup`
      * *Instance* has finished booting
    * `configure`
      * *Instance* enters or leaves the `online` state
      * *Elastic IP* is associated or disassociated
      * *Load balancer* is attached or detached
      * Event is executed on *all* instances, not only the impacted one
    * `deploy`
      * *Deploy command* is run on an instance
    * `undeploy`
      * *Undeploy command* is run on an instance
      * *App* is deleted
    * `shutdown`
      * When *instance* is shutdown, before termination
      * Allows cleanup
* Under the hood
	* *OpsWorks* **agent**
		* Configuration of machines
	* *OpsWorks* **automation engine**
		* *Create*, *update* & *delete* of various AWS components
		* Handles *loadbalancing*, *autoscaling* and *autohealing*
		* Supports *lifecycle* events

<a name="6_1_1"></a>
### BerkShelf
* Addresses an *OpsWorks* shortcoming from old versions - only one repository for recipes
* Was added in *OpsWorks* 11.10 and allows to install cookbooks from many repositories

TODO: Quickstart OpsWorks

<a name="6_2"></a>
## [↖](#top)[↑](#6_1_1)[↓](#6_2_1) Cloudformation

<a name="6_2_1"></a>
### Overview
* Allows to create and provision **resources** in a reusable **template** fashion
	* A *CloudFormation* template is a `JSON` or `YAML` formatted text file
* Related resources are managed in a single unit called a **stack**
	* Controls lifecycle of managed resources
	* All the resources in a stack are defined by the stack's *CloudFormation* template
	* Stack has `name` & `id`
* Two ways to update a stack
	* *Direct update*
		* Directly applies changes (if any)
	* *Change set*
		* Summary of proposed changes, can be applied or rejected
* Will **rollback** stack if it fails to create (can be disabled via API/console)
* A **stack policy** is an *IAM*-style policy statements that governs who can do what

<a name="6_2_2"></a>
### Templates
* `AWSTemplateFormatVersion`
* `Description`
* `Metadata`
	* Details about the template
* `Parameters`
	* Values to pass in right before template creation
		* Type
			* `String`, `Number`, `List`, `CommaDelimitedList`
			* AWS-specific types like `AWS::EC2::KeyPair::KeyName`
		* Description
		* Default Value
		* Allowed Values
		* Allowed Pattern
			* Validation per *regular expression*
		* MinLength/MaxLength
		* MinValue/MaxValue
	* Problem:
		* Usage of parameters *might* make it hard to instantiate stacks without human interaction
		* *CloudFormation* is able to auto-generate many resources attributes, e.g. name
* `Mappings`
	* Maps keys to values (eg different values for different regions)
* `Conditions`
	* Check values before deciding what to do
* `Resources`
	* Creates resources. Only mandatory section in a template.
	* Can have `Condition` element to toggle creation
* `Outputs`
	* Values to be exposed from the console or from API calls.
	* Can be used in a different stack (*cross stack references*)
	* Can be:
		* Constructed value
		* Parameter reference
		* Pseudo parameter
		* Output from a function like `fn::getAtt` or `Ref`

<a name="6_2_3"></a>
### Intrinsic Functions
* Used to pass in values that are not available until runtime
* Usable in `resource` properties, `metadata` attributes, and `update policy` attributes (auto-scaling)
* `Ref`
	* Returns the *default* value of the specified parameter or resource, usually instance id
* `Fn::GetAtt`
	* Returns the value of an attribute from an object, either the default or the specified attribute
	* Object is either from the same or a nested template
* `Fn::Join`
	* Joins a set of values into a single value separated by the specified delimiter
* `Fn::Sub`
	* Substitutes variables in an input string with values that you specify
* `Fn::FindInMap`
	* Returns the value corresponding to keys in a two-level map that is declared in the *Mappings*
	section
* `Fn::Select`
	* Returns a single object from a list of objects by index
* `Fn::Base64`
	* Provides encoding, converts from plain text into base64
* `Fn::GetAZs`
	* Returns an array that lists *Availability Zones* for a specified region
	* If region is omitted return AZs from the region the template is applied in
* `Fn::ImportValue`
	* Returns the value of an *Output* exported by another stack
* `Fn::Split`
	* Split a string into a list of string values so that you can select an element from the resulting
	string list
* `Fn::If`
	* Takes a list of arguments (`boolean`, `string1`, `string2`)
	*	Returns `string1` if `boolean` is `true`, `string2` otherwise
* `Fn::And`, `Fn::Equals`, `Fn::Or`, `Fn::Not`
	* Good for `condition` element

---

<a name="7"></a>
# [↖](#top)[↑](#6_2_3)[↓](#7_1) Backups & Recovery

<a name="7_1"></a>
## [↖](#top)[↑](#7)[↓](#7_2) AWS Services with automated backups
* RDS
  * Backups
    * *Transactional* storage engine recommended as DB engine
    * Degrades performance if multi-AZ is not enabled (taken from slave if enabled)
    * Deleting an instance deletes all *automated* backups
    * Backups are stored internaly on S3
    * PITR 5 minutes

  * Restoring
    * When restoring, only default parameters and security groups are associated with instance
    * Can change to different storage engine if closely related and enough space available

* Elasticache
  * Backups
    * Available to Redis cluster only
    * Taking snaphots can degrade performance, should be performed on read replica
    * Backups are stored internaly on S3

* Redshift
  * Backups
    * Provides free storage equal to the storage capacity of the cluster
    * Snapshots can be automated or manual and are incremental
    * Backups are stored internaly on S3
  * Restoring
    * Creates a new cluster and imports the data

* EC2
  * Backups
    * No built-in automated backup solution
    * Snapshots of EBS volumes are incremental, causing performance degradation
    * Every snapshot will restore *all* data, even if older snapshots are deleted
    * Backups are stored internaly on S3

<a name="7_2"></a>
## [↖](#top)[↑](#7_1)[↓](#7_2_1) Disaster Recovery Scenarios

<a name="7_2_1"></a>
### DR of on-prem infra
* Use AWS as backup solution by storing VMs, snapshots and other data
* 'Pilot light' - have bare minimum infra always ready and scale up as required
* 'Hot standby' (aka 'multi site') - has everything ready to go

<a name="7_2_2"></a>
### DR of cloud infra
* Duplicate the environment from one region to another

<a name="7_2_3"></a>
### DR of RDS data
* Protection from multiple AZs being down
* Reduce latency for global audience
* Replica lag will most likely go up
  * Data transfer across regions is getting charged
  * May potentially run into bandwith issues
* Create read replica from existing DB instance, pick different region
  * Trigger setup process that will take some time

<a name="7_3"></a>
## [↖](#top)[↑](#7_2_3)[↓](#8) Storing log files and backups
* Implement centralized logging
  * From there
    * Send to 3rd party tool for analyis
    * Backup to S3
      * 11x9 durability
      * Versioning
      * Lifecycle policies

* Other logging options
  * S3 access logs
  * Cloudtrail
  * Cloudwatch

---

<a name="8"></a>
# [↖](#top)[↑](#7_3)[↓](#8_1) Security

<a name="8_1"></a>
## [↖](#top)[↑](#8)[↓](#8_1_1) Implement and Manage Security Policies

<a name="8_1_1"></a>
### IAM
IAM is a global service that helps to securely control access to AWS resources.

* **Users** hold credentials
* **Groups** hold users, typically only provides permission to assume a role
* **Roles** hold policies.
	* Can have **trust relationships** with trusted entities that can *assume* this role
* **Policies** can be attached to users, groups or roles (preferred)
* An **instance profile** is a container for an IAM role that you can use to pass role information to an
	EC2 instance when the instance starts.
* Users and/or services assume roles

<a name="8_1_1_1"></a>
#### Policies
* Any actions on resources that are not explicitly allowed are **denied by default**
* Structure
	* **E** - `effect` (*allow*/*deny*)
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
<a name="8_1_1_2"></a>
#### IAM Policies
* Managed policies (the new way)
	* Can be attached to multiple users, groups and roles
	* AWS managed policies
		* Updated by AWS if new API come out
  * Customer managed policies
* Inline policies (the old way)

<a name="8_1_1_3"></a>
#### IAM roles and EC2

* Create an IAM role.
  * Define which accounts or AWS services can assume the role.
    * EC2 here, could be other services
  * Define which API actions and resources the application can use after assuming the role.
  * Specify the role when you launch your instance, or attach the role to a running or stopped instance.
  * Have the application retrieve a set of temporary credentials and use them.

* Only one role can be assigned to an EC2 instance, and all applications share the same role and permissions

<a name="8_1_2"></a>
### S3 IAM and bucket policy concepts

<a name="8_1_2_1"></a>
#### Defaults
* Bucket is *owned* by the AWS account that created it
	* Bucket ownership is not transferable
* Bucket owner gets full permission (ACL)
* The person paying the bills always has full control.
* A person uploading an object into a bucket owns it by default.

<a name="8_1_2_2"></a>
#### Bucket policies (resource level)
* Specify what actions are allowed or denied for which principals on the bucket that the policy
  is attached to
* Attached *only* to S3 buckets. Can however effect object in buckets.
* Contains *principal* element (unnecessary for IAM policies)
* Use if you’re more interested in *“Who can access this S3 bucket?”*
* Easiest way to grant *cross-account permissions* for all `s3:*` permission. (Cannot do this
  with ACLs.)
* Explicit *deny* in bucket policy overwrites explicite *allow* in IAM policy
* Defined as JSON

```
{
"Version":"2012-10-17",
"Statement":
  [
    {
      "Sid":"PutObjectAcl",
      "Effect":"Allow",
      "Principal":
      {
        "AWS":
          [
           "arn:aws:iam::111122223333:tom", "arn:aws:iam::444455556666:chris"
          ]
      },
      "Action":
        [
          "s3:PutObject",
          "s3:PutObjectAcl"
        ],
        "Resource":
        [
          "arn:aws:s3:::examplebucket/*"
        ]
    }
  ]
}
```

<a name="8_1_2_3"></a>
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
```
<?xml version="1.0" encoding="UTF-8"?>
<AccessControlPolicy xmlns="http://s3.amazonaws.com/doc/2006-03-01/">
  <Owner>
    <ID>*** Owner-Canonical-User-ID ***</ID>
    <DisplayName>owner-display-name</DisplayName>
  </Owner>
  <AccessControlList>
    <Grant>
      <Grantee xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
               xsi:type="Canonical User">
        <ID>*** Owner-Canonical-User-ID ***</ID>
        <DisplayName>display-name</DisplayName>
      </Grantee>
      <Permission>FULL_CONTROL</Permission>
    </Grant>
  </AccessControlList>
</AccessControlPolicy> 
```

<a name="8_1_2_4"></a>
#### IAM policies (user level)
* IAM policies (in general) specify what actions are allowed or denied on what AWS resources
* Attached to IAM users, groups, or roles (so they cannot grant access to anonymous users)
* Use if you’re more interested in *“What can this user do in AWS?”*

.|.
-|-
`arn:partition:service:region:namespace:relative-id`|`arn:aws:s3:::mybucket`
`arn:aws:s3:::*`|All buckets and objects in account
`arn:aws:s3:::mybucket`|`mybucket`
`arn:aws:s3:::mybucket/*`|All objects in `mybucket`
`arn:aws:s3:::mybucket/mykey`|`mykey` in `mybucket`
`arn:aws:s3:::mybucket/developers/($aws:username)/`|folder matching the accessing user's name

<a name="8_1_2_5"></a>
#### Cloudfront
* Can use Cloudfront Origin Access Identity to restrict access to S3 objects

<a name="8_2"></a>
## [↖](#top)[↑](#8_1_2_5)[↓](#8_2_1) Ensure Data Integrity and Access Controls when Using the AWS Platform

<a name="8_2_1"></a>
### MFA
* *Should* be turned on for all console access
* *Can* be enabled for API access as well
  * The administrator configures an AWS MFA device for each user who needs to make API requests that
  require MFA authentication. This process is described at Enabling MFA Devices.
  * The administrator creates policies for the users that include a *Condition* element that checks
  whether the user authenticated with an AWS MFA device.
  * The user calls one of the AWS STS API operations that support the MFA parameters `AssumeRole` or
  `GetSessionToken`, depending on the scenario for MFA protection, as explained later. As part of the
  call, the user includes the device identifier for the device that's associated with the user. The
  user also includes the time-based one-time password (TOTP) that the device generates. In either case,
  the user gets back temporary security credentials that the user can then use to make additional
  requests to AWS.
  * This is not supported by all services (support by *SQS*, *SNS*, *S3*)

* MFA delete can be enabled for root accounts (bucket owners) before permanently deleting an object

```
{
  "Version": "2012-10-17",
  "Statement": [{
    "Effect": "Allow",
    "Principal": {"AWS": ["ALICE", "BOB"]},
    "Action": [ "s3:PutObject", "s3:DeleteObject" ],
    "Resource": ["arn:aws:s3:::Alice-Bucket/*"],
    "Condition": {"Bool": {"aws:MultiFactorAuthPresent": "true"}}
  }]
}
```

<a name="8_2_2"></a>
### Secure Token Service (STS)
* Allows to grant **temporary access** to authenticated users
	* IAM users
	* Web-based identity providers (google, facebook, ...)
	* Organization's existing identity system
* Returns **temporary credentials** that expire after some time:
	* Access key
	* Session token

<a name="8_2_2_1"></a>
#### Terms
* **Federation**
	* Trust relationship between identity provider and AWS
* **Identity broker**
	* Broker in charge of mapping user to the right set of credentials
* **Identity store**
	* Eg Google or Facebook
* **Identities**
	* Users

<a name="8_2_2_2"></a>
#### Scenarios
* Temporary credentials with EC2
	* Assign IAM role to instance
	* Get temp credentials from *instance metadata*
* Temporary credentials with SDK
	* Call `assumeRole`, extract temp credentials
* Options for temporary credentials with API calls
	* *Sign request* with temp credentials
	* Add AC/SK to request (*header* or *query string*)

<a name="8_3"></a>
## [↖](#top)[↑](#8_2_2_2)[↓](#8_4) Share responsibility model
* **Shared responsibility** environment
* AWS is responsible for:
	* Server/Host level and below
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

<a name="8_4"></a>
## [↖](#top)[↑](#8_3)[↓](#9) AWS and IT Audits
* AWS performs self audits of changes to key services to monitor quality, maintain high standards, and
facilitate continuous improvement of the change management process
*  For audits, AWS provides:
  * *Security of the cloud*
  * Information regarding their global infrastructure
  * From the host operating system and virtualization layer down to the physical security of facilities
  * Annual certifications and reports: (like the Service Organization Control (SOC) reports, ISO 27001
  cert, PCI assessments)
* For audits, the customer provides:
  * *Security in the cloud*
  * Anything their organization puts on (or connects to) their AWS assets
  Examples: guest operating system, apps on virtual machine instances, objects in S3, database like RDS,
  etc...

---

<a name="9"></a>
# [↖](#top)[↑](#8_4)[↓](#9_1) Networking

<a name="9_1"></a>
## [↖](#top)[↑](#9)[↓](#9_1_1) Route53 Routing Policies
  * *Simple*
  * *Weighted*
  * *Latency*
  * *Failover*
  * *Geolocation*

<a name="9_1_1"></a>
### DNS Failover
* Can set up *health checks* for endpoints or domains from within *Route53*
  * Route 53 has health checkers in locations around the world. When you create a health check that
    monitors an endpoint, health checkers start to send requests to the endpoint that you specify
    to determine whether the endpoint is healthy.
  * `evaluate target health`
* DNS entries are then being associated with health checks and can be configured to failover as
  well (1 primary and n secondary recordsets)

<a name="9_1_2"></a>
### Weighted
* Control distribution of traffic with DNS entries
  * This can be based on a certain percentage
  * Set *routing policy* to weighted (instead of failover)

<a name="9_1_3"></a>
### Latency-based
* Control distribution of traffic based on latency.

<a name="9_2"></a>
## [↖](#top)[↑](#9_1_3)[↓](#9_2_1) VPC Essentials
* Provisions a logically isolated section of the AWS cloud
* Spans over all AZs in a region
* Allows to create layered architecture
* Shared or dedicated tenancy (exclusive hardware or not)
* *Security groups* and subnet *network ACLs*
* Ability to extend on-premise network to cloud

<a name="9_2_1"></a>
### Default VPC (Amazon specific)
* Gives easy access to a VPC without having to configure it from scratch
* Has different subnets in different AZs and an internet gateway per AZ
* Each instance launched automatically receives a *public IP* (very different to non-default VPC)
* Cannot be restored if deleted

<a name="9_2_2"></a>
### Non-default VPC (regular VPC)
* Only has private IP addresses
* Resources *only* accessible through *Elastic IP*, *VPN* or *internet gateways*
* Does not have a gateway attached

<a name="9_2_3"></a>
### VPC Peering
* Connect VPCs through direct network routing
* Can occur between different accounts and VPCs, but must be in the same region
* Allows instances to communicate with each other as if they were in the same network
* CIDRs must not overlap

<a name="9_2_4"></a>
### VPC Scenarios
* VPC with private subnet only -> single tier apps
* VPC with public and private subnets -> layered apps
* VPC with public, private subnets and hardware connected VPN -> extending apps to on-premise
* VPC with private subnets and hardware connected VPN -> extended VPN

<a name="9_2_5"></a>
### Components
* **Subnet**
	* In exactly one AZ
	* If a subnet doesn't have a route to the Internet gateway, it's known as a *private* subnet
    * Instances receive
      * *Private IP* address
      * Internal DNS hostname
	* If traffic is routed to an Internet gateway, the subnet is known as a *public* subnet
    * Instances receive
      * *Public IP* address
      * External DNS hostname
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
	* Static IPv4 address mapped to an *instance* or *network interface*
	* If attached to network interface it's decoupled from the instance's lifecycle
	* Routes to *private IP* address of instance
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

<a name="9_2_6"></a>
### Security
<a name="9_2_6_1"></a>
#### Network ACL
* Subnet level, acting as firewall
* Rules for inbound and outbound traffic
* Rules have numbers and are evaluated from low to high, first matching rule wins, others are *not* evaluated
* *Stateless*

<a name="9_2_6_2"></a>
#### Security Groups
* Acts as a virtual firewall to control inbound and outbound traffic to instances
* Acts on instance level, not subnet level
* Rules for inbound and outbound traffic
* *Stateful* - will always allow response to (allowed) outbound traffic
* Can refer to other security group, e.g. allow traffic from there

<a name="9_2_6_3"></a>
#### Structure & package flow
* VPC (has *CIDR*)
	* Gateway (Internet or VPN)
	* Routes (one per subnet, can be shared)
	* Network ACL (one per subnet, can be shared)
	* Subnets (CIDRs match VPC's CIDR)
	* Security Group (on VPC level)
	* Instance (needs public IP for internet communication, either ELB or Elastic IP)

* Flow from internet
  * Internet Gateway
  * VPC Router (routes into desired subnet)
  * Route Table (of that subnet)
  * NACL
  * Security Group
  * Instance

<a name="9_2_6_4"></a>
#### Connection To On-prem Network/Direct Connect
* VPC
  * (has attached) Virtual Private Gateway
  * (has attached) VPN Connection
  * (has attached) Customer Gateway

TODO: VPN vs direct connect. Can I use VPN instead of DC?

<a name="9_3"></a>
## [↖](#top)[↑](#9_2_6_4)[↓](#10) Limits:
.|.
-|-
VPCs per region|5
Subnets per VPC|200
Customer gateways per region|50
Virtual private gateways per region|5
Virtual private gateways per VPC|1
Gateway per region|5 Internet
Elastic IPs per account per region|5
VPN connections per region|50
Route tables per region|200
Security groups per region|500

<a name="10"></a>
# [↖](#top)[↑](#9_3)[↓](#10_1) Etc

<a name="10_1"></a>
## [↖](#top)[↑](#10)[↓](#10_2) Accessing the OS
* Services that allow access the the underlaying OS
  * EC2
  * ECS
  * EB  (Elastic Bean Stalk)
  * EMR (Elastic Map Reduce)
  * OpsWorks
* Services that hide the OS away (managed services)
  * DynamoDB
  * RDS

<a name="10_2"></a>
## [↖](#top)[↑](#10_1)[↓](#10_3) SQS
  * Default message retention period: 4 days (max 14 days)
  * `DelaySeconds` will delay a message appearing in the queue
  * Setting `WaitTimeSeconds` will enable *long polling* (can be more cost efficient)

<a name="10_3"></a>
## [↖](#top)[↑](#10_2)[↓](#) DynamoDb
  * Prefix partition key with hash to enforce even distribution of IO across many partitions
