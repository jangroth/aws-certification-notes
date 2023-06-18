
# DevOps Engineer Professional (C02)

## Comments per Service

### CodeStar

#### CodeCommit

- CodeCommit requires CloudWatch Events rule to trigger CodePipeline
- Can trigger lambda functions out of CodeCommit events
- AWS provides several managed policies:
	- `AWSCodeCommitFullAccess` , `AWSCodeCommitPowerUser` , `AWSCodeCommitReadOnly`
- Can use Approval Rule templates to e.g. trigger unit tests via CodeBuild

#### CodePipeline

- CodePipeline can execute cross-region actions
- CodePipeline can deploy straight into S3
- CodePipeline can have custom actions that invoke job workers

#### CodeBuild

- CodeBuild can be triggered directly from Github via web hook
- CodeBuild supports build badges, which provide an embeddable, dynamically generated image (_badge_) that displays the status of the latest build for a project

#### CodeDeploy

- In EC2/On-Premises deployment, a CodeDeploy **deployment group** is a set of individual instances targeted for a deployment. A deployment group contains individually tagged instances, Amazon EC2 instances in Amazon EC2 Auto Scaling groups, or both.
- CodeDeploy can terminate the original instances in the deployment group with a waiting period of 1 hour.
- CodeDeploy has a default timeout of 1 hour to wait for scripts to finish
- CodeDeploy failing on `AllowTraffic` can mean that health checks on ELB are misconfigured
- Notifies via CloudWatch Events
	- Lambda[]()
	- SNS
	- Kinesis streams
	- SQS
	- Built-in targets (CloudWatch Alarms actions)

#### CodeGuru

- Amazon CodeGuru **Profiler** helps developers understand the runtime behaviour of their applications, improve performance, and decrease infrastructure costs.
- Amazon CodeGuru **Reviewer** is an automated code review service that identifies critical defects and deviation from coding best practices for Java and Python code. Works on PRs
- Reviewer can protect secrets and suggest code changes to mitigate

### IaC

#### CloudFormation

- CFN custom resources ->  pre-signed URLs
- In a stackset, global resources (like S3) have to be unique
- CloudFormation drift detection requires manual intervention; use AWS Config to automate detection.

#### Service Catalog

- By using a launch role via **launch constraint**, you can instead limit the end users’ permissions to the minimum they require for that product
- The **template constraint** limits the options that are available to end-users when they launch a product. It works by narrowing the allowable values for parameters that are defined in the product’s underlying AWS CloudFormation template
	- Apply template constraints to ensure that the end users can use products without breaching the compliance requirements of your organization

#### OpsWorks

- OpsWorks can create time-based instances for scaling of predictable workload,  or load-based using CPU utilisation or load, or memory utilisation

### Compute

#### EC2

- EC2 memory metrics are not collected by default and need to have CloudWatch agent installed
- EC2 can use built-in **instance recovery**
- An instance is scheduled to be retired when AWS detects irreparable failure of the underlying hardware that hosts the instance.
	- When an instance reaches its scheduled retirement date, it is stopped or terminated by AWS.
	- AWS also sends an AWS Health event, which you can monitor and manage by using Amazon CloudWatch Events.

#### ASG

  - ASG lifecycle states:
    - `Pending` (hooks `Pending:Wait`, `Pending:Proceed`)
    - `InService`
    - `Terminating` (hooks `Terminating:Wait`, `Terminating:Proceed`)
    - `Terminated`
- `Pending:Wait` lifecycle hook can allow AMI upgrades before bringing them into service
- `Terminating:Wait` lifecycle hook to collect instance data (e.g. logs) before final termination
- Tags mentioned in the Auto Scaling group are _not_ propagated to EBS volumes
- ASG: A warm pool gives you the ability to decrease latency for your applications that have exceptionally long boot times, for example, because instances need to write massive amounts of data to disk.
	- Can keep instances in pool _running_ or _stopped_
- ASG can notify via SNS on failed instance launch
- Can use Amazon EventBridge or Amazon CloudWatch Events to track the Auto Scaling Events
	- Can trigger Lambdas from ASG by filtering on EventBridge events
- CloudFormation + ASGs:
    - `AutoScalingReplacingUpdate`: `WillReplace` `true` will wait for a complete replacement of the ASG and its instances before deleting the old ASG
    - `AutoScalingRollingUpdate`: replaces existing instance in ASG; valid options: MaxBatchSize, MinInstancesInService,  MinSuccessfulInstancesPercent, PauseTime, SuspendProcesses, WaitOnResourceSignals

#### Storage Gateway

- Storage Gateway does not automatically refresh the cache if the files were added directly to S3. `RefreshCache` can be used to refresh the cache periodically.
	- **Tape gateway** is backed up by glacier, meant for backups etc
	- **File gatewayEC2** gets on-premises data into the cloud
	- **Volume gateway** is cloud-backed iSCSI block storage volumes

#### SSM

- ``AWS-AmazonLinuxDefaultPatchBaseline`` is a predefined patch baseline, doesn't do custom patches
- `aws:runDocument` plugin runs SSM documents stored in Systems Manager or on a local share
- `aws:downloadContent` plugin downloads an SSM document from a remote location to a local share
- Can use SSM to create AMIs

#### ELB

- ALBs can be configured for 'dual stack' mode that allows IPv4 and IPv6
- ALBs can have weightings between target groups

### Security

#### IAM

- `iam:passrole` passes a role to a service. E.g. a developer role to CloudFormation

#### Firewall Manager

- Firewall Manager can be used to configure and apply WAF ACLs to the ALBs in an AWS account. It can help centrally manage as well as apply them to new accounts added to the Organization in the future.

#### KMS

- **KMS grants** are commonly used by AWS services that integrate with AWS KMS to encrypt your data at rest.
	- The service creates a grant on behalf of a user in the account, uses its permissions, and retires the grant as soon as its task is complete.

### Compliance

#### GuardDuty

- Can be used for org-wide compliance
- AWS recommends a separate delegated GuardDuty administrator account
- Can auto-enable GuardDuty for all future Org accounts
- Can configure GuardDuty **Trusted IP** list and **Threat IP** list and work with findings based on those
- GuardDuty needs EventBridge for filtering

#### Config

- AWS Config can ensure all EC2 instances are managed by AWS Systems Manager.
- AWS Config can find `ec2-volume-inuse-check`, but cannot detect how long a volume was unused for
- `cloudformation-stack-drift-detection-check`  checks if the actual configuration of a CloudFormation stack differs, or has drifted
-  `s3-bucket-ssl-requests-only`  checks whether S3 buckets have policies that require requests to use SSL
- Can deploy **conformance packs** into org accounts (from a delegated admin account)
- Config itself is per region, use **Config Aggregator** for centralised collection of findings across regions & accounts
	- Uses aggregator account
- By default, AWS Config will not automatically remediate the accounts that disabled its CloudTrail. You must manually set this up using a CloudWatch Events rule and a custom Lambda function that calls the StartLogging API to enable CloudTrail back again. Furthermore, the `cloudtrail-enabled` AWS Config managed rule is only available for the periodic trigger type and not Configuration changes.

#### ControlTower

- Use EventBridge to get notifications on Control Tower events like `CreateManagedAccount`
- **Customizations for AWS Control Tower (CfCT)** helps you customize your AWS Control Tower landing zone and stay aligned with AWS best practices. Customizations are implemented with AWS CloudFormation templates and service control policies (SCPs).
	- CfCT capability is integrated with AWS Control Tower lifecycle events so that your resource deployments remain synchronized with your landing zone

#### Org Policies

- Are inherited down the path `org root` -> `ou` -> `accounts`

#### Trusted Advisor

- AWS Trusted Advisor checks identify ways to optimize your AWS infrastructure, improve security and performance, reduce costs, and monitor service quotas
	-  Cost Optimization, Performance, Security, Fault Tolerance, and Service Limits
- TrustedAdvisor can check for under-utilized EC2
- Trusted Advisor's primary integration point is CloudWatch Events
-  With Trusted Advisor’s **Service Limit Dashboard**, you can view, refresh, and export utilization and limit data on a per-limit basis.
	- Metrics are published on Amazon CloudWatch in which you can create custom alarms

#### Health

- AWS Health is scanning public repos and can send events for compromised keys
- On detection of an exposed IAM access key, AWS Health generates an `AWS_RISK_CREDENTIALS_EXPOSED` CloudWatch Event.
- Also lists AWS Scheduled maintenance events on Health Dashboard
	- Can use CloudWatch Events/EventBridge to trigger workflows based on events
-  Can monitor AWS Health events using Amazon EventBridge or CloudWatch Events by calling the AWS Health API

#### CloudTrail

- Can set up trails for
	- **Data events**: These events provide insight into the resource operations performed on or within a resource. These are also known as data plane operations.
		- For S3 or Lambda data events
	- **Management events**: Management events provide insight into management operations that are performed on resources in your AWS account. These are also known as control plane operations.

### Networking

#### VPC

- NAT gateway does not span multiple AZs (instead: one gateway per AZ)
- Can send VPC Flow Logs to CloudWatch Logs

### Storage

#### Aurora

- Read replicas are always asynchronous
- AWS Aurora Global Database uses storage-based replication with typical latency of less than 1 second, using dedicated infrastructure that leaves your database fully available to serve application workloads.
	- 1 primary region (read/write), up to 5 secondary regions (read)
	- In the event of a regional degradation or outage, one of the second regions can be promoted to read and write capabilities in less than 1 minute.
- Aurora endpoints
	- single built-in cluster endpoint, connects to the primary instance of the cluster
	- reader endpoint for read-only connections for your Aurora cluster
	- can have custom cluster endpoints (managed by Aurora) that can be READER. WRITER or ANY

#### RDS

- RDS creates and saves automated backups of your DB instance or Multi-AZ DB cluster during the backup window of your database.
	- default: 30min backup during 8h per-region night
- Amazon RDS uses SNS to provide notification when an Amazon RDS event occurs.
	- Can also use CloudWatch Events/Eventbridge
- Failover:
    - AZ outages => RDS multi-AZ deployment
    - Regional outages => RDS read replica
    - Multi-region deployments are like multi-AZ deployments, but other regions  can be used for reads. Read replicas can be in the same AZ, same region, or cross-region
    - Read replicas have best RTO/RPO, but highest cost

#### DynamoDB

- In DynamoDb `ThrottledWriteRequests` can help adjusting increase the maximum write capacity units for the table's Auto Scaling policy.
- `WriteThrottleEvents` are requests to DynamoDB that exceed the provisioned write capacity units for a table or a global secondary index.
- Can use Kinesis Data Streams to capture changes to DynamoDB
- Amazon DynamoDB global tables provide a single-digit millisecond latency and make sure the data is available across regions.
- DynamoDB Global Tables requires
	- tables are created in each region already
	- DynamoDB Streams is enabled
- Don't have multiple lambdas read from DynamoDB Streams
	- Only one process per shard!
	- Better to use fan-out pattern

#### Glue

- AWS Glue is an efficient way to store object metadata. Combination: S3 - Glue - Athena - QuickSight

#### S3

- Can include a pre-calculated checksum as part of your request. Amazon S3 compares the provided checksum to the checksum that it calculates by using your specified algorithm
- Can activate access logs and use Athena for analysis/queries
- S3 cross-region replication is push-based: source bucket gets a replication rule, destination bucket gets a bucket policy, source needs IAM role for S3 service to assume
	- Configure a replication rule within the source bucket to activate the replication process.
	- Create a bucket policy in the destination bucket that grants the source bucket permission to replicate objects into it.
	- In the source AWS account, create an IAM role that Amazon S3 can assume to replicate objects. Enable versioning in both buckets.
 - AWS CloudTrail only logs bucket-level actions in your Amazon S3 buckets by default. If you want to record all object-level API activity in your S3 bucket, you can set up data events in CloudTrail

### Serverless

#### API Gateway

- API Gateway does not have specific metrics for individual http error codes like 403, only a generic `4XXError` metric
- Can enable API **caching** in Amazon API Gateway to cache your endpoint's responses

#### ECS

- can set ECS tasks as a target of CloudWatch events
- ECS/Fargate logs
	- add the required `logConfiguration` parameters to your task definition to turn on the `awslogs` log driver
- ECS/EC2
	- container instances have an attached IAM role that contains `logs:CreateLogStream` and `logs:PutLogEvents`
	- to turn on the `awslogs` log driver, your Amazon ECS container instances require at least version 1.9.0 of the container agent

### Application Auto Scaling

- Is a web service for automatically scaling scalable resources for individual AWS services beyond Amazon EC2
	- Lambda function provisioned concurrency
	- DynamoDB tables and global secondary indexes
	- Aurora replicas
	- Amazon Elastic Container Service (ECS) services
	- ...

- **Target** tracking scaling – Scale a resource based on a target value for a specific CloudWatch metric.
- **Step** scaling – Scale a resource based on a set of scaling adjustments that vary based on the size of the alarm breach.
- **Scheduled** scaling – Scale a resource one time only or on a recurring schedule.

### Content Delivery

#### CloudFront

- **OriginGroup**: An origin group includes two origins (a primary origin and a second origin to failover to) and a failover criteria that you specify.

### Notifications/Events

#### SNS

- SNS defines a **delivery policy** for each delivery protocol. The delivery policy defines how Amazon SNS retries the delivery of messages when server-side errors occur (when the system that hosts the subscribed endpoint becomes unavailable).
	- When the delivery policy is exhausted, Amazon SNS stops retrying the delivery and discards the message
	- —> unless a **dead-letter queue** is attached to the subscription.
- For ECS notifications on **essential task** stopped, used EventBridge
- For S3 fanout, use SNS and subscribe consumers to it

### Logging/Monitoring/Notification

#### CloudWatch

- CloudWatch Logs are always encrypted
- CloudWatch _Metrics_ filters can be used to filter CloudWatch _Logs_
- Can create CloudWatch **Alarm** for the `StatusCheckFailed_System` metric and select the EC2 action to recover the instance
- **CloudWatch Logs Subscription** for near realtime feed of log events
	- "Getting logs out of CloudWatch for further processing"
	- from CloudWatch Logs, to _Kinesis_, _ElasticSearch_ or _Lambda_
- CloudWatch has a predefined dashboard for CodeBuild metrics
- You can call the EC2 `CreateSnapshot` API directly as a target from CloudWatch Events.

#### KMS

- KMS monitors to CloudWatch, can define alarms and alert

#### Xray

- Can run X-Ray daemon on AWS Elastic Beanstalk
- X-Ray daemon uses UDP port 2000

---

## Comments per Topic

### Implement CI/CD Pipelines

- CodeDeploy states + lifecycle hooks
- CodeCommit IAM policies
- CodeCommit needs CloudWatch Events/EventBridge to detect PRs
	- (EventBridge is the same service as CloudWatch Events, just with a new interface and more features exposed.)
- GitHub needs a web hook to start a CodePipeline
- CodeDeploy lifecycle hooks (reserved for CodeDeploy in parentheses):
	- `ApplicationStop`
	- (`DownloadBundle`)
	- `BeforeInstall`
	- (`Install`)
	- `AfterInstall`
	- `ApplicationStart`
	- `ValidateService`
	- `BeforeBlockTraffic`
	- (`BlockTraffic`)
	- `AfterBlockTraffic`
	- `BeforeAllowTraffic`
	- (`AllowTraffic`)
	- `AfterAllowTraffic`
- Integrate automated testing into CI/CD pipelines
	- CloudWatch Logs + EventBridge to automate based on CodeBuild job results
	- CodeDeploy + EventBridge to automate based on CodeDeploy job results
	- EventBridge for CodePipeline scheduled events
	- CodeDeploy can integrate with CloudWatch Alarms to pause deployments
- Build and manage artifacts
	- CodeBuild + CodePipeline + CodeDeploy + S3 for artifacts
	- S3 versioning + encryption required for CodePipeline
- Implement deployment strategies for instance, container, and serverless environments
	- Elastic Beanstalk policies
		- All at once - fastest, but causes downtime; all remaining options have zero downtime
		- Rolling - still uses batches
		- Rolling with additional batch - to maintain full capacity during deploy
		- Immutable for when new & old versions must not be mixed and for fast rollback
		- Traffic splitting: for canary deploys
		- Blue/Green deployments: swap environment URLs; keep RDS in a separate stack; requires DNS change (all previous ones do not)
	- Lambda
		- canary deployments via alias weights
		- use CodeDeploy default deploy options:
			- Lambda: `LambdaLinear10PercentEvery10Minutes` (10% of traffic shifted at a time), `LambdaCanary10Percent10Minutes` (one 10% and one 90% deploy)
			- EC2: `AllAtOnce`, `OneAtATime`, `HalfAtATime`
	  - ALB + EC2 + Route53 alias record swaps
	  - OpsWorks Stack cloning + Route53 alias swaps
		  - OpsWorks lifecycle stages

### Config Management and IaC

- Define cloud infrastructure and reusable components to provision and manage  systems throughout their lifecycle
	- CloudFormation cross-stack references use exports + Fn::ImportValue
	- Inline Lambda functions in CFN
	- Custom resource is used to invoke a Lambda function in AWS CloudFormation, the request will include a pre-signed URL. The Lambda  function is responsible for returning a response to the pre-signed URL to indicate if the resource creation was successful or not.
- Deploy automation to create, onboard, and secure AWS accounts in a multi-account/multi-region environment
- Design and build automated solutions for complex tasks and large-scale environments
	- CloudFormation + ASGs:
		- `AutoScalingReplacingUpdate`: `WillReplace:true` will wait for a complete replacement of the ASG and its instances before deleting the old ASG
		- `AutoScalingRollingUpdate`: replaces existing instance in ASG; valid options: `MaxBatchSize`, MinInstancesInService, MinSuccessfulInstancesPercent, PauseTime, SuspendProcesses, WaitOnResourceSignals
  - OpsWorks can create _time-based_ instances for scaling of predictable workload, or _load-based_ using CPU utilisation or load, or memory utilisation
  - Collecting on-prem info:
	  - Application Discovery Agent (install on each VM) or Agentless Discovery Connector (separate VM)

### Resilient Cloud Solutions

- Implement highly available solutions to meet resilience and business requirements
	- RDS:
		- AZ outages => RDS multi-AZ deployment
		- Regional outages => RDS read replica
		- Multi-region deployments are like multi-AZ deployments, but other regions can be used for reads. Read replicas can be in the same AZ, same region, or cross-region
		- Read replicas have best RTO/RPO, but highest cost
	- Frontend traffic switching => Route53 failover
	- AutoScaling with a min & max of 1 is actually sensible - it makes the instance auto-redeploy if it dies
	- Route53 policies: `simple`, `failover`, `geolocation`, `geoproximity`, `latency`, `multi-value answer`, `weighted`
- Implement solutions that are scalable to meet business requirements
	- ASG lifecycle states:
		- `Pending` (hooks `Pending:Wait`, `Pending:Proceed`)
		- `InService`
		- `Terminating` (hooks `Terminating:Wait`, `Terminating:Proceed`)
		- `Terminated`
	- EC2 autoscaling` Pending:Wait` lifecycle hook can allow AMI upgrades before bringing them into service
	- `Terminating:Wait` lifecycle hook to collect instance data (e.g. logs) before final termination
	- EKS: k8s cluster autoscaler or karpenter
  - EKS networking:
	- VPC CNI plugin
	- Load Balancer Controller
	- CoreDNS
	- kube-proxy
	- Calico
- Hybrid environment patching
- Implement automated recovery processes to meet RTO/RPO requirements

### Monitoring and Logging

- Configure the collection, aggregation, and storage of logs and metrics
	- AWS Config Aggregator for centralised collection of findings across regions & accounts
	- EC2 custom logging requirements => CloudWatch Logs Agent
	- ECS Fargate logs => awslogs driver on task definition
	- CloudWatch has a predefined dashboard for CodeBuild metrics
- Audit, monitor, and analyze logs and metrics to detect issues
	- near real time dashboards => QuickSight
	- near real time processing on CloudWatch logs:
		- Lambda subscription filter
		- Kinesis stream filter
		- ElasticSearch (OpenSearch) subscription filter
	- CloudTrail has log integrity checking which must be turned on
- Automate monitoring and event management of complex environments
	- Service limit alerting => Trusted Advisor + CloudWatch Alarms + ServiceLimitUsage metric

### Incident and Event Response

- Manage event sources to process, notify, and take action in response to events
	- S3 event notifications for data notifications like file deletion
	- RDS event notifications for multi-AZ failover events
	- EventBridge + AWS Health for notification about IAM credentials being  exposed on GitHub, and for notifications about instance outages, etc.
	- CloudTrail _data_ events for object-level activity on S3
	- EC2 Auto Scaling groups => EventBridge
	- CodePipeline stage => EventBridge
	- CodeDeploy => CloudWatch Alarm + `MinimumHealthyHosts` metric can be used for rollbacks
	- OpsWorks self-healing => EventBridge
- Implement configuration changes in response to events
- Troubleshoot system and application failures

### Security and Compliance

- Implement techniques for identity and access management at scale
	- Limit CodeCommit permissions via IAM policy which matches repo
	- S3 bucket policies for requiring TLS
- Apply automation for security controls and data protection
	- Lifecycle management + auto-rotation of secrets => Secrets Manager
	- Cost-effective => SSM Parameter Store SecureStrings
	- Patching => SSM Patch Manager
- Implement security monitoring and auditing solutions
