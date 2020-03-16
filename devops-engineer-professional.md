<!-- toc_start -->
<a name="top"></a>
---
* [DevOps Engineer Professional](#1)
* [Exam Objectives](#2)
  * [Content](#2_1)
* [Concepts](#3)
  * [Deployment Strategies](#3_1)
  * [EC2 Deployment Concepts](#3_2)
  * [EC2 Autoscaling Concepts](#3_3)
  * [External Tools](#3_4)
* [Services](#4)
  * [API Gateway](#4_1)
  * [CloudFormation](#4_2)
  * [CloudTrail](#4_3)
  * [CloudWatch](#4_4)
  * [CodeBuild](#4_5)
  * [CodeCommit](#4_6)
  * [CodeDeploy](#4_7)
  * [CodePipeline](#4_8)
  * [CodeStar](#4_9)
  * [Config](#4_10)
  * [ECS](#4_11)
  * [Elastic Beanstalk](#4_12)
  * [Kinesis](#4_13)
  * [Lambda](#4_14)
  * [Managed Services](#4_15)
  * [OpsWorks Stacks](#4_16)
  * [Organizations](#4_17)
  * [Step Functions](#4_18)
  * [X-Ray](#4_19)
---
<!-- toc_end -->

<a name="1"></a>
# [↖](#top)[↓](#2) DevOps Engineer Professional

> 10/2019 - *current*

---

<a name="2"></a>
# [↖](#top)[↑](#1)[↓](#2_1) Exam Objectives

* Implement and manage continuous delivery systems and methodologies on AWS
* Implement and automate security controls, governance processes, and compliance validation
* Define and deploy monitoring, metrics, and logging systems on AWS
* Implement systems that are highly available, scalable, and self-healing on the AWS platform
* Design, manage, and maintain tools to automate operational processes

<a name="2_1"></a>
## [↖](#top)[↑](#2)[↓](#2_1_1) Content
<!-- toc_start -->
* [Domain 1: SDLC Automation](#2_1_1)
* [Domain 2:Configuration Management and Infrastructure as Code](#2_1_2)
* [Domain 3: Monitoring and Logging](#2_1_3)
* [Domain 4: Policies and Standards Automation](#2_1_4)
* [Domain 5: Incident and Event Response](#2_1_5)
* [Domain 6: High Availability, Fault Tolerance, and Disaster Recovery](#2_1_6)
<!-- toc_end -->

<a name="2_1_1"></a>
### [↖](#2_1)[↑](#2_1)[↓](#2_1_2) Domain 1: SDLC Automation

* Apply concepts required to automate a CI/CD pipeline
* Determine source control strategies and how to implement them
* Apply concepts required to automate and integrate testing
* Apply concepts required to build and manage artifacts securely
* Determine deployment/delivery strategies (e.g., A/B, Blue/green, Canary, Red/black) and how to implement them using AWS Services

<a name="2_1_2"></a>
### [↖](#2_1)[↑](#2_1_1)[↓](#2_1_3) Domain 2:Configuration Management and Infrastructure as Code

* Determine deployment services based on deployment needs
* Determine application and infrastructure deployment models based on business needs
* Apply security concepts in the automation of resource provisioning
* Determine how to implement lifecycle hooks on a deployment
* Apply concepts required to manage systems using AWS configuration management tools and services

<a name="2_1_3"></a>
### [↖](#2_1)[↑](#2_1_2)[↓](#2_1_4) Domain 3: Monitoring and Logging

* Determine how to set up the aggregation, storage, and analysis of logs and metrics
* Apply concepts required to automate monitoring and event management of an environment
* Apply concepts required to audit, log, and monitoroperating systems, infrastructures, and applications
* Determine how to implement tagging and other metadata strategies

<a name="2_1_4"></a>
### [↖](#2_1)[↑](#2_1_3)[↓](#2_1_5) Domain 4: Policies and Standards Automation

* Apply concepts required to enforce standards for logging, metrics, monitoring, testing, and security
* Determine how to optimize cost through automation
* Apply concepts required to implement governance strategies

<a name="2_1_5"></a>
### [↖](#2_1)[↑](#2_1_4)[↓](#2_1_6) Domain 5: Incident and Event Response

* Troubleshoot issues and determine how to restore operations
* Determine how to automate event managementand alerting
* Apply concepts required to implement automated healing
* Apply concepts required to set up event-driven automated action

<a name="2_1_6"></a>
### [↖](#2_1)[↑](#2_1_5)[↓](#3) Domain 6: High Availability, Fault Tolerance, and Disaster Recovery

* Determine appropriate use of multi-AZ versus multi-region architectures
* Determine how to implement high availability, scalability, and fault tolerance
* Determine the right services based on business needs (e.g., RTO/RPO, cost)
* Determine how to design and automate disaster recovery strategies
* Evaluate a deployment for points of failure

<a name="3"></a>
# [↖](#top)[↑](#2_1_6)[↓](#3_1) Concepts

<a name="3_1"></a>
## [↖](#top)[↑](#3)[↓](#3_1_1) Deployment Strategies
<!-- toc_start -->
* [Single target deployment](#3_1_1)
* [All-at-once deployment](#3_1_2)
* [Minimum in-service style deployment](#3_1_3)
* [Rolling deployment](#3_1_4)
* [Rolling deployment with extra batches](#3_1_5)
* [Blue/green deployment](#3_1_6)
* [Red/black deployment](#3_1_7)
* [A/B testing](#3_1_8)
* [Canary deployment](#3_1_9)
<!-- toc_end -->

Strategy|Deploy<br/>time|Downtime|Testing|Deployment<br/>Costs|Impact of<br/>failed deployment|Rollback<br/>process|Elastic<br/>Beanstalk|CodeDeploy|OpsWorks
-|-|-|-|-|-|-|-|-|-
**Single Target Deployment**|🕑|complete deploy|limited|no extra costs|downtime|redeploy|*all at once*|todo|todo
**All At Once**|🕑|complete deploy|limited|no extra costs|downtime|redeploy|*all at once*|todo|todo
**Minimum In Service**|🕑🕑|none|can test new version<br/>while old is still active|no extra costs|no downtime|redeploy|*rolling*|todo|todo
**Rolling**|🕑🕑🕑|usually none|can test new version<br/>while old is still active|no extra costs|no downtime|redeploy|*rolling*|todo|todo
**Rolling With Extra Batches**|🕑🕑🕑|usually none|can test new version<br/>while old is still active|little extra costs|no downtime|redeploy|*rolling with<br/>extra batches*|todo|todo
**Blue/Green**|🕑🕑🕑🕑|none|can test <br/>prior to cutover|extra costs for new stack|no downtime|revert cutover|*immutable* comes close<br/>or: create new environment and use DNS|todo|todo

<a name="3_1_1"></a>
### [↖](#3_1)[↑](#3_1)[↓](#3_1_2) Single target deployment

System|Deploy
-|-
`v1`|Initial State
`v1-2`|Deployment Stage
`v2`|Final State

* When initiated a new application version is installed on the (single) target server
* Practically not in use any more

**pros**|**cons**
-|-
Simple & very few moving parts|Downtime
Deployment is faster than other methods|Limited testing

<a name="3_1_2"></a>
### [↖](#3_1)[↑](#3_1_1)[↓](#3_1_3) All-at-once deployment

System|Deploy|.
-|-|-
`v1` `v1` `v1` `v1` `v1`|Initial State|.
`v1-2` `v1-2` `v1-2` `v1-2` `v1-2`|Deployment Stage|.
`v2` `v2` `v2` `v2` `v2`|Final State|.

* Single build stage triggers multiple target environments

**pros**|**cons**
-|-
Deployment is relatively fast|Downtime (like STD)
.|Limited testing (like STD)
.|Everything in-flight - can't stop deployment/rollback if targets fail
.|More complicated than STD, often requires orchestration

<a name="3_1_3"></a>
### [↖](#3_1)[↑](#3_1_2)[↓](#3_1_4) Minimum in-service style deployment

System|Deploy|.
-|-|-
`v1` `v1` `v1` `v1` `v1`|Initial State|.
`v1` `v1` `v1-2` `v1-2` `v1-2`|Deployment Stage 1|Minimum targets required for operational state: 2
`v1-2` `v1-2` `v2` `v2` `v2`|Deployment Stage 2|.
`v2` `v2` `v2` `v2` `v2`|Final State|.

* Orchestration engines know how many targets are required for a *minimum operational state*
* System ensures that this number of instances is active while completing the rest of the deployment
  as quickly as possible
* Happens to as many targets as possible
* Suitable for large environments

**pros**|**cons**
-|-
No downtime|Many moving parts, requires orchestration
Deployment happens in (two) stages|.
Generally quicker & with less stages than rolling deployments|.

<a name="3_1_4"></a>
### [↖](#3_1)[↑](#3_1_3)[↓](#3_1_5) Rolling deployment

System|Deploy|.
-|-|-
`v1` `v1` `v1` `v1` `v1`|Initial State|.
`v1-2` `v1-2` `v1` `v1` `v1`|Deployment Stage 1|Deploy first set of targets
`v2` `v2` `v1-2` `v1-2` `v1`|Deployment Stage 2|Only if health checks succeed: Deploy next set of targets
`v2` `v2` `v2` `v2` `v1-2`|Deployment Stage 3|Only if health checks succeed: Deploy next set of targets
`v2` `v2` `v2` `v2` `v2`|Final State|.

* Do *x* deployments at once, than move on to the next *x*
* Flexible on failing health checks - roll back stage or whole deployment
* Was considered cheapest and least risk method until hourly and consumption-based billing entered
the market

**pros**|**cons**
-|-
No downtime (if number of stage deployments is small enough)|Does not necessarily maintain overall application health
Can be paused to allow for multi-version testing|Many moving parts, requires orchestration
.|Can be least efficient deployment method in terms of time taken

<a name="3_1_5"></a>
### [↖](#3_1)[↑](#3_1_4)[↓](#3_1_6) Rolling deployment with extra batches

System|Deploy|.
-|-|-
`v1` `v1` `v1` `v1`|Initial State|.
`v1` `v1` `v1` `v1` `.` `.`|Deployment Stage 1|Deploy new batch of servers
`v1` `v1` `v1` `v1` `v2` `v2`|Deployment Stage 2|Deploy new version to new servers
`.` `.` `v1` `v1` `v2` `v2`|Deployment Stage 3|Undeploy first batch
`v2` `v2` `v1` `v1` `v2` `v2`|Deployment Stage 4|Deploy new version to first batch
`v2` `v2` `.` `.` `v2` `v2`|Deployment Stage 5|Undeploy second batch
`v2` `v2` `v2` `v2`|Deployment Stage 6|Decommission servers from second batch

* Deploy new batch of servers first
* Very similar to *rolling deployment*

**pros**|**cons**
-|-
No downtime (if number of stage deployments is small enough)|Does not necessarily maintain overall application health
Can be paused to allow for multi-version testing|Many moving parts, requires orchestration
.|Can be least efficient deployment method in terms of time taken
<a name="3_1_6"></a>
### [↖](#3_1)[↑](#3_1_5)[↓](#3_1_7) Blue/green deployment

System|Deploy|.
-|-|-
(`v1` `v1` `v1`)()|Initial State|Blue environment, all traffic goes here
(`v1` `v1` `v1`)(`v` `v` `v`)|Deployment Stage 1|Bring up green environment
(`v1` `v1` `v1`)(`v2` `v2` `v2`)|Deployment Stage 2|Deploy application into green environment
(`v1` `v1` `v1`)(`v2` `v2` `v2`)|Deployment Stage 3|Cutover - direct traffic from blue to green
() (`v2` `v2` `v2`)|Final State|Blue environment removed

* Deploys to a separate environment to provide outage risks
* Different cutover techniques
	* DNS routing
	* Swap auto scaling group behind load balancer
  * Elastic Beanstalk *immutable*: Merge new ASG into old one
	* Update auto scaling launch configuration
	* Swap environment of an AWS Elastic Beanstalk application
	* Clone stack in AWS OpsWorks and update DNS

**pros**|**cons**
-|-
Rapid all-at-once deployment process, no need to wait for per target health checks|Requires advanced orchestration tooling
Can test health prior to cutover|Significant cost for a second environment (mitigated by advanced billing models)
Clean & controlled cutover (various options)|.
Easy rollback|.
Can be fully automated using advanced templating|.
By far the best method in terms of risk mitigation and minimal user impact|.

<a name="3_1_7"></a>
### [↖](#3_1)[↑](#3_1_6)[↓](#3_1_8) Red/black deployment

> ... are just like blue/green, but they happen at a much faster rate.

Example:
1. `DNS` -> `LB` -> `ASG1`
2. `DNS` -> `LB` -> `ASG2`

<a name="3_1_8"></a>
### [↖](#3_1)[↑](#3_1_7)[↓](#3_1_9) A/B testing
* Like blue/green deployment, but only shift a percentage of the traffic over, not everything at once
* Gradually increase percentage of traffic sent to the new environment
* Allows for different end goal:
	* *Measuer user feedback* and decide whether a feature should be rolled out or rolled back
	* This can be decided well before the new environment gets 100% of the traffic
	* Could only role out a feature to 10% of the users and switch back after metrics have been
	collected
	* -> different to red/green deployment
* Achieved via *AWS route 53* **weighted routing**

**pros**|**cons**
-|-
.|Different versions across the environment
.|DNS switching affected by caches and other DNS related issues

<a name="3_1_9"></a>
### [↖](#3_1)[↑](#3_1_8)[↓](#3_2) Canary deployment
* Like A/B testing, but gradually increases percentage of traffic to green environment

---

<a name="3_2"></a>
## [↖](#top)[↑](#3_1_9)[↓](#3_2_1) EC2 Deployment Concepts
<!-- toc_start -->
* [Instance Profile](#3_2_1)
* [ELB/ALB Logs](#3_2_2)
* [ELB/ALB Health Checks](#3_2_3)
* [ELB Security](#3_2_4)
<!-- toc_end -->

<a name="3_2_1"></a>
### [↖](#3_2)[↑](#3_2)[↓](#3_2_2) Instance Profile

* A *container* for an IAM *role* that you can use to pass role information to an EC2 instance when the instance starts.
* An EC2 Instance cannot be assigned a role directly, but it can be assigned an Instance Profile which contains a role.
* If you use the AWS Management Console to create a role for Amazon EC2, the console automatically creates an instance profile and gives it the same name as the role.
* If you manage your roles from the AWS CLI or the AWS API, you create roles and instance profiles as separate actions.

<a name="3_2_2"></a>
### [↖](#3_2)[↑](#3_2_1)[↓](#3_2_3) ELB/ALB Logs

* Access logging is an optional feature of Elastic Load Balancing that is disabled by default.
* After you enable access logging for your load balancer, Elastic Load Balancing captures the logs and stores them in the Amazon S3 bucket as compressed files.
* Can log every 5 or 60 minutes
* There's no additional charge
* You can disable access logging at any time.

<a name="3_2_3"></a>
### [↖](#3_2)[↑](#3_2_2)[↓](#3_2_4) ELB/ALB Health Checks

If you have associated your Auto Scaling group with a Classic Load Balancer, you can use the load
balancer health check to determine the health state of instances in your Auto Scaling group. By
default an Auto Scaling group periodically determines the health state of each instance.

Your Application Load Balancer periodically sends requests to its registered targets to test their
status. These tests are called health checks.

The status of the instances that are healthy at the time of the health check is `InService`. The
status of any instances that are unhealthy at the time of the health check is `OutOfService`.

<a name="3_2_4"></a>
### [↖](#3_2)[↑](#3_2_3)[↓](#3_3) ELB Security

* Need end-to-end security
* Encrypt all communication
* Use HTTPS (layer 7) or SSL (layer 4)
* Need to deploy an X.509 certificate on ELB
* Can configure back-end authentication
  * Once configured ELB only communicates with an instance if it has a matching public key

<a name="3_3"></a>
## [↖](#top)[↑](#3_2_4)[↓](#3_3_1) EC2 Autoscaling Concepts
<!-- toc_start -->
* [Overview](#3_3_1)
* [Components](#3_3_2)
  * [Autoscaling Group](#3_3_2_1)
  * [Launch Configuration](#3_3_2_2)
  * [Launch Template](#3_3_2_3)
  * [Termination Policy](#3_3_2_4)
  * [Auto Scaling Lifecycle Hooks](#3_3_2_5)
  * [Scaling](#3_3_2_6)
* [CLI/API/SDK](#3_3_3)
* [Troubleshooting](#3_3_4)
  * [Possible Problems](#3_3_4_1)
  * [Suspending ASG processes](#3_3_4_2)
<!-- toc_end -->

<a name="3_3_1"></a>
### [↖](#3_3)[↑](#3_3)[↓](#3_3_2) Overview

*Amazon EC2 Auto Scaling* helps you ensure that you have the correct number of Amazon EC2 instances
available to handle the load for your application. You create collections of EC2 instances, called
*Auto Scaling Groups*. You can specify the **minimum** number of instances in each Auto Scaling group,
and Amazon EC2 Auto Scaling ensures that your group never goes below this size. You can specify
the **maximum** number of instances in each Auto Scaling group, and Amazon EC2 Auto Scaling ensures
that your group never goes above this size. If you specify the **desired** capacity, either when you
create the group or at any time thereafter, Amazon EC2 Auto Scaling ensures that your group has
this many instances. If you specify **scaling policies**, then Amazon EC2 Auto Scaling can launch or
terminate instances as demand on your application increases or decreases.

* Auto scaling can play a major role in deployments
* Need to avoid downtime during deployments
* How long does it take to deploy code and configure an instance?
* How do you test a new launch configuration?
* How do you phase out older launch configurations?
* Use lifecycle hooks for custom actions
* CloudFormation init scripts
* Cloud init scripts
* Scale out/scale in

<a name="3_3_2"></a>
### [↖](#3_3)[↑](#3_3_1)[↓](#3_3_2_1) Components

<a name="3_3_2_1"></a>
#### [↖](#3_3)[↑](#3_3_2)[↓](#3_3_2_2) Autoscaling Group

* Contains a collection of Amazon EC2 instances that are treated as a logical grouping for the purposes of automatic scaling and management
* To use Amazon EC2 Auto Scaling features such as health check replacements and scaling policies

<a name="3_3_2_2"></a>
#### [↖](#3_3)[↑](#3_3_2_1)[↓](#3_3_2_3) Launch Configuration

* Instance configuration template that an Auto Scaling group uses to launch EC2 instances
* One LC per ASG, can be used in many ASGs though
* Can't be modified, needs to be recreated

<a name="3_3_2_3"></a>
#### [↖](#3_3)[↑](#3_3_2_2)[↓](#3_3_2_4) Launch Template

* Similar to LC
* Allows to have multiple versions of the same template
* With versioning, you can create a subset of the full set of parameters and then reuse it to create other templates or template versions
* AWS recommends to use launch templates instead of launch configurations to ensure that you can use the latest features of Amazon EC2

<a name="3_3_2_4"></a>
#### [↖](#3_3)[↑](#3_3_2_3)[↓](#3_3_2_5) Termination Policy

* To specify which instances to terminate first during scale in, configure a termination policy for the Auto Scaling group.
* Policies will be applied to the AZ with the most instances
* Can be combined with *instance proctection* to prevent termination of specific instances, this starts as soon as the instance is *in service*.
  * Instances can still be terminated manually (unless *termination protection* has been enabled)
  * Unhealthy instance will still be replaced
  * Spot instance interuptions can still occur
* *Instance protection* can also be applied to an autoscaling group - protecting the whole group: *protect from scale in*
* Can specify *multiple* policies, will be executed in order until an instance has been found
* *Default* policy being last in a list of multiple policies is like `catchAll`, will always find an instance

.|.|.
-|-|-
0|**Default**|Designed to help ensure that your instances span Availability Zones evenly for high availability<br/>`3`->`4`->`random`
1|**OldestInstance**|Useful when upgrading to a new EC2 instance type
2|**NewestInstance**|Useful when testing a new launch configuration
3|**OldestLaunchConfiguration**|Useful when updating a group and phasing out instances
5|**OldestLaunchTemplate**|Useful when you're updating a group and phasing out the instances from a previous configuration
4|**ClosestToNextInstanceHour**|Next billing hour - useful to maximize instance us
6|**AllocationStrategy**|Useful when preferred instance types have changed

<a name="3_3_2_5"></a>
#### [↖](#3_3)[↑](#3_3_2_4)[↓](#3_3_2_6) Auto Scaling Lifecycle Hooks

The EC2 instances in an Auto Scaling group have a path, or lifecycle, that differs from that of
other EC2 instances. The lifecycle *starts* when the Auto Scaling group launches an instance and
puts it into service. The lifecycle *ends* when you terminate the instance, or the Auto Scaling
group takes the instance out of service and terminates it.

Allows to cater for applications that take longer to deploy/tear-down.

After Lifecycle Hooks are added to the instance:
* ASG responds to scale-out/scale-in events
* LCH puts instance into `pending:wait`/`terminating:wait` state, instance is paused until we continue or timeout
* Custom actions are performed through one or more of these options:
  * CloudWatch Event target to invoke Lambda function
  * Notification target for LCH is defined
  * Script on instance runs as instance starts, script can control lifecycle actions
* Going into `pending:proceed`/`terminating:proceed` after that.
* By default, the instance remains in a wait state for one hour, and then the Auto Scaling group
  continues the launch or terminate process

<a name="3_3_2_6"></a>
#### [↖](#3_3)[↑](#3_3_2_5)[↓](#3_3_3) Scaling

Scaling is the ability to increase or decrease the compute capacity of your application. Scaling
starts with an event, or scaling action, which instructs an Auto Scaling group to either launch or
terminate Amazon EC2 instances.

Options:
* Manual scaling
  * Specify min/max/desired
* Scheduled scaling
  * Specify time and date
* Dynamic based on demand
  * Create Scaling Policies
    * With *simple* and *step* scaling policies, you choose scaling metrics and threshold values for the CloudWatch alarms that trigger the scaling process.
    * We recommend that you use step scaling policies instead of simple scaling policies, even if you have a single scaling adjustment
    * After a scaling activity is started, the policy continues to respond to additional alarms, even while a scaling activity or health check replacement is in progress.
    * Therefore, all alarms that are breached are evaluated by Amazon EC2 Auto Scaling as it receives the alarm messages.
    * However, scaling actions from previous alarms are taken into account (thereby not changing the absolute outcome of the scaling action)
  * Trigger via Cloudwatch Alarms
* Predictive scaling
  * AWS using data collection from actual EC2 usage

<a name="3_3_3"></a>
### [↖](#3_3)[↑](#3_3_2_6)[↓](#3_3_4) CLI/API/SDK

```
aws autoscaling create-launch-configuration
```
```
https://autoscaling.amazonaws.com/?Action=CreateLaunchConfiguration
```
```
create_launch_configuration(**kwargs)
```

<a name="3_3_4"></a>
### [↖](#3_3)[↑](#3_3_3)[↓](#3_3_4_1) Troubleshooting

<a name="3_3_4_1"></a>
#### [↖](#3_3)[↑](#3_3_4)[↓](#3_3_4_2) Possible Problems

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

<a name="3_3_4_2"></a>
#### [↖](#3_3)[↑](#3_3_4_1)[↓](#3_4) Suspending ASG processes

You can suspend and then resume one or more of the scaling processes for your Auto Scaling group.
This can be useful for investigating a configuration problem or other issues with your web
application and making changes to your application without invoking the scaling processes.

.|.
-|-
`Launch`|Disrupts other processes as no more scale out
`Terminate`|Disrupts other processes as no more scale in
`HealthCheck`|.
`ReplaceUnhealthy`|.
`AZRebalance`|.
`AlarmNotification`|Suspends actions normally triggered by alarms
`ScheduledAction`|.
`AddToLoadBalancer`|.

---

<a name="3_4"></a>
## [↖](#top)[↑](#3_3_4_2)[↓](#3_4_1) External Tools
<!-- toc_start -->
* [Jenkins](#3_4_1)
  * [Integrating into CodePipeline](#3_4_1_1)
  * [Plugins](#3_4_1_2)
<!-- toc_end -->

<a name="3_4_1"></a>
### [↖](#3_4)[↑](#3_4)[↓](#3_4_1_1) Jenkins

* Can replace CodeBuild, CodePipeline, CodeDeploy
	* Tight integration with those services

* Master/Slave setup
	* Master/slaves can run on the same instance, but usually run on separate instances
	* Can have multiple masteer with respective set of slaves assigned to them
* Must managage Multi-AZ, deploy on EC2, ...
* `Jenkinsfile` to configure CI/CD
* Many AWS plugins

<a name="3_4_1_1"></a>
#### [↖](#3_4)[↑](#3_4_1)[↓](#3_4_1_2) Integrating into CodePipeline

* CodePipeline can send build jobs to Jenkins instead of CodeBuild
* Jenkins can pull from CodeCommit and eg. upload build result to ECR, invoke Lambda, ...
* Direct Jenkins support in CodePipeline, requires *CodePipeline-plugin* on the Jenkins end

<a name="3_4_1_2"></a>
#### [↖](#3_4)[↑](#3_4_1_1)[↓](#4) Plugins

* *EC2-Plugin*
	* Allows Jenkins to start agents on EC2 on demand, and kill them as they get unused.
	* Also support spot instances
* *CodeBuild-Plugin*
	* Send builds to CodeBuild
	* Official AWS plugin
* *ECS-Plugin*
	* Launch slaves into ECS

---

<a name="4"></a>
# [↖](#top)[↑](#3_4_1_2)[↓](#4_1) Services

<a name="4_1"></a>
## [↖](#top)[↑](#4)[↓](#4_1_1) API Gateway
<!-- toc_start -->
* [Overview](#4_1_1)
  * [Benefits](#4_1_1_1)
* [Concepts](#4_1_2)
  * [Endpoint](#4_1_2_1)
  * [Stage](#4_1_2_2)
  * [Deployment](#4_1_2_3)
  * [Integration](#4_1_2_4)
  * [Mapping Template](#4_1_2_5)
  * [Model](#4_1_2_6)
  * [Throttling](#4_1_2_7)
<!-- toc_end -->

<a name="4_1_1"></a>
### [↖](#4_1)[↑](#4_1)[↓](#4_1_1_1) Overview
*Amazon API Gateway* is a fully managed service that makes it easy for developers to create, publish,
maintain, monitor, and secure APIs at any scale. With a few clicks in the AWS Management Console,
you can create REST and WebSocket APIs that act as a “front door” for applications to access data,
business logic, or functionality from your backend services, such as workloads running on Amazon
Elastic Compute Cloud (Amazon EC2), code running on AWS Lambda, any web application, or real-time
communication applications.

<a name="4_1_1_1"></a>
#### [↖](#4_1)[↑](#4_1_1)[↓](#4_1_2) Benefits
* **RESTful** or **Websocket** APIs
* Powerful, flexible **authentication** mechanisms, such as AWS Identity and Access Management policies,
  Lambda authorizer functions, and Amazon Cognito user pools.
* **Developer portal** for publishing your APIs.
* **Canary release deployments** for safely rolling out changes.
* *CloudTrail* logging and monitoring of API usage and API changes.
* *CloudWatch* access logging and execution logging, including the ability to set alarms.
* Ability to use *AWS CloudFormation* templates to enable API creation
* Support for custom domain names.
* Integration with *AWS WAF* for protecting your APIs against common web exploits.
* Integration with *AWS X-Ray* for understanding and triaging performance latencies.

<a name="4_1_2"></a>
### [↖](#4_1)[↑](#4_1_1_1)[↓](#4_1_2_1) Concepts

<a name="4_1_2_1"></a>
#### [↖](#4_1)[↑](#4_1_2)[↓](#4_1_2_2) Endpoint
A hostname for an API in API Gateway that is deployed to a specific region. The hostname is of the
form `{api-id}.execute-api.{region}.amazonaws.com`.

The following types of API endpoints are supported:
* Regional - deployed to the specified region and intended to serve clients in the same AWS region.
* Edge Optimized - deployed to the specified region while using a *CloudFront distribution* to
  facilitate client access typically from across AWS regions
* Private - exposed through interface VPC endpoints

<a name="4_1_2_2"></a>
#### [↖](#4_1)[↑](#4_1_2_1)[↓](#4_1_2_3) Stage
A logical reference to a lifecycle state of your REST or WebSocket API (for example, `dev`, `prod`,
`beta`, `v2`).
* API stages are identified by API ID and stage name.
* Each stage has its own configuration parameters.
* Can be rolled back in history.
* Have *stage variables*, that are like environment variables for API Gateway.
  * Can be used to configure enpoints that the stage talks to.
  * Accessible from Lambda context as well.
* Can enable *canary deployments* for a stage (usually `PROD`)
  * Canaray releases attaches a new version to an existing stage deployment and randomly shift traffic over
  * Logs and metrics are generated separately for all canary requests
  * This is blue/green for API Gateway/Lambda

TODO: play with gateway stages, variables, lambda alias and versions

<a name="4_1_2_3"></a>
#### [↖](#4_1)[↑](#4_1_2_2)[↓](#4_1_2_4) Deployment
After creating your API, you *must* deploy it to make it callable by your users. To deploy an API,
you create an *API deployment* and associate it with a *stage*. Each stage is a snapshot of the API
and is made available for client apps to call.

<a name="4_1_2_4"></a>
#### [↖](#4_1)[↑](#4_1_2_3)[↓](#4_1_2_5) Integration
* *Lambda Proxy* - request is passed through straight to a lambda
  * Can point to an *alias* to enable canary testing
* *Lambda* - allows integration of *mapping template*
  * Can transform request as well as repsonse
  * Allows to evolve the API while keeping lambda function static
* Any service
  * All AWS services support dedicated APIs to expose their features. However, the application
  protocols or programming interfaces are likely to differ from service to service. An API Gateway
  API with the AWS integration has the advantage of providing a consistent application protocol
  for your client to access different AWS services.

<a name="4_1_2_5"></a>
#### [↖](#4_1)[↑](#4_1_2_4)[↓](#4_1_2_6) Mapping Template
A scripts in Velocity Template Language (VTL) that transforms a request body from the frontend
data format to the backend data format.

<a name="4_1_2_6"></a>
#### [↖](#4_1)[↑](#4_1_2_5)[↓](#4_1_2_7) Model
A data schema specifying the data structure of a request or response payload.

<a name="4_1_2_7"></a>
#### [↖](#4_1)[↑](#4_1_2_6)[↓](#4_2) Throttling
* Account-wide limit of 10,000 requests per second.
  * Applies at service/account level
* Can create *usage plan*:
  * *Rate*, *burst*, *quota*
  * Can assoicate with stage/method/API key (to limit certain clients)




---
<a name="4_2"></a>
## [↖](#top)[↑](#4_1_2_7)[↓](#4_2_1) CloudFormation
<!-- toc_start -->
* [Overview](#4_2_1)
* [Components](#4_2_2)
  * [Template](#4_2_2_1)
  * [Stacks](#4_2_2_2)
  * [Stack Sets](#4_2_2_3)
* [Concepts](#4_2_3)
  * [Running code on instance boot](#4_2_3_1)
  * [Custom Resources](#4_2_3_2)
  * [Drift detection](#4_2_3_3)
  * [Stacks Nesting](#4_2_3_4)
* [Limits](#4_2_4)
<!-- toc_end -->

<a name="4_2_1"></a>
### [↖](#4_2)[↑](#4_2)[↓](#4_2_2) Overview
*AWS CloudFormation* provides a common language for you to describe and provision all the
infrastructure resources in your cloud environment. CloudFormation allows you to use a simple text
file to model and provision, in an automated and secure manner, all the resources needed for your
applications across all regions and accounts. This file serves as the single source of truth for
your cloud environment.

AWS CloudFormation is available at no additional charge, and you pay only for the AWS resources
needed to run your applications.

* Allows to create and provision **resources** in a reusable **template** fashion
* Declarative - no need for ordering and orchestration
* Separation of concerns - different stacks for different purposes

Templates are uploaded to S3 and then referenced by CloudFormation.

<a name="4_2_2"></a>
### [↖](#4_2)[↑](#4_2_1)[↓](#4_2_2_1) Components

<a name="4_2_2_1"></a>
#### [↖](#4_2)[↑](#4_2_2)[↓](#4_2_2_1_1) Template

A *CloudFormation* template is a `JSON` or `YAML` formatted text file

Element|Comment
-|-
`AWSTemplateFormatVersion`|` 2010-09-09`
`Description`|.
`Metadata`|Details about the template
`Parameters`|Values to pass in right before template creation
`Mappings`|Maps keys to values (eg different values for different regions)
`Conditions`|Check values before deciding what to do
`Resources`|Creates resources - only mandatory section in a template
`Outputs`|Values to be exposed from the console or from API calls

##### Parameters

* Type: `String`, `Number`, `List`, `CommaDelimitedList`, AWS-specific types like `AWS::EC2::KeyPair::KeyName`, SSM-Parameter key (`AWS::SSM::Parameter`)
  * SSM *SecureString* is not supported
* *Description*, *Default Value*, *Allowed Values*, *Allowed Pattern*
* Validation: *regular expression* / *MinLength* / *MaxLength* / *MinValue* / *MaxValue*
* Can set `NoEcho` for secrets, will be masked with `****`
* *Pseudo parameters* are parameters that are predefined by AWS CloudFormation. You do not declare them in your template. Use them the same way as you would a parameter, as the argument for the Ref function.
  * `AWS::AccountId`, `AWS::NotificationARNs`, `AWS::NoValue`, `AWS::Partition`, `AWS::Region`, `AWS::StackId`, `AWS::StackName`, `AWS::URLSuffix`
* Reference a parameter within the template `!Ref myParam`
* Usage of parameters *might* make it hard to instantiate stacks

##### Mappings
* Fixed (hardcoded) variables within CloudFormation template
```
  RegionMap:
    us-east-1:
      HVM64: ami-0ff8a91507f77f867
      HVMG2: ami-0a584ac55a7631c0c
    us-west-1:
      HVM64: ami-0bdb828fd58c52235
      HVMG2: ami-066ee5fd4a9ef77f1
...
  myEC2Instance:
    Type: "AWS::EC2::Instance"
    Properties:
      ImageId: !FindInMap [RegionMap, !Ref "AWS::Region", HVM64]
```

##### Conditions
```
Conditions:
  CreateProdResources: !Equals [ !Ref EnvType, prod ]
```
* Can use (and combine) `Fn::And`, `Fn::Equals`, `Fn::If`, `Fn::Not`, `Fn::Or`

##### Resources
* Over 220 types of resources, `AWS::aws-product-name::data-type-name`
* AWS figures out creation, update and delete of resources for us
  * Update can impact a resource in 4 possible ways
    * *No interruption*
      * E.g. change `ProvisionedThroughput` of a DynamoDB table
    * *Some interruption*
      * E.g. change `InstanceType` of an EC2 instance
    * *Replacement*
      * E.g. change `AvailabilityZone` of an EC2 instance
      * E.g. change `ImageId` of an EC2 instance
      * E.g. change `Tablename` of a DynamoDB table
* Can toggle creation with `Condition`:
	```
	Resources:
		MountPoint:
		Type: "AWS::EC2:VolumeAttachment"
		Condition: CreateProdResources
	```

##### Outputs
* Can be
	* constructed value / parameter reference / pseudo parameter / output from a function like `fn::getAtt` or `Ref`
* Can be used in a different stack (*cross stack references*)
  * `!ImportValue NameOfTheExport`
  * Cannot delete stack if its outputs are used in another stack

##### Intrinsic Functions
* Used to pass in values that are not available until runtime
* Usable in `resources`, `outputs`, `metadata` attributes and `update policy` attributes (auto
scaling). You can also use intrinsic functions to conditionally create stack resources.
* Most intrinsic functions have a short and a long form (not `Ref`):
	* `Fn::GetAtt: [ logicalNameOfResource, attributeName ]`
	* `!GetAtt logicalNameOfResource.attributeName`

Name|Attributes|Description
-|-|-
`Ref`| *logicalName* | * Returns the *default* value of the specified *parameter*. For *resource* typically physical id
`Fn::Base64`| *valueToEncode* | * Provides encoding, converts from plain text into base64
`Fn::Cidr`| *ipBlock*, *count*, *cidrBits* | * Returns an array of CIDR address blocks. The number of CIDR blocks returned is dependent on the count parameter
`Fn::FindInMap`| *MapName*, *TopLevelKey*, *SecondLevelKey* | * Returns the value corresponding to keys in a two-level map that is declared in the *Mappings* section
`Fn::GetAtt`| *logicalNameOfResource*, *attributeName*| * Returns the value of an attribute from an object, either the default or the specified attribute<br/>* Object is either from the same or a nested template
`Fn::GetAZs`| *region*| * Returns an array that lists *Availability Zones* for a specified region<br/> * If region is omitted return AZs from the region the template is applied in
`Fn::If`| *boolean*, *string1*, *string2*| *	Returns `string1` if `boolean` is `true`, `string2` otherwise
`Fn::And`, `Fn::Equals`, `Fn::Or`, `Fn::Not`|.|* Good for `condition` element
`Fn::ImportValue`| *sharedValueToImport* | * Returns the value of an *Output* exported by another stacki<br/> * You can't delete a stack if another stack references one of its outputs.<br/> * You can't modify or remove an output value that is referenced by another stack.
`Fn::Join`| *delimiter*, [ *comma-delimited list of values* ] | * Joins a set of values into a single value separated by the specified delimiter
`Fn::Select`| *index*, *listOfObjects*| * Returns a single object from a list of objects by index
`Fn::Split`| *delimiter*, *source string* | * Split a string into a list of string values so that you can select an element from the resulting
`Fn::Sub`| - *String*<br/> - { *key*: *Value*, ... } | * Substitutes variables in an input string with values that you specify string list<br/>Also: `!Sub 'arn:aws:ec2:${AWS::Region}:${AWS::AccountId}:vpc/${vpc}'`
`Fn::Transform`| Name: *String*<br/> Parameters:<br/>   { *key*: *Value*, ... } | * Specifies a macro to perform custom processing on part of a stack template

<a name="4_2_2_2"></a>
#### [↖](#4_2)[↑](#4_2_2_1_6)[↓](#4_2_2_2_1) Stacks

* Related resources are managed in a single unit called a **stack**
	* All the resources in a stack are defined by the stack's *CloudFormation* template
	* Controls lifecycle of managed resources
	* Stack has `name` & `id`
  * Can be updated *directly* or via *change set*
  * Will **rollback** stack if it fails to create (can be disabled via API / console)
  * Possible to detect **stack drift**, if supported by created rersources
  * Can enable **termination protection**
* A **stack policy** is an *IAM*-style policy statements that governs who can do what

##### Stack Creation

###### Process
1. Template upload into S3 bucket
2. Template syntax check
    * CloudFormation will check for any IAM resources being created, and require `CAPABILITY_IAM`|
    `CAPABILITY_NAMED_IAM` if so
    * Will raise `InsufficientCapabilities` otherwise
3. Stack name & parameter verification & ingestion (apply default values)
4. Template processing & stack creation
	* **Resource ordering**
      * *Natural ordering*
        * CloudFormation knows about 'natural' dependencies between resources.
      * *DependsOn*
        * Also `DependsOn` attribute
        * Allows to direct *CloudFormation* on how to handle more complex dependencies
        * Applies to *creation* as well as *deletion* & *rollback*
        * `DependsOn` can be a single resource or a list of resources
        * Will error on circular dependencies
        * `DependsOn` is problematic if the target resource needs more complex setup than just stack creation
      * -> *Wait conditions* allow further control about what happens when
	* **Resource creation**
		* Will try to create as many resources as possible in parallel
		* Includes pausing and waiting for other resources to be created first
		* Associate the `CreationPolicy` attribute with a resource to prevent its status from reaching
		create complete until AWS CloudFormation receives a specified number of success signals or the
		timeout period is exceeded.
	* **Output creation**
5. Stack completion or rollback
	* Rollback settings can be provided while creating the stack
		* `onFailure` - `ROLLBACK` | `DELETE` | `DO_NOTHING`
    * Can try to manually resolve problems if in state `UPDATE_ROLLBACK_FAILED`

##### Stacks Updates

###### Process

* **Direct updates**
	* You submit changes and AWS CloudFormation immediately deploys them
* **Change sets**
	* You can preview the changes AWS CloudFormation will make to your stack, and then decide whether
	to apply those changes by executing the change set
	* *Change sets* are JSON-formatted documents that summarize the changes AWS CloudFormation will
	make to a stack
* Use the `UpdatePolicy` attribute to specify how AWS CloudFormation handles updates to the `AWS:
	AutoScaling::AutoScalingGroup`, `AWS::ElastiCache::ReplicationGroup`, `AWS::Elasticsearch::Domain`
	or `AWS::Lambda::Alias` resources.
	* Values depend on resource type, e.g. ASG replacing vs rolling update
* Use the `UpdateReplacePolicy` attribute to retain or (in some cases) backup the existing
	physical instance of a resource when it is replaced during a stack update operation.
* On Failure, the stack will rollback automatically to the last known working state

###### Interuption while updating
* Update can impact a resource in 4 possible ways
	* *No interruption*
		* E.g. change `ProvisionedThroughput` of a DynamoDB table
	* Some interruption
		* E.g. change `EbsOptimized` of an EC2 instance (EBS-backed)
		* E.g. change `InstanceType` of an EC2 instance (EBS-backed)
	* Replacement
		* E.g. change `AvailabilityZone` of an EC2 instance
		* E.g. change `ImageId` of an EC2 instance
		* E.g. change `Tablename` of a DynamoDB table
	* Deletion

##### Stack Policy

Defines which actions can be performed on specified resources. With CloudFormation stack policies
you can protect all or certain resources in your stacks from being unintentionally updated or
deleted during the update process.

* Check **stack policy** if updates are allowed
	* No policy present: All updates are allowed -> This differs from IAM default!
	* Once a policy is applied
		* It cannot be deleted
		* *All* resources that are not explicitely allowed are denied
		* Default deny can be explicitely overwritten
	* Policy format JSON
		* Contains *policy documents*
* Don't confuse with `DeletionPolicy`, `UpdatePolicy`, `UpdateRollbackPolicy` attributes

Element|.
-|-
`Effect`|.
`Principal`|*Must* be wildcard for stack policies
`Action`|`Update:Modify`,`Update:Replace`,`Update:Delete`,`Update:(wildcard)`
`Resource`,`NotResource`|.
`Condition`|Typically evaluates based on resource type

##### Stack Deletion

###### Process

* Specify the stack to delete, and AWS CloudFormation deletes the stack and all the resources in that stack.
* With the `DeletionPolicy` attribute you can preserve or (in some cases) backup a resource when its
stack is deleted.
* If AWS CloudFormation cannot delete a resource, the stack will not be deleted.
* A stack can have *termination protection* enabled, which will prevent it from being deleted accidentally

###### Resource deletion policy

* **Policy** / statement that is associated with every resource of a stack
* Controls what happens if stack is deleted
* `DeletionPolicy`
	* `Delete`
		* (default)
		* Creates transitive environment - immutable architecture
	* `Retain`
		* Obviously needs further cleanup - non-immutable architecture
	* `Snapshot`
		* Takes snapshot prior to deletion
		* Some resourcetypes only
			* `AWS::EC2::Volume`
			* `AWS::ElastiCache::CacheCluster`
			* `AWS::ElastiCache::ReplicationGroup`
			* `AWS::Neptune::DBCluster`
			* `AWS::RDS::DBCluster`
			* `AWS::RDS::DBInstance`
			* `AWS::Redshift::Cluster`
		* Allow data recovery at a later stage

<a name="4_2_2_3"></a>
#### [↖](#4_2)[↑](#4_2_2_2_4_2)[↓](#4_2_2_3_1) Stack Sets

A *stack set* lets you create stacks in AWS accounts across regions by using a single AWS
CloudFormation template. All the resources included in each stack are defined by the stack set's
AWS CloudFormation template. As you create the stack set, you specify the template to use, as well
as any parameters and capabilities that template requires.

##### Concept

* Stack sets are created in a region of an administrator account
* A *stack instance* is a reference to a stack in a target account within a region
  * Can exist without a stack, e.g. if stack failed to create, than the stack instance shows the reason for that
* Operations: *Create*, *Update*, *Delete*
* Operation options:
  * *Maximum concurrent accounts* - maximum number or percentage of target accounts in which an operation is performed at one time
  * *Failure tolerance* - maximum number or percentage of stack operation failures that can occur,
    per region, beyond which AWS CloudFormation stops an operation automatically
  * *Retain stack* (delete operations only) - keep stacks and their resources running even after
    they have been removed from a stack set

<a name="4_2_3"></a>
### [↖](#4_2)[↑](#4_2_2_3_1)[↓](#4_2_3_1) Concepts

<a name="4_2_3_1"></a>
#### [↖](#4_2)[↑](#4_2_3)[↓](#4_2_3_1_1) Running code on instance boot

.|.
-|-
`cfn-init`|Use to retrieve and interpret resource metadata, install packages, create files, and start services.
`cfn-signal`|Use to signal with a CreationPolicy or WaitCondition, so you can synchronize other resources in the stack when the prerequisite resource or application is ready.
`cfn-get-metadata`|Use to retrieve metadata for a resource or path to a specific key.
`cfn-hup`|Use to check for updates to metadata and execute custom hooks when changes are detected.

##### Define code and scripts to run

**CloudFormation User Data**
* Scripts and commands to be passed to a launching EC2 instance.
* Failing user data scripts don't fail the CFN stack
* Logged to `/var/log/cloud-init-output.log`
* Needs to be base64-encoded
```
UserData:
  Fn::Base64: |
        #!/bin/bash -x
        ...
```
`cfn-init`
* Use the AWS::CloudFormation::Init type to include *metadata* on an Amazon EC2 instance for the cfn
  init helper script. If your template calls the `cfn-init` script, the script looks for resource
  metadata rooted in the `AWS::CloudFormation::Init` metadata key.
* Different sections: `packages`, `groups`, `users`, `sources`, `files`, `commands`, `services`
* Need to make sure `aws-cfn-bootstrap` is in place und up to date
* Logged to `/var/log/cfn-init.log`
* Can use *WaitCondition*/`cfn-signal` to make CloudFormation wait for successful finish of code

* By default, user data scripts and cloud-init directives run only during the boot cycle when you first launch an instance.
* Can use `cfn-hup` to detect changes in resource metadata and run user-specified actions when a change is detected
* Use `cfn-get-metadata` to fetch a metadata block from AWS CloudFormation and print it to standard out

##### Signal outcome of installation back to CFN

**Creation Policy**
* Can (only) be used for *EC2 Instances* and *AutoscalingGroup*
* Creation policy definion
  * Defines desired signal count & waiting period
* Signal configuration
  * Call to `cfn-signal` from EC2 user-data
```
AutoScalingGroup:
  Type: AWS::AutoScaling::AutoScalingGroup
  Properties:
    ...
  CreationPolicy:
    ResourceSignal:
      Count: '3'
      Timeout: PT15M

LaunchConfig:
  Type: AWS::AutoScaling::LaunchConfiguration
  Properties:
    ...
    UserData:
      "Fn::Base64":
        !Sub |
          #!/bin/bash -xe
          yum update -y aws-cfn-bootstrap
          /opt/aws/bin/cfn-signal -e $? --stack ${AWS::StackName} --resource AutoScalingGroup --region ${AWS::Region}
```
**Wait Conditions and Handlers**
* For other resources (*external* to the stack)
* Wait condition handler
  * *CloudFormation* resource with no properties
  * Generates *signed URL* to communicate success or failure
  * URL can be used by `cfn-signal` to send data to
    * Takes custom data as well
* Wait condition
  * Links handler and resource
    * Know which resource they depend on
    * Hold reference to handler
    * Have response timeout
    * Have a desired count (defaults to 1)
  * Allows to define complex wait order
```
WebServerGroup:
  Type: AWS::AutoScaling::AutoScalingGroup
  Properties:
    ...
WaitHandle:
  Type: AWS::CloudFormation::WaitConditionHandle
WaitCondition:
  Type: AWS::CloudFormation::WaitCondition
  DependsOn: "WebServerGroup"
  Properties:
    Handle:
      Ref: "WaitHandle"
    Timeout: "300"
    Count:
      Ref: "WebServerCapacity"
```
<a name="4_2_3_2"></a>
#### [↖](#4_2)[↑](#4_2_3_1_2)[↓](#4_2_3_3) Custom Resources
* Problems with existing *CloudFormation* resources:
	* Sometimes lacks behind AWS services
	* Cannot deal with non-AWS resources
	* Cannot do much logic beyond the scope of intrinsic functions
	* Cannot interact with external services
* Solvable with custom resources:
	* Custom resource type that is backed by *SNS* or *Lambda*
		* `Type: Custom::NameOfResourceType`
		* `ServiceToken: arnOfSnsOrLambda`
	* If stack is *created*, *updated* or *deleted* a payload is sent to `ServiceToken`
		* Payload contains any custom data that's defined with the resource together with the action type
		* This invokes a *lambda* that performs any sort of custom action
    * Or an *SNS topic*, e.g. to communicate with on-prem resources
		* Returns outcome of operation back to *CloudFormation*, typically includes custom data as well

<a name="4_2_3_3"></a>
#### [↖](#4_2)[↑](#4_2_3_2)[↓](#4_2_3_4) Drift detection
* Can detect drift on an entire stack or on a particular resource
	* Not supported by all resources types
* CloudFormation
	* Compares the current stack configuration to the one specified in the template that was used to create or update the stack
	* Reports on any differences, providing you with detailed information on each one.

<a name="4_2_3_4"></a>
#### [↖](#4_2)[↑](#4_2_3_3)[↓](#4_2_4) Stacks Nesting
* *Resources* in a stack can be references by other stacks
* How to nest
	* Declare resources as `AWS::CloudFormation::Stack`
	* Point `TemplateURL` to S3 URL of nested stack
	* Use `Parameters` to provide the nested stack with input values (defaults will be used otherwise)
	* Output values of nested stack are returned to parent (root) stack
		* `!GetAtt nestedStack.Outputs.db_name`
* Benefits
	* Allows infrastructure to be split over many templates
	* Allows infrastructure reuse
	* Allows to workaround limitations like max resources or max template size
	* Considered best practice by AWS

<a name="4_2_4"></a>
### [↖](#4_2)[↑](#4_2_3_4)[↓](#4_3) Limits
.|.
-|-
Max stacks per region|200
Max templates per region|unlimited
Max template size (stored in S3)|460kB
Parameters per stack|60
Mappings per stack|100
Resources per stack|200
Outputs per stack|60

---

<a name="4_3"></a>
## [↖](#top)[↑](#4_2_4)[↓](#4_3_1) CloudTrail
<!-- toc_start -->
* [Overview](#4_3_1)
* [Concepts](#4_3_2)
  * [Event](#4_3_2_1)
* [Trail](#4_3_3)
<!-- toc_end -->

AWS CloudTrail is a service that enables governance, compliance, operational auditing, and risk
auditing of your AWS account. With CloudTrail, you can log, continuously monitor, and retain
account activity related to actions across your AWS infrastructure. CloudTrail provides event
history of your AWS account activity, including actions taken through the AWS Management Console,
AWS SDKs, command line tools, and other AWS services. This event history simplifies security
analysis, resource change tracking, and troubleshooting. In addition, you can use CloudTrail to
detect unusual activity in your AWS accounts. These capabilities help simplify operational
analysis and troubleshooting.

<a name="4_3_1"></a>
### [↖](#4_3)[↑](#4_3)[↓](#4_3_2) Overview

CloudTrail is enabled by default in every account. All activities in an AWS account are being
recorded as CloudTrail events.

<a name="4_3_2"></a>
### [↖](#4_3)[↑](#4_3_1)[↓](#4_3_2_1) Concepts

<a name="4_3_2_1"></a>
#### [↖](#4_3)[↑](#4_3_2)[↓](#4_3_3) Event

* JSON format, who did what (API calls).
* ~15min delay
* Stored for 90 days

<a name="4_3_3"></a>
### [↖](#4_3)[↑](#4_3_2_1)[↓](#4_4) Trail

* One region / all regions / organizatio-wide
* Store data in nominated S3 bucket, this can be encrypted as well
* Can also deliver and analyse events in a trail with CloudWatch Logs and CloudWatch Events
* Can validate integrity of log files using digest files
* Can deliver trails from multiple accounts into the same bucket
  * Change bucket policy to allow that

---

<a name="4_4"></a>
## [↖](#top)[↑](#4_3_3)[↓](#4_4_1) CloudWatch
<!-- toc_start -->
* [Overview](#4_4_1)
* [Concepts](#4_4_2)
  * [Logging](#4_4_2_1)
  * [Metrics & Alarms](#4_4_2_2)
* [Key metrics for EC2](#4_4_3)
* [Key metrics for Auto Scaling Group](#4_4_4)
* [Key metrics for ELB](#4_4_5)
* [Key metrics for ALB](#4_4_6)
* [Key metrics for NLB](#4_4_7)
<!-- toc_end -->

<a name="4_4_1"></a>
### [↖](#4_4)[↑](#4_4)[↓](#4_4_2) Overview

*Amazon CloudWatch* is a monitoring and management service built for developers, system operators,
site reliability engineers (SRE), and IT managers. CloudWatch provides you with data and
actionable insights to monitor your applications, understand and respond to system-wide
performance changes, optimize resource utilization, and get a unified view of operational health.
CloudWatch collects monitoring and operational data in the form of logs, metrics, and events,
providing you with a unified view of AWS resources, applications and services that run on AWS, and
on-premises servers. You can use CloudWatch to set high resolution alarms, visualize logs and
metrics side by side, take automated actions, troubleshoot issues, and discover insights to
optimize your applications, and ensure they are running smoothly.

* Access all your data from a single platform
* Easiest way to collect custom and granular metrics for AWS resources
* Visibility across your applications, infrastructure, and services
* Improve total cost of ownership
* Optimize applications and operational resources
* Derive actionable insights from logs

TODO: Cloudwatch Subscription.
https://aws.amazon.com/pt/blogs/architecture/central-logging-in-multi-account-environments/

<a name="4_4_2"></a>
### [↖](#4_4)[↑](#4_4_1)[↓](#4_4_2_1) Concepts

<a name="4_4_2_1"></a>
#### [↖](#4_4)[↑](#4_4_2)[↓](#4_4_2_2) Logging

**Logs**
* *Log events* are records of some activity recorded by the application or resource being monitored
* *Log streams* are sequences of log events from the same source
* *Log groups* are groups of log streams that share the same retention, monitoring, and access control settings
* *Metric filters* allow to extract metric observations from ingested events and transform them to data points in a CloudWatch metric
* *Retention settings* can be used to specify how long log events are kept in CloudWatch Logs

Logs can be exported to S3 for durable storage

<a name="4_4_2_2"></a>
#### [↖](#4_4)[↑](#4_4_2_1)[↓](#4_4_3) Metrics & Alarms

**Namespaces**
* Container for CloudWatch metrics
* Metrics in different namespaces are isolated from each other
* The AWS namespaces typically use the following naming convention: `AWS/service`

**Metrics**
* Metrics are the fundamental concept in CloudWatch.
* A metric represents a time-ordered set of *data points* that are published to CloudWatch.
* *High resolution metrics* down to 1 second
  * Higher resolution data automatically aggregates into lower resolution data
* Data is kept for 3h to 15m, depending on the metric resolution
* Available metrics are based on currently used service
* Not everything is available out of the box, e.g. no data on memory usage of EC2 instances
* Can also create *Custom Metrics*
  * Publish individual *data points* via AWS CLI or API
  * Exist only in the region where they were created
  * Expire after 15 months if no data is published
  * `aws cloudwatch put-metric-data --metric-name PageViewCount --namespace MyService --value 2 --timestamp 2016-10-20T12:00:00.000Z`

**Time Stamps**
* Each metric data point must be associated with a time stamp.
* Can be up to two weeks in the past and up to two hours into the future.

**Dimension**
* A dimension is a name/value pair that is part of the identity of a metric.
* You can assign up to 10 dimensions to a metric.
* Every metric has specific characteristics that describe it, and you can think of dimensions as categories for those characteristics.
* For example 'ec2 instance id'

**Statistics**
* Statistics are metric data aggregations over specified periods of time
* Average, Sum, Minimum, Maximum, Sample Count, pNN.NN (value of specified percentile)
* Can be computed for any time periods between 60-seconds and 1-day

**Period**
* The length of time associated with a specific Amazon CloudWatch statistic

**Aggregation**
* CloudWatch aggregates statistics according to the period length that you specify when retrieving statistics

**Alarms**
* Based on thresholds defined on metrics
* Can trigger *Lambda*, *SNS*, email, ...
* Can be added to dashboard
* *High resolution alarms* down to 10 seconds
* Takes place once, at a specific point in time
  * Disable with `mon-disable-alarm-actions` via CLI

**Events**
* Define actions on things that happened
* Define `cron`-based events
* Events are recorded constantly over time
  * *Targets* process events (Lambda, SNS, SQS, ...)
  * *Rules* match incoming events and route them to targets
  * E.g. CodeCommit automatically triggers CodePipeline on new commits

<a name="4_4_3"></a>
### [↖](#4_4)[↑](#4_4_2_2)[↓](#4_4_4) Key metrics for EC2

* EC2 metrics are based on what is exposed to the hypervisor.
* *Basic Monitoring* (default) submits values every 5 minutes, *Detailed Monitoring* every minute

Metric|Effect
-|-
`CPUUtilization`|The total CPU resources utilized within an instance at a given time.
`DiskReadOps`,<br/>`DiskWriteOps`|The number of read (write) operations performed on all instance store volumes. This metric is applicable for instance store-backed AMI instances.
`DiskReadBytes`,<br/>`DiskWriteBytes`|The number of bytes read (written) on all instance store volumes. This metric is applicable for instance store-backed AMI instances.
`NetworkIn`,<br/>`NetworkOut`|The number of bytes received (sent) on all network interfaces by the instance
`NetworkPacketsIn`,<br/>`NetworkPacketsOut`|The number of packets received (sent) on all network interfaces by the instance
`StatusCheckFailed`,<br/>`StatusCheckFailed_Instance`,<br/>`StatusCheckFailed_System`|Reports whether the instance has passed both/instance/system status check in the last minute.

* Can **not** monitor **memory usage**, **available disk space**, **swap usage**

**Setup**
* Install CloudWatch agent on EC2 instance
  * Old way: Cloudwatch monitoring scripts (perl-based)
* Adjust config files on instance

<a name="4_4_4"></a>
### [↖](#4_4)[↑](#4_4_3)[↓](#4_4_5) Key metrics for Auto Scaling Group

Metric|Effect
-|-
`GroupMinSize`|The minimum size of the Auto Scaling group.
`GroupMaxSize`|The maximum size of the Auto Scaling group.
`GroupDesiredCapacity`|The number of instances that the Auto Scaling group attempts to maintain.
`GroupInServiceInstances`|The number of instances that are running as part of the Auto Scaling group. This metric does not include instances that are pending or terminating.
`GroupPendingInstances`|The number of instances that are pending. A pending instance is not yet in service. This metric does not include instances that are in service or terminating.
`GroupStandbyInstances`|The number of instances that are in a Standby state. Instances in this state are still running but are not actively in service.
`GroupTerminatingInstances`|The number of instances that are in the process of terminating. This metric does not include instances that are in service or pending.
`GroupTotalInstances`|The total number of instances in the Auto Scaling group. This metric identifies the number of instances that are in service, pending, and terminating.

<a name="4_4_5"></a>
### [↖](#4_4)[↑](#4_4_4)[↓](#4_4_6) Key metrics for ELB

Metric|Effect
-|-
`Latency`|Time it takes to receive an response. Measure `max` and `average`
`BackendConnectionErrorr`|Number of not successfully established connections to registered instances, measure `sum` and look at difference between `min` and `max`
`SurgeQueueLength`|Total number of request waiting to get routed, look at `max` and `average`
`SpilloverCount`|Dropped requests because of exceeded surge queue. Look at `sum`
`HTTPCode_ELB_4XX`<br/>`HTTPCode_ELB_5XX`|The number of HTTP XXX server error codes that originate from the *load balancer*. This count does *not* include any response codes generated by the targets. Look at `sum`
`HTTPCode_Backend_2XX`...<br/>...`HTTPCode_Backend_5XX`|The number of HTTP XXX server error codes that originate from the *backend*. Look at `sum`
`RequestCount`|Number of completed requests
`HealthyHostCount`,`UnhealthyHostCount`|Self explainatory

* Elastic Load Balancing reports metrics only when requests are flowing through the load balancer. If there are requests flowing through the load balancer, Elastic Load Balancing measures and sends its metrics in 60-second intervals.

> spillover and surge queue give an indication of the ELB being overloaded

* Typically this means that the backend system cannot process requests as fast as they are coming in
  * Ideally load balance into an autoscaling group.

<a name="4_4_6"></a>
### [↖](#4_4)[↑](#4_4_5)[↓](#4_4_7) Key metrics for ALB

Metric|Effect
-|-
`RequestCount`|Number of completed requests
`HealthyHostCount`,`UnhealthyHostCount`|Self explainatory
`TargetResponseTime`|The time elapsed after the request leaves the load balancer until a response from the target is received.
`HTTPCode_ELB_3XX_Count`<br/>`HTTPCode_ELB_4XX_Count`<br/>`HTTPCode_ELB_5XX_Count`|The number of HTTP XXX server error codes that originate from the *load balancer*. This count does *not* include any response codes generated by the targets.

<a name="4_4_7"></a>
### [↖](#4_4)[↑](#4_4_6)[↓](#4_5) Key metrics for NLB

Metric|Effect
-|-
`processedbyte `|The total number of bytes processed by the load balancer, including TCP/IP headers.
`tcp_client_reset_count`|the total number of reset (rst) packets sent from a client to a target.
`tcp_elb_reset_count`|the total number of reset (rst) packets generated by the load balancer.
`tcp_target_reset_coun`|the total number of reset (rst) packets sent from a target to a client.
---

<a name="4_5"></a>
## [↖](#top)[↑](#4_4_7)[↓](#4_5_1) CodeBuild
<!-- toc_start -->
* [Overview](#4_5_1)
* [Benefits](#4_5_2)
* [Components](#4_5_3)
  * [How it works](#4_5_3_1)
  * [Buildspec](#4_5_3_2)
<!-- toc_end -->

<a name="4_5_1"></a>
### [↖](#4_5)[↑](#4_5)[↓](#4_5_2) Overview
*AWS CodeBuild* is a fully managed continuous integration service that compiles source code, Runs
tests, and produces software packages that are ready to deploy. With CodeBuild, you don’t need to
provision, manage, and scale your own build servers. CodeBuild scales continuously and processes
multiple builds concurrently, so your builds are not left waiting in a queue. You can get started
quickly by using prepackaged build environments, or you can create custom build environments that
use your own build tools. With CodeBuild, you are charged by the minute for the compute resources
you use.

<a name="4_5_2"></a>
### [↖](#4_5)[↑](#4_5_1)[↓](#4_5_3) Benefits
* Fully managed build service
	* Serverless
	* Leverages Docker under the hood
	* Can use own docker images
* Continuous scaling
* Extensible
  * Can use own build tools and runtimes
* Pay as you go
* Enables CI/CD
* Secure
	* Integrates with KMS, IAM, VPC and CloudTrail

<a name="4_5_3"></a>
### [↖](#4_5)[↑](#4_5_2)[↓](#4_5_3_1) Components
* Source code from CodeCommit, S3, GitHub, Bitbucket
* Build defined in `buildspec.yml`
  * Build timeouts up to 8h
  * Uses queue to process build jobs
* Cloudwatch integration
  * Logs (can also go to S3)
  * *Metrics* to monitor CodeBuild statistics
	* Can set up *Alarms* on top of those
  * Can schedule CloudWatch *Events*

<a name="4_5_3_1"></a>
#### [↖](#4_5)[↑](#4_5_3)[↓](#4_5_3_2) How it works

* CodeBuild is provided with a *build project*.
	* Defines how Codebuild runs
		* Source code location, build environment to use, build commands
* CodeBuild uses information from build project to create *build environment*
  * Build runs in container, in phases
  * `submitted`, `queued`, `provisioning`, `download_source`, `install`, `pre_build`, `build`, `post_build`, `upload_artifacts`, `finalizing`, `completed`
* Download source code into build environment, use *buildspec* to build
* If there is build output, upload to S3
* While build is running, the build environments sends information to CloudWatch and CodeBuild
	* Can also use console, CLI, SDK to retrieve information about runnign build

<a name="4_5_3_2"></a>
#### [↖](#4_5)[↑](#4_5_3_1)[↓](#4_6) Buildspec

```
version: 0.2

run-as: Linux-user-name

env:
  variables:
    key: "value"
  parameter-store:
    key: "value"
  exported-variables:
    - variable
  secrets-manager:
    key: secret-id:json-key:version-stage:version-id
  git-credential-helper: yes

proxy:
    upload-artifacts: yes
    logs: yes

phases:
  install:
    run-as: Linux-user-name
    runtime-versions:
      runtime: version
    commands:
      - command
    finally:
      - command
  pre_build:
    run-as: Linux-user-name
    commands:
      - command
    finally:
      - command
  build:
		as_above
  post_build:
		as_above
  reports:
	...
  artifacts:
	...
  secondary-artifacts:
	...
cache:
  paths:
    - path
```

* *Artifacts* are what is kept after the build has finished.
  * Uploaded to S3, encrypted by default
  * With default configuration, artifacts are overwritten each time
* Envrironment variables can come from SSM / Secrets-manager.

---

<a name="4_6"></a>
## [↖](#top)[↑](#4_5_3_2)[↓](#4_6_1) CodeCommit
<!-- toc_start -->
* [Overview](#4_6_1)
* [Benefits * Fully managed * Highly available * Faster development cycle * Code lives close to actual environments](#4_6_2)
* [How To](#4_6_3)
  * [Protect branches](#4_6_3_1)
  * [Send Notifications](#4_6_3_2)
  * [Trigger SNS / Lambda](#4_6_3_3)
<!-- toc_end -->

<a name="4_6_1"></a>
### [↖](#4_6)[↑](#4_6)[↓](#4_6_2) Overview
*AWS CodeCommit* is a fully-managed source control service that hosts secure Git-based repositories.
It makes it easy for teams to collaborate on code in a secure and highly scalable ecosystem.
CodeCommit eliminates the need to operate your own source control system or worry about scaling
its infrastructure. You can use CodeCommit to securely store anything from source code to binaries,
and it works seamlessly with your existing Git tools.

<a name="4_6_2"></a>
### [↖](#4_6)[↑](#4_6_1)[↓](#4_6_3) Benefits * Fully managed * Highly available * Faster development cycle * Code lives close to actual environments
* Secure
  * Encryption, IAM integration
* Collaborate on code
* Use existing tools
  * CodeBuild, Jenkins, other CI tools
* Fully enabled for automation
	* Provides notifacations and triggers for all repository events

<a name="4_6_3"></a>
### [↖](#4_6)[↑](#4_6_2)[↓](#4_6_3_1) How To

<a name="4_6_3_1"></a>
#### [↖](#4_6)[↑](#4_6_3)[↓](#4_6_3_2) Protect branches

Use IAM policy:

```
"Condition": {
		"StringEqualsIfExists": {
				"codecommit:References": [
						"refs/heads/master"
				]
		},
		"Null": {
				"codecommit:References": false
		}
}
```

<a name="4_6_3_2"></a>
#### [↖](#4_6)[↑](#4_6_3_1)[↓](#4_6_3_3) Send Notifications

Use CloudWatch Event Rules under the hood

* Set up notification / notification rules:
	* Pick triggering event (`on commit`, ..., `brunch updated`)
	* Pick SNS topic as target
	* Add subscriber to target

* Set up Cloudwatch Events directly:
	* Pick event *source* (AWS service)
	* Pick event *type* (different types, also includes CloudTrail)
	* Pick target (many different types, e.g. Lambda, SNS, SSM, Code*)

<a name="4_6_3_3"></a>
#### [↖](#4_6)[↑](#4_6_3_2)[↓](#4_7) Trigger SNS / Lambda

More limited in scope than Notifications. Do not us CloudWatch Events under the hood.

* Configure CodeCommit as Lambda trigger

---

<a name="4_7"></a>
## [↖](#top)[↑](#4_6_3_3)[↓](#4_7_1) CodeDeploy
<!-- toc_start -->
* [Overview](#4_7_1)
  * [Benefits](#4_7_1_1)
* [Components](#4_7_2)
  * [Application](#4_7_2_1)
  * [AppSpec](#4_7_2_2)
* [How it works](#4_7_3)
  * [Overview](#4_7_3_1)
  * [CloudWatch integration](#4_7_3_2)
  * [Rollback](#4_7_3_3)
  * [On-prem Deploys](#4_7_3_4)
  * [Lambda Deploys](#4_7_3_5)
<!-- toc_end -->

<a name="4_7_1"></a>
### [↖](#4_7)[↑](#4_7)[↓](#4_7_1_1) Overview
*AWS CodeDeploy* is a fully managed deployment service that automates software deployments to a
variety of compute services such as Amazon EC2, AWS Fargate, AWS Lambda, and your on-premises
servers. AWS CodeDeploy makes it easier for you to rapidly release new features, helps you avoid
downtime during application deployment, and handles the complexity of updating your applications.
You can use AWS CodeDeploy to automate software deployments, eliminating the need for error-prone
manual operations. The service scales to match your deployment needs.

* CodeDeploy can be chained into CodePipeline and can use artifacts from there
* CodeDeploy does not provision resources

<a name="4_7_1_1"></a>
#### [↖](#4_7)[↑](#4_7_1)[↓](#4_7_2) Benefits
* Automated deployments
  * EC2, on-prem, (ASG), ECS, (Fargate), Lambda
* Minimize downtime
* Centralized control
* Easy to adopt
* Integrates with AWS SAM

<a name="4_7_2"></a>
### [↖](#4_7)[↑](#4_7_1_1)[↓](#4_7_2_1) Components

<a name="4_7_2_1"></a>
#### [↖](#4_7)[↑](#4_7_2)[↓](#4_7_2_2) Application
  * *Deployment*
    * *Deployment Group*
      * Set of instances, defined by tags, e.g. 'environment=prod'
      * Can be associated with
        * CloudWatch Alarms that would stop the deployment if triggered
        * Triggers for notification
        * Rollbacks
    * *Deployment configuration*
      * `CodeDeployDefault.OneAtATime`, ..., `CodeDeployDefault.LambdaCanary10Percent10Minutes`
      * Can create own
        * Define _minimum healthy hosts_ by percentage or number
        * E.g. 9 instances in total, 6 minimum healthy hosts, deploy 3 at a time. Deployment is successful after 6 hosts have been successfully deployed

<a name="4_7_2_2"></a>
#### [↖](#4_7)[↑](#4_7_2_1)[↓](#4_7_3) AppSpec
* Slightly different format for EC2/ECS/Lambda.

* The content in the 'hooks' section of the AppSpec file varies, depending on the compute platform
for your deployment. The 'hooks' section for an EC2/On-Premises deployment contains mappings that
link deployment lifecycle event hooks to one or more *scripts*. The 'hooks' section for a Lambda or
an Amazon ECS deployment specifies *Lambda validation functions* to run during a deployment
lifecycle event.

* Environment variables are being exposed as well (e.g. `DEPLOYMENT_ID`, `DEPLOYMENT_GROUP_NAME`),
allow to implement logic in installation process.

```
version: 0.0
os: linux
files:
  - source: /
    destination: /var/www/html/WordPress
hooks:
  BeforeInstall:
    - location: scripts/install_dependencies.sh
      timeout: 300
      runas: root
  AfterInstall:
    - location: scripts/change_permissions.sh
      timeout: 300
      runas: root
  ApplicationStart:
    - location: scripts/start_server.sh
    - location: scripts/create_test_db.sh
      timeout: 300
      runas: root
  ApplicationStop:
    - location: scripts/stop_server.sh
      timeout: 300
      runas: root
```
<a name="4_7_3"></a>
### [↖](#4_7)[↑](#4_7_2_2)[↓](#4_7_3_1) How it works

<a name="4_7_3_1"></a>
#### [↖](#4_7)[↑](#4_7_3)[↓](#4_7_3_2) Overview
* CodeDeploy Agent continuously polls CodeDeploy
* CodeDeploy sends `appspec.yml`
* Application is pulled from S3 or github
* EC2 will run deploy instructions
  * *In-place* or *blue/green*
  * Run in phases `ApplicationStop`, `DownloadBundle`, `BeforeInstall`, `Install`, `AfterInstall`, `ApplicationStart`, `ValidateService`
* CodeDeploy Agent reports back success/failure

<a name="4_7_3_2"></a>
#### [↖](#4_7)[↑](#4_7_3_1)[↓](#4_7_3_3) CloudWatch integration
	* Events can report and notify other services
	* CloudWatch Log Agent on machine can push logs to CloudWatch
		* *No logs* for ECS / Lambda deploys
	* Deployment *triggers* can notify SNS
    * Can trigger based on *deployment* or *instance* events

<a name="4_7_3_3"></a>
#### [↖](#4_7)[↑](#4_7_3_2)[↓](#4_7_3_4) Rollback
* *Manual Rollback* by simply deploying a previous version
* *Automated Rollbacks*
	* Options
		* When deployment fails
			* Rollback when any deployments on any instance fails
		* When alarm thresholds are met
			* Add CloudWatch Alarm to deployment group
	* Can define `cleanup` file to help removing already installed files

<a name="4_7_3_4"></a>
#### [↖](#4_7)[↑](#4_7_3_3)[↓](#4_7_3_5) On-prem Deploys
* Configure each on-premise instance, register it with CodeDeploy, and then tag it.
	* Can create IAM User per instance
		* Needs configuration file with AK/SAK
		* Use `register` or `register-on-premises-instances` command
		* Best for only few instances
	* Can create IAM Role
		* Use `register-on-premises-instances` command together with STS token service
    * Needs credentials to call STS with
		* Best for many instances, also more secure
		* Setup more complicated
* Need to install CodeDeploy agent, obviously
* Deploy application revisions to the on-premises instance.
* On-prem instances cannot blue/green, as CodeDeploy cannot create new infrastructure

<a name="4_7_3_5"></a>
#### [↖](#4_7)[↑](#4_7_3_4)[↓](#4_8) Lambda Deploys
* Simpler `appspec`
* No source code uploads to S3 (?)
* Deploy Configuration options
	* *Canary* - deploy in 2 increments
	* *Linear* - deploy in many increments
	* *All-at-once*
* Lambda deploys a new *version* under an *alias*, and traffic is shifted between old and new version
	* (Versions and Aliases are native Lambda features)

--

<a name="4_8"></a>
## [↖](#top)[↑](#4_7_3_5)[↓](#4_8_1) CodePipeline
<!-- toc_start -->
* [Overview](#4_8_1)
  * [Benefits](#4_8_1_1)
  * [Components](#4_8_1_2)
  * [Pipeline Actions](#4_8_1_3)
* [Scenarios](#4_8_2)
<!-- toc_end -->

<a name="4_8_1"></a>
### [↖](#4_8)[↑](#4_8)[↓](#4_8_1_1) Overview
*AWS CodePipeline* is a fully managed continuous delivery service that helps you automate your
release pipelines for fast and reliable application and infrastructure updates. CodePipeline
automates the build, test, and deploy phases of your release process every time there is a code
change, based on the release model you define. This enables you to rapidly and reliably deliver
features and updates. You can easily integrate AWS CodePipeline with third-party services such as
GitHub or with your own custom plugin. With AWS CodePipeline, you only pay for what you use. There
are no upfront fees or long-term commitments.

<a name="4_8_1_1"></a>
#### [↖](#4_8)[↑](#4_8_1)[↓](#4_8_1_2) Benefits
* Rapid delivery
* Configurable workflow
* Get started fast
  * No CI/CD infastructue needs to be provisioned
* Easy to integrate
  * Plugin concept to integrate with other components

<a name="4_8_1_2"></a>
#### [↖](#4_8)[↑](#4_8_1_1)[↓](#4_8_1_3) Components

* **stage**
  * **action group** (run in sequence)
    * **action** (run in sequnece _or_ parallel)
      * Various *action providers* provide functionality
      * `runOrder` allows to decide about sequential and parallel

* Stages create *Artifacts*
  * Stored in S3, passed on to the next stage
    * *Default* setting for artifact store would create one bucket per pipe, can also specify *Custom* location
    * Store must be in the same region as pipeline
    * Always encrypted, default KMS or CMK
  * Artifacts are the way different pipeline stages 'communicate' with each other
  * CodePipelin artifacts are sightly different to CodeBuild artifacts

* Integrates with CloudWatch events

* Can invoke Lambda as an almost arbitrary pipeline action
	* `codepipeline:PutJobSuccessResult`, `codepipeline:PutJobFailureResult`

<a name="4_8_1_3"></a>
#### [↖](#4_8)[↑](#4_8_1_2)[↓](#4_8_2) Pipeline Actions

```
[
		{
			 "inputArtifacts": [
						An input artifact structure, if supported for the action category
				],
			 "name": "ActionName",
			 "region": "Region",
			 "namespace": "source_namespace",
			 "actionTypeId": {
						"category": "An action category",
						"owner": "AWS",
						"version": "1"
						"provider": "A provider type for the action category",
			 },
			 "outputArtifacts": [
						An output artifact structure, if supported for the action category
			 ],
			 "configuration": {
						Configuration details appropriate to the provider type
			 },
			 "runOrder": A positive integer that indicates the run order within the stage,
		}
]
```

* Source
  * S3
  * CodeCommit
    * -> Must have *one* pipeline *per* branch!
    * Change detection Cloudwatch (recommended), or CodePipeline (poll periodically)
    * Creates CloudWatch event rule in the background
  * Github
  * ECR
* Build
  * CodeBuild
  * Jenkins
  * TeamCity
  * etc
* Test
  * CodeBuild
  * Jenkins
  * Ghost Inspector
* Deploy
  * CodeDeploy
    * Can deploy into different region
  * CloudFormation
  * Beanstalk
  * ECS
	* ServiceCatalog
  * etc
* Invoke
  * Lambda
* Approval
  * SNS

<a name="4_8_2"></a>
### [↖](#4_8)[↑](#4_8_1_3)[↓](#4_9) Scenarios

CodePipeline with
* Amazon S3, AWS CodeCommit, and AWS CodeDeploy
* Third-party Action Providers (GitHub and Jenkins)
* AWS CodeStar to Build a Pipeline in a Code Project
* Compile, Build, and Test Code with CodeBuild
* Amazon ECS for Continuous Delivery of Container-Based Applications to the Cloud
* Elastic Beanstalk for Continuous Delivery of Web Applications to the Cloud
* AWS Lambda for Continuous Delivery of Lambda-Based and Serverless Applications
* AWS CloudFormation Templates for Continuous Delivery to the Cloud

---

<a name="4_9"></a>
## [↖](#top)[↑](#4_8_2)[↓](#4_9_1) CodeStar
<!-- toc_start -->
* [Overview](#4_9_1)
* [Benefits](#4_9_2)
* [Under the hood](#4_9_3)
<!-- toc_end -->

<a name="4_9_1"></a>
### [↖](#4_9)[↑](#4_9)[↓](#4_9_2) Overview
AWS CodeStar enables you to quickly develop, build, and deploy applications on AWS. AWS CodeStar
provides a unified user interface, enabling you to easily manage your software development
activities in one place. With AWS CodeStar, you can set up your entire continuous delivery
toolchain in minutes, allowing you to start releasing code faster. AWS CodeStar makes it easy for
your whole team to work together securely, allowing you to easily manage access and add owners,
contributors, and viewers to your projects. Each AWS CodeStar project comes with a project
management dashboard, including an integrated issue tracking capability powered by Atlassian JIRA
Software. With the AWS CodeStar project dashboard, you can easily track progress across your
entire software development process, from your backlog of work items to teams’ recent code
deployments.

<a name="4_9_2"></a>
### [↖](#4_9)[↑](#4_9_1)[↓](#4_9_3) Benefits

* Start developing on AWS in minutes
* Manage software delivery in one place
* Work across your team securely
* Choose from a variety of project templates

<a name="4_9_3"></a>
### [↖](#4_9)[↑](#4_9_2)[↓](#4_10) Under the hood

Uses `cfn-transform` to generate cfn from `template.yml`

---

<a name="4_10"></a>
## [↖](#top)[↑](#4_9_3)[↓](#4_10_1) Config
<!-- toc_start -->
* [Overview](#4_10_1)
<!-- toc_end -->

<a name="4_10_1"></a>
### [↖](#4_10)[↑](#4_10)[↓](#4_11) Overview
*AWS Config* is a service that enables you to assess, audit, and evaluate the configurations of your
AWS resources. Config continuously monitors and records your AWS resource configurations and
allows you to automate the evaluation of recorded configurations against desired configurations.
With Config, you can review changes in configurations and relationships between AWS resources,
dive into detailed resource configuration histories, and determine your overall compliance against
the configurations specified in your internal guidelines. This enables you to simplify compliance
auditing, security analysis, change management, and operational troubleshooting.

---

<a name="4_11"></a>
## [↖](#top)[↑](#4_10_1)[↓](#4_11_1) ECS
<!-- toc_start -->
* [Overview](#4_11_1)
  * [Benefits](#4_11_1_1)
* [Components](#4_11_2)
* [Autoscaling](#4_11_3)
* [Logging](#4_11_4)
* [ECR](#4_11_5)
* [Fargate](#4_11_6)
<!-- toc_end -->

<a name="4_11_1"></a>
### [↖](#4_11)[↑](#4_11)[↓](#4_11_1_1) Overview
*Amazon Elastic Container Service* (Amazon ECS) is a highly scalable, fast, container management
service that makes it easy to run, stop, and manage Docker containers on a cluster. You can host
your cluster on a serverless infrastructure that is managed by Amazon ECS by launching your
services or tasks using the Fargate launch type. For more control you can host your tasks on a
cluster of Amazon Elastic Compute Cloud (Amazon EC2) instances that you manage by using the EC2
launch type.

<a name="4_11_1_1"></a>
#### [↖](#4_11)[↑](#4_11_1)[↓](#4_11_2) Benefits
* Containers without servers
* Containerize Everything
* Secure
* Performance at Scale
* AWS Integration

<a name="4_11_2"></a>
### [↖](#4_11)[↑](#4_11_1_1)[↓](#4_11_3) Components

```
[Cluster
  [Service
    [Task Definition
      [Container Definition]
    ]
  ]
]
```

* **Task Definition**
  * ECS allows to run and maintain a specified number containers in a task definition
    * Group by responsility, e.g. separate task definitions for frontend and backend
  * The task definition is a text file, in JSON format, that describes one or more containers, up
    to a maximum of ten, that form your application
  * Specify various parameters, eg:
    * Container image to use
    * Port to be opened & networking
    * Data volumes
  * Either for ECS or Fargate
* **Task**
  * A *task* is the instantiation of a *task definition* within a cluster
  * If a task should fail or stop, the ECS scheduler launches another instance of the task
    definition to replace it and to maintain the desired count of tasks in service
  * Static host port mapping: Only one task per container instance allowed, e.g. mapping host port 80 to container port
  * Dynamic host port mapping: Uses randomized host ports, can work together with ALB to run multiple task instances per container instance
  * Tasks can have individual IAM roles
* **Service**
  * Runs and maintains a specified number of tasks simultaneously
  * Created on Cluster-Level, launch type EC2 or Fargate
  * Can be linked to ALB/NLB/ELB
  * *Service type*
    * *Replica* - places and maintains the desired number of tasks across your cluster
    * *Demon* - deploys exactly one task on each active container instance that meets all of the task placement constraints
      * Good for e.g. *monitoring* that should run on every container instance
  * *Deployment type*
    * *Rolling*
      * Controlled by Amazon ECS
      * Service scheduler replacing the current running version of the container with the latest version
    * *Blue/Green*
      * Controlled by CodeDeploy
      * Allows to verify a new deployment of a service before sending production traffic to it
* **Clusters**
  * Logical grouping of EC2 instances that you can place tasks on
  * Instances run ECS agent as a Docker container
  * Cluster is an *auto scaling group* with a launch configuration using a special ECS AMI

<a name="4_11_3"></a>
### [↖](#4_11)[↑](#4_11_2)[↓](#4_11_4) Autoscaling

* Use *Service Auto Scaling* for
  * Target Tracking Scaling Poilicy
  * Step Scaling Policy
  * Sdcheduled Scaling

* For ECS, we also need to scale the cluster
  * This is really tricky, but in essence there's an ASG around the EC2 instances that form the cluster
  * Could use Fargate, obviously
  * Or even Elastic Beanstalk

<a name="4_11_4"></a>
### [↖](#4_11)[↑](#4_11_3)[↓](#4_11_5) Logging

* For tasks, configure logging agent with task definition
  * Typically CloudWatch, also supports Splunk
* For cluster instances, install CloudWatch Agent
* Various ECS-specific CloudWatch metrics available
* Various ECS-specific CloudWatch events available
* Can enable CloudWatch Container Insights
  * Sends per-container metrics into CloudWatch metrics

<a name="4_11_5"></a>
### [↖](#4_11)[↑](#4_11_4)[↓](#4_11_6) ECR

* Needs login `aws ecr get-login --no-include-email --region ap-south-2`
* `docker pull aws_account_id.dkr.ecr.us-west-2.amazonaws.com/amazonlinux:latest`

<a name="4_11_6"></a>
### [↖](#4_11)[↑](#4_11_5)[↓](#4_12) Fargate

* Don't need to provision cluster
  * Does not need EC2 instance roles to create cluster
* Requires VPC

TODO: why do load balancers interfere in udemy example?
TODO: https://aws.amazon.com/blogs/devops/build-a-continuous-delivery-pipeline-for-your-container-images-with-amazon-ecr-as-source/

---

<a name="4_12"></a>
## [↖](#top)[↑](#4_11_6)[↓](#4_12_1) Elastic Beanstalk
<!-- toc_start -->
* [Overview](#4_12_1)
* [Concepts](#4_12_2)
  * [Components](#4_12_2_1)
  * [Configuration](#4_12_2_2)
  * [Deployment Types](#4_12_2_3)
* [Limits](#4_12_3)
<!-- toc_end -->

<a name="4_12_1"></a>
### [↖](#4_12)[↑](#4_12)[↓](#4_12_2) Overview
AWS Elastic Beanstalk is an easy-to-use service for deploying and scaling web applications and
services developed with `Java`, `.NET`, `PHP`, `Node.js`, `Python`, `Ruby`, `Go`, and `Docker` on familiar servers
such as Apache, Nginx, Passenger, and IIS.

You can simply upload your code and Elastic Beanstalk automatically handles the deployment, from
capacity provisioning, load balancing, auto-scaling to application health monitoring. At the same
time, you retain full control over the AWS resources powering your application and can access the
underlying resources at any time.

* Allows to *deploy*, *monitor* and *scale* applications quickly
* Focusses on components and performance, *not* configuration and specification
* Aims to simplify or even remove infrastructure management
* Provides different options for *low cost* and *high availability* quick starts
* Underlying *instances* can be automatically patched
* Platform-specific application *source bundle* (e.g. Java `war` for Tomcat)
  * Go
  * Java SE/with Tomcat
  * .NET on Windows Server with IIS
  * Node.js
  * PHP
  * Python
  * Ruby Stanalone/Puma
  * Docker Single-/Multicontainer - runs on ECS
  * Docker Preconfigured Glassfish/Python/Go

<a name="4_12_2"></a>
### [↖](#4_12)[↑](#4_12_1)[↓](#4_12_2_1) Concepts

<a name="4_12_2_1"></a>
#### [↖](#4_12)[↑](#4_12_2)[↓](#4_12_2_2) Components
* **Application**
  * Either *application* in the tradional sense
  * Or *application component*, e.g. service, frontend, backend
* **Environment**
  * Isolated, self-contained set of components of infrastructure
    * Type **Web server** environment
      * Represents a web application
    * Type **Worker** environment
      * Act upon output created by another environment - pulls work from SQS queue
      * Ideal for long running workloads
      * Should only be loosely coupled to web server environments, eg. via *SQS*
      * Can also be invoked on a schedule
  * Single-instance or multi-instance scalable
  * Application can have mulitple environments
    * Either represent *development stages* (PROD, STAGE, ...)
    * ...or *application component*, e.g. service, frontend, backend
  * Can be cloned as a whole environment
  * Can rebuild environment - complete delete and rebuild
* **Application Version**
  * Unique package that represents a version of the *application*
  * Uploaded as a zipped *application source bundle*
  * Each application can have many application versions
  * Can be deployed to one or more *environments* within an application
  * Limit of 1000 version -> can configure application version *lifecycle management*

*Web Application*<br/>(non-docker)|*Web Application*<br/>(docker, runs on ECS)|*Worker*
-|-|-
`AWS::AutoScaling::AutoScalingGroup`|`AWS::AutoScaling::AutoScalingGroup`|`AWS::CloudFormation::WaitConditionHandle`
`AWS::AutoScaling::LaunchConfiguration`|`AWS::AutoScaling::LaunchConfiguration`|`AWS::DynamoDB::Table`
`AWS::AutoScaling::ScalingPolicy`|`AWS::CloudFormation::WaitCondition`|`AWS::EC2::SecurityGroup`
`AWS::CloudFormation::WaitCondition`|`AWS::CloudFormation::WaitConditionHandle`|`AWS::SQS::Queue`
`AWS::CloudFormation::WaitConditionHandle`|`AWS::EC2::EIP`|.
`AWS::CloudWatch::Alarm`|`AWS::EC2::SecurityGroup`|.
`AWS::EC2::SecurityGroup`|.|.
`AWS::EC2::SecurityGroupIngress`|.|.
`AWS::ElasticLoadBalancing::LoadBalancer`|.|.

<a name="4_12_2_2"></a>
#### [↖](#4_12)[↑](#4_12_2_1)[↓](#4_12_2_2_1) Configuration
Configuration options, sorted by precedence:

##### Settings applied directly to the environment
Via console, eb-cli, ...

##### Existing configuration saved into `.elasticbeanstalk`
* Can you `eb config ...` to save/snapshot a configuration of an application
* Saved into `.elasticbeanstalk`
  * Only non-default values are being saved
* This can be modified, uploaded and applied
  * Good to backup existing applications
  * Can also be applied elsewhere, e.g. in a different region

##### `.ebextensions` in project
* *Folder* is part of application source bundle
* Allows granular configuration & customisation of the EB environment and its resources
* Contains `*.config` in *YAML* format with different sections like
	* `option_settings` - global configuration options
	* `resources` - specify additional resources, allows granular configuration of these
    * Put *CloudFormation* here, export *outputs* into beanstalk environment
    * Good for e.g. DDB table, SNS topic, ...
    * However, those resources are part of the *environemt* and would be deleted with it
      * If this is not desired, then create resources independently
      * Usually best for e.g. databases
	* `commands`
    * Execute on ec2 instance
    * Run before application and web server are being set up
	* `container_commands`
    * Affects application source code
    * Run after application archive has been extracted, but before application version has been
    deployed
    * Can use `leader_only` to only run on a single instance. E.g. migrate database
	* `packages`, `sources`, `files`, `users`, `groups`, `service`
* Applied with next `eb deploy`

##### Default values
As the name says.

<a name="4_12_2_3"></a>
#### [↖](#4_12)[↑](#4_12_2_2_4)[↓](#4_12_3) Deployment Types
* Single instance deploys
* HA with Load Balancer
  * All at once
  * Rolling update
  * Rolling with additional batches
  * Immutable
  * 'Blue/Green' - not really supported, however
    * Can manually create new environment
    * Either use *swap URL* feature or manually create DNS

<a name="4_12_3"></a>
### [↖](#4_12)[↑](#4_12_2_3)[↓](#4_13) Limits
.|.
-|-
Applications|75
Application Versions|1000
Configuration Templates|2000
Environments|200

---

<a name="4_13"></a>
## [↖](#top)[↑](#4_12_3)[↓](#4_13_1) Kinesis
<!-- toc_start -->
* [Overview](#4_13_1)
  * [Kinesis Data Stream](#4_13_1_1)
  * [Kinesis Data Firehose](#4_13_1_2)
  * [Kinesis Data Analytics](#4_13_1_3)
* [Limits](#4_13_2)
<!-- toc_end -->

Amazon Kinesis makes it easy to collect, process, and analyze real-time, streaming data so you can
get timely insights and react quickly to new information. Amazon Kinesis offers key capabilities
to cost-effectively process streaming data at any scale, along with the flexibility to choose the
tools that best suit the requirements of your application. With Amazon Kinesis, you can ingest real-time
data such as video, audio, application logs, website clickstreams, and IoT telemetry data
for machine learning, analytics, and other applications. Amazon Kinesis enables you to process and
analyze data as it arrives and respond instantly instead of having to wait until all your data is
collected before the processing can begin.

[`various data sources`]->`Kinesis Streams`->`Kinesis Analytics`->`Kinesis Firehose`->[`S3`]

<a name="4_13_1"></a>
### [↖](#4_13)[↑](#4_13)[↓](#4_13_1_1) Overview

<a name="4_13_1_1"></a>
#### [↖](#4_13)[↑](#4_13_1)[↓](#4_13_1_2) Kinesis Data Stream
* Real-time data delivery
* Streams are devided into ordered *shards*/*partitions*
  * Shards can evolve over time (reshard/merge)
  * Records are ordered per shard (but not across shards)
* Data retention is 1 day (default), up to 7 days
* Ability to process/replay data
  * Real-time processing
* Multiple applications can consume the same stream
* Once date is inserted into Kinesis, it can't be deleted (immutability)
* *Records*
  * `Data Blob`, up to 1MB
  * `Record Key` - helps grouping into shards, should be highly distributed
  * `Sequence Number` - unique identifier for each record put into shards
* Producers
  * Kinesis SDK, Kinesis Producer Library (KPL), Kinesis Agent, Cloudwatch Logs
  * 3rd party libraries: Spark, Log4j Appenders, ...
* Consumers
  * Kinesis SDK, Kinesis Client Library (KCL), Kinesis Connector Library, AWS Lambda
  * 3rd party libraries: Spark, Log4j Appenders, ...

<a name="4_13_1_2"></a>
#### [↖](#4_13)[↑](#4_13_1_1)[↓](#4_13_1_3) Kinesis Data Firehose
* Near Real-time data delivery (~60 seconds)
* Automatic Scaling
* Can do data transformation through Lambda
* Supports compression for S3
* Pay for the amount of data going through Firehose
* Producers
  * Kinesise Data Streams, Cloudwatch Logs & Events, ...
* Consumers (data receivers)
  * Redshift, S3, ElasticSearch, Splunk

Kinesis Data Streams|Kinesis Firehose
-|-
Must manage scaling|Fully managed
Real time | Near real time
Data storage| No data storage
Can write custom code for consumers/producers| Serverless lambda

For _real time delivery_ Kinesis data streams are the only option.

<a name="4_13_1_3"></a>
#### [↖](#4_13)[↑](#4_13_1_2)[↓](#4_13_2) Kinesis Data Analytics

* Performing real time analytics on Kinesis Streams using SQL
* Managed, auto-scaling
* Can create Kinesis Streams in real-time

<a name="4_13_2"></a>
### [↖](#4_13)[↑](#4_13_1_3)[↓](#4_14) Limits
.|.|..
-|-|-
**Kinesis Streams**|.|.
.|Producer|1MB/s or 1000 messages/s write per shard (->`ProvisionedThroughputException`)
.|Consumer Classic|2MB/s write per shard
.|.|5 API calls per second per shard
.|Data Retentions|7 days

---

<a name="4_14"></a>
## [↖](#top)[↑](#4_13_2)[↓](#4_14_1) Lambda
<!-- toc_start -->
* [Overview](#4_14_1)
* [Managing Functions](#4_14_2)
  * [Versions](#4_14_2_1)
  * [Aliases](#4_14_2_2)
  * [Layers](#4_14_2_3)
  * [Network](#4_14_2_4)
  * [Database](#4_14_2_5)
* [Invoking Functions](#4_14_3)
  * [Synchronous / Asynchronous / Event Source Invocation](#4_14_3_1)
  * [Function Scaling](#4_14_3_2)
<!-- toc_end -->

<a name="4_14_1"></a>
### [↖](#4_14)[↑](#4_14)[↓](#4_14_2) Overview
*AWS Lambda* lets you run code without provisioning or managing servers. You pay only for the
compute time you consume - there is no charge when your code is not running. With Lambda, you can
run code for virtually any type of application or backend service - all with zero administration.
Just upload your code and Lambda takes care of everything required to run and scale your code with
high availability. You can set up your code to automatically trigger from other AWS services or
call it directly from any web or mobile app.

* Features
  * No
  servers
  * Continuous scaling
    * Cold Start - if no idle container is available to run the lambda
  * Very cheap
  * Can give more RAM which will proportionaly increase CPU as well
* Supported languages
  * `nodejs`, `Java`, `C#/PowerShell`, `Python`, `Golang`, `Ruby`
* Can pass in *environment variables*
  * These can be KMS-encrypted as well (need SDK to decrypt)

<a name="4_14_2"></a>
### [↖](#4_14)[↑](#4_14_1)[↓](#4_14_2_1) Managing Functions
`triggers` -> `function & layers` -> `destinations`

<a name="4_14_2_1"></a>
#### [↖](#4_14)[↑](#4_14_2)[↓](#4_14_2_2) Versions
* If you work on a Lambda function, you work on `$LATEST`
* The system creates a new version of your Lambda function each time that you publish the function.
  The new version is a copy of the unpublished version of the function.
* Version is code *and* configuration
* Versions are immutable, you can change the function code and settings only on the unpublished
  version of a function.
* Each version gets its own ARN

<a name="4_14_2_2"></a>
#### [↖](#4_14)[↑](#4_14_2_1)[↓](#4_14_2_3) Aliases
* You can create one or more aliases for your AWS Lambda function. A Lambda alias is like a pointer
to a specific Lambda function *version*.
* Aliases are mutable
* Users can access the function version using the alias ARN.
* Can create e.g. `dev`, `test` and `prod`.
  * Aliases can point to multiple versions with a *weight* - for canary-style deployments

<a name="4_14_2_3"></a>
#### [↖](#4_14)[↑](#4_14_2_2)[↓](#4_14_2_4) Layers
* You can configure your Lambda function to pull in additional code and content in the form of layers.
* A layer is a ZIP archive that contains libraries, a custom runtime, or other dependencies.
* With layers, you can use libraries in your function without needing to include them in your deployment package.

<a name="4_14_2_4"></a>
#### [↖](#4_14)[↑](#4_14_2_3)[↓](#4_14_2_5) Network
* You can configure a function to connect to private subnets in a VPC in your account.
* Use VPC to create a private network for resources such as databases, cache instances, or internal services.
* Connect your function to the VPC to access private resources during execution.
* Provisioning process for Lambda takes longer

<a name="4_14_2_5"></a>
#### [↖](#4_14)[↑](#4_14_2_4)[↓](#4_14_3) Database
* You can use the Lambda console to create an RDS database proxy for your function.
* A database proxy manages a pool of database connections and relays queries from a function.
* This enables a function to reach high concurrency levels without exhausting database connections.

<a name="4_14_3"></a>
### [↖](#4_14)[↑](#4_14_2_5)[↓](#4_14_3_1) Invoking Functions

<a name="4_14_3_1"></a>
#### [↖](#4_14)[↑](#4_14_3)[↓](#4_14_3_2) Synchronous / Asynchronous / Event Source Invocation
* When you invoke a function **synchronously**, Lambda runs the function and waits for a response.
  * -> API Gateway, ALB, Cognito, Lex, Alexa, CloudFront (Lambda@Edge), Kinesis Data Firehose
* When you invoke a function **asynchronously**, Lambda sends the event to a queue. A separate
process reads events from the queue and runs your function.
  * Lambda manages the function's asynchronous invocation queue and attempts to retry failed
  events automatically. If the function returns an error, Lambda attempts to run it two more times
  * When all attempts to process an asynchronous invocation fail, Lambda can send the event to an
  Amazon SQS queue or an Amazon SNS topic.
  * -> S3, SNS, SES, CloudFormation, Cloudwatch Logs & Events, CodeCommit, Config
* An **event source mapping** is an AWS Lambda resource that reads from an event source and invokes a Lambda function.
  * -> Kinesis, DynamoDB, SQS

<a name="4_14_3_2"></a>
#### [↖](#4_14)[↑](#4_14_3_1)[↓](#4_15) Function Scaling
* The first time you invoke your function, AWS Lambda creates an instance of the function and runs
its handler method to process the event.
  * When the function returns a response, it sticks around to process additional events.
  * If you invoke the function again while the first event is being processed, Lambda creates another instance.
  * This continues until there are enough instances to serve all requests, or a concurrency limit is reached.
  * When the number of requests decreases, Lambda stops unused instances to free up scaling capacity for other functions.
* **Concurrency** is `invocations/s * runtime` (eg. 10/s * 4s = 40)
  * Can configure *reservered concurrency*
    * No other function can use that concurrency
  * Can configure *provisioned concurrency* before an increase in invocations
    * Can ensure that all requests are served by initialized instances with very low latency.

---

<a name="4_15"></a>
## [↖](#top)[↑](#4_14_3_2)[↓](#4_15_1) Managed Services
<!-- toc_start -->
* [Overview](#4_15_1)
<!-- toc_end -->

<a name="4_15_1"></a>
### [↖](#4_15)[↑](#4_15)[↓](#4_16) Overview
As enterprise customers move towards adopting the cloud at scale, some find their people need help
and time to gain AWS skills and experience. AWS Managed Services (AMS) operates AWS on your behalf,
providing a secure and compliant AWS Landing Zone, a proven enterprise operating model, on-going
cost optimization, and day-to-day infrastructure management. By implementing best practices to
maintain your infrastructure, AWS Managed Services helps to reduce your operational overhead and
risk. AWS Managed Services automates common activities, such as change requests, monitoring, patch
management, security, and backup services, and provides full-lifecycle services to provision, run,
and support your infrastructure. AWS Managed Services unburdens you from infrastructure operations
so you can direct resources toward differentiating your business.

---

<a name="4_16"></a>
## [↖](#top)[↑](#4_15_1)[↓](#4_16_1) OpsWorks Stacks
<!-- toc_start -->
* [Overview](#4_16_1)
* [Components](#4_16_2)
* [Lifecycle Events](#4_16_3)
  * [Setup](#4_16_3_1)
  * [Configure](#4_16_3_2)
  * [Deploy](#4_16_3_3)
  * [Undeploy](#4_16_3_4)
  * [Shutdown](#4_16_3_5)
* [Under the hood](#4_16_4)
<!-- toc_end -->

<a name="4_16_1"></a>
### [↖](#4_16)[↑](#4_16)[↓](#4_16_2) Overview
*AWS OpsWorks* is a configuration management service that provides managed instances of Chef and
Puppet. Chef and Puppet are automation platforms that allow you to use code to automate the
configurations of your servers. OpsWorks lets you use Chef and Puppet to automate how servers are
configured, deployed, and managed across your Amazon EC2 instances or on-premises compute
environments.

* Declarative desired state engine
  * Automate, monitor and maintain deployments
* AWS' implementation of *Chef*
	* Original Chef
	* AWS-bespoke orchestration components
  * **Cookbooks** define **recipes**
* OpsWorks has three offerings:
  * *AWS OpsWorks Stacks* (`<- exam relevant`)
  * *AWS Opsworks for Chef Automate*
  * *AWS OpsWorks for Puppet Enterprise*

<a name="4_16_2"></a>
### [↖](#4_16)[↑](#4_16_1)[↓](#4_16_3) Components
* **Stack**
  * Set of resources that are managed as a group
* **Layer**
  * Represent and configure components of a stack
  * Share common configuration elements
  * E.g. loadbalancer layer, app layer, db layer
  * Type: *OpsWorks*, *ECS* or *RDS*
* **Instance**
  * Units of compute within the platform
  * Must be associated with at least one layer
  * Can run
    * 24/7
    * Load-based
    * Time-based
  * Servers have to exist and to be pre-assigned to be e.g. load-based. So they are *not* created on demand.
* **Application**
  * Applications that are deployed on one or more instances
  * Deployed through source code repo or S3
* **Deployments**
  * Deploy application code and related files to application server instances
  * Deployment operation is handled by each instance's Deploy recipes, which are determined by the instance's layer

<a name="4_16_3"></a>
### [↖](#4_16)[↑](#4_16_2)[↓](#4_16_3_1) Lifecycle Events
* **Each layer** has a set of five lifecycle events, each of which has an associated set of recipes that are specific to the layer
* When an event occurs on a layer's instance, AWS OpsWorks Stacks automatically runs the appropriate set of recipes

<a name="4_16_3_1"></a>
#### [↖](#4_16)[↑](#4_16_3)[↓](#4_16_3_2) Setup
* Occurs after a started instance has finished booting

<a name="4_16_3_2"></a>
#### [↖](#4_16)[↑](#4_16_3_1)[↓](#4_16_3_3) Configure
* Occurs on *all* of the stack's instances when one of the following occurs:
    * An instance enters or leaves the online state.
    * You associate an Elastic IP address with an instance or disassociate one from an instance.
    * You attach an Elastic Load Balancing load balancer to a layer, or detach one from a layer.

<a name="4_16_3_3"></a>
#### [↖](#4_16)[↑](#4_16_3_2)[↓](#4_16_3_4) Deploy
* Occurs when you run a *Deploy* command.

<a name="4_16_3_4"></a>
#### [↖](#4_16)[↑](#4_16_3_3)[↓](#4_16_3_5) Undeploy
* Occurs when you run a *Undeploy* command,

<a name="4_16_3_5"></a>
#### [↖](#4_16)[↑](#4_16_3_4)[↓](#4_16_4) Shutdown
* Occurs after you direct AWS OpsWorks Stacks to shut an instance down but before the associated Amazon EC2 instance is actually terminated.

<a name="4_16_4"></a>
### [↖](#4_16)[↑](#4_16_3_5)[↓](#4_17) Under the hood
* CloudWatch event integration
  * Can configure event rules to trigger alarms
* Under the hood
	* *OpsWorks* **agent**
		* Configuration of machines
	* *OpsWorks* **automation engine**
		* *Create*, *update* & *delete* of various AWS components
		* Handles *loadbalancing*, *autoscaling* and *autohealing*
		* Supports *lifecycle* events
* BerkShelf
  * Addresses an *OpsWorks* shortcoming from old versions - only one repository for recipes
  * Was added in *OpsWorks* 11.10 and allows to install cookbooks from many repositories

---

<a name="4_17"></a>
## [↖](#top)[↑](#4_16_4)[↓](#4_17_1) Organizations
<!-- toc_start -->
* [Overview](#4_17_1)
  * [Benefits](#4_17_1_1)
* [Limits:](#4_17_2)
<!-- toc_end -->

<a name="4_17_1"></a>
### [↖](#4_17)[↑](#4_17)[↓](#4_17_1_1) Overview
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

<a name="4_17_1_1"></a>
#### [↖](#4_17)[↑](#4_17_1)[↓](#4_17_2) Benefits
* Centrally manage policies across multiple accounts
* Control access to AWS services
* Automate AWS account creation and management
* *Consolidated billing*
  * One *paying account* linked to many *linked accounts*
  * Pricing benefits (Volumes, Storage, Instances)

<a name="4_17_2"></a>
### [↖](#4_17)[↑](#4_17_1_1)[↓](#4_18) Limits:
.|.
-|-
Maximum linked accounts|20

---

<a name="4_18"></a>
## [↖](#top)[↑](#4_17_2)[↓](#4_18_1) Step Functions
<!-- toc_start -->
* [Overview](#4_18_1)
<!-- toc_end -->

<a name="4_18_1"></a>
### [↖](#4_18)[↑](#4_18)[↓](#4_19) Overview
*AWS Step Functions* lets you coordinate multiple AWS services into serverless workflows so you can
build and update apps quickly. Using Step Functions, you can design and run workflows that stitch
together services such as AWS Lambda and Amazon ECS into feature-rich applications. Workflows are
made up of a series of steps, with the output of one step acting as input into the next.
Application development is simpler and more intuitive using Step Functions, because it translates
your workflow into a state machine diagram that is easy to understand, easy to explain to others,
and easy to change. You can monitor each step of execution as it happens, which means you can
identify and fix problems quickly. Step Functions automatically triggers and tracks each step, and
retries when there are errors, so your application executes in order and as expected.

---

<a name="4_19"></a>
## [↖](#top)[↑](#4_18_1)[↓](#4_19_1) X-Ray
<!-- toc_start -->
* [Overview](#4_19_1)
<!-- toc_end -->

<a name="4_19_1"></a>
### [↖](#4_19)[↑](#4_19) Overview
*AWS X-Ray* helps developers analyze and debug production, distributed applications, such as those
built using a microservices architecture. With X-Ray, you can understand how your application and
its underlying services are performing to identify and troubleshoot the root cause of performance
issues and errors. X-Ray provides an end-to-end view of requests as they travel through your
application, and shows a map of your application’s underlying components. You can use X-Ray to
analyze both applications in development and in production, from simple three-tier applications to
complex microservices applications consisting of thousands of services.

---

TODO: look at drawings from [awsgeek](https://www.awsgeek.com/)
