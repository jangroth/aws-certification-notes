[toc_start]::
<a name="top"></a>
---
* [DevOps Engineer Professional](#1)
* [Exam Objectives](#2)
  * [Content](#2_1)
* [Concepts](#3)
  * [Deployment Strategies](#3_1)
  * [EC2 Deployment Concepts](#3_2)
  * [EC2 Autoscaling Concepts](#3_3)
* [Services](#4)
  * [API Gateway](#4_1)
  * [Cloudformation](#4_2)
  * [CloudWatch](#4_3)
  * [CodeBuild](#4_4)
  * [CodeCommit](#4_5)
  * [Overview](#4_6)
  * [CodeDeploy](#4_7)
  * [CodePipeline](#4_8)
  * [Config](#4_9)
  * [ECS](#4_10)
  * [Elastic Beanstalk](#4_11)
  * [Lambda](#4_12)
  * [OpsWorks](#4_13)
  * [Organizations](#4_14)
  * [Step Functions](#4_15)
  * [X-Ray](#4_16)
---
[toc_end]::
<a name="1"></a>
# [↖](#top)[↑](#)[↓](#2) DevOps Engineer Professional

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

<a name="2_1_1"></a>
### Domain 1: SDLC Automation

* Apply concepts required to automate a CI/CD pipeline
* Determine source control strategies and how to implement them
* Apply concepts required to automate and integrate testing
* Apply concepts required to build and manage artifacts securely
* Determine deployment/delivery strategies (e.g., A/B, Blue/green, Canary, Red/black) and how to implement them using AWS Services

<a name="2_1_2"></a>
### Domain 2:Configuration Management and Infrastructure as Code

* Determine deployment services based on deployment needs
* Determine application and infrastructure deployment models based on business needs
* Apply security concepts in the automation of resource provisioning
* Determine how to implement lifecycle hooks on a deployment
* Apply concepts required to manage systems using AWS configuration management tools and services

<a name="2_1_3"></a>
### Domain 3: Monitoring and Logging

* Determine how to set up the aggregation, storage, and analysis of logs and metrics
* Apply concepts required to automate monitoring and event management of an environment
* Apply concepts required to audit, log, and monitoroperating systems, infrastructures, and applications
* Determine how to implement tagging and other metadata strategies

<a name="2_1_4"></a>
### Domain 4: Policies and Standards Automation

* Apply concepts required to enforce standards for logging, metrics, monitoring, testing, and security
* Determine how to optimize cost through automation
* Apply concepts required to implement governance strategies

<a name="2_1_5"></a>
### Domain 5: Incident and Event Response

* Troubleshoot issues and determine how to restore operations
* Determine how to automate event managementand alerting
* Apply concepts required to implement automated healing
* Apply concepts required to set up event-driven automated action

<a name="2_1_6"></a>
### Domain 6: High Availability, Fault Tolerance, and Disaster Recovery

* Determine appropriate use of multi-AZ versus multi-region architectures
* Determine how to implement high availability, scalability, and fault tolerance
* Determine the right services based on business needs (e.g., RTO/RPO, cost)
* Determine how to design and automate disaster recovery strategies
* Evaluate a deployment for points of failure

<a name="3"></a>
# [↖](#top)[↑](#2_1_6)[↓](#3_1) Concepts

<a name="3_1"></a>
## [↖](#top)[↑](#3)[↓](#3_1_1) Deployment Strategies

<a name="3_1_1"></a>
### Single target deployment

System|Deploy
-|-
`v1`|Initial State
`v1-2`|Deployment Stage
`v2`|Final State

* When initiated a new application version is installed on the (single) target server
* Practically not in use any more

.|.
-|-
Deploy time|Fast
Downtime|During complete deploy
Testing|Limited, because single server
Impact of failed Deployment|Downtime
Rollback|Remove new version and install old again

**pros**|**cons**
-|-
Simple & very few moving parts|Downtime
Deployment is faster than other methods|Limited testing

<a name="3_1_2"></a>
### All-at-once deployment

System|Deploy|.
-|-|-
`v1` `v1` `v1` `v1` `v1`|Initial State|.
`v1-2` `v1-2` `v1-2` `v1-2` `v1-2`|Deployment Stage|.
`v2` `v2` `v2` `v2` `v2`|Final State|.

* Single build stage triggers multiple target environments

.|.
-|-
Deploy time|Fast
Downtime|During complete deploy
Testing|Limited, because all at once
Impact of failed Deployment|Downtime
Rollback|Remove new version and install old again

**pros**|**cons**
-|-
Deployment is relatively fast|Downtime (like STD)
.|Limited testing (like STD)
.|Everything in-flight - can't stop deployment/rollback if targets fail
.|More complicated than STD, often requires orchestration

<a name="3_1_3"></a>
### Minimum in-service style deployment

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

.|.
-|-
Deploy time|Relatively fast
Downtime|None
Testing|Can test new version while old version is still active
Impact of failed Deployment|No downtime
Rollback|Remove new version and install old again

**pros**|**cons**
-|-
No downtime|Many moving parts, requires orchestration
Deployment happens in (two) stages|.
Generally quicker & with less stages than rolling deployments|.

<a name="3_1_4"></a>
### Rolling deployment

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

.|.
-|-
Deploy time|Can be slow
Downtime|Usually none
Testing|Can test new version while old version is still active
Impact of failed Deployment|No downtime
Rollback|Remove new version and install old again

**pros**|**cons**
-|-
No downtime (if number of stage deployments is small enough)|Does not necessarily maintain overall application health
Can be paused to allow for multi-version testing|Many moving parts, requires orchestration
.|Can be least efficient deployment method in terms of time taken

<a name="3_1_5"></a>
### Blue/green deployment

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
	* Update auto scaling launch configuration
	* Swap environment of an AWS Elastic Beanstalk application
	* Clone stack in AWS OpsWorks and update DNS

.|.
-|-
Deploy time|Medium
Downtime|None
Testing|Can test prior to cutover
Impact of failed Deployment|No downtime
Rollback|Revert cutover process

**pros**|**cons**
-|-
Rapid all-at-once deployment process, no need to wait for per target health checks|Requires advanced orchestration tooling
Can test health prior to cutover|Significant cost for a second environment (mitigated by advanced billing models)
Clean & controlled cutover (various options)|.
Easy rollback|.
Can be fully automated using advanced templating|.
By far the best method in terms of risk mitigation and minimal user impact|.

<a name="3_1_6"></a>
### Red/black deployment

> ... are just like blue/green, but they happen at a much faster rate.

Example:
1. `DNS` -> `LB` -> `ASG1`
2. `DNS` -> `LB` -> `ASG2`

<a name="3_1_7"></a>
### A/B testing
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

<a name="3_1_8"></a>
### Canary deployment
* Like A/B testing, but gradually increases percentage of traffic to green environment

---

<a name="3_2"></a>
## [↖](#top)[↑](#3_1_8)[↓](#3_2_1) EC2 Deployment Concepts

<a name="3_2_1"></a>
### Instance Profile

* A *container* for an IAM *role* that you can use to pass role information to an EC2 instance when the instance starts.
* An EC2 Instance cannot be assigned a role directly, but it can be assigned an Instance Profile which contains a role.
* If you use the AWS Management Console to create a role for Amazon EC2, the console automatically creates an instance profile and gives it the same name as the role.
* If you manage your roles from the AWS CLI or the AWS API, you create roles and instance profiles as separate actions.

<a name="3_2_2"></a>
### ELB/ALB Logs

* Access logging is an optional feature of Elastic Load Balancing that is disabled by default.
* After you enable access logging for your load balancer, Elastic Load Balancing captures the logs and stores them in the Amazon S3 bucket as compressed files.
* Can log every 5 or 60 minutes
* There's no additional charge
* You can disable access logging at any time.

<a name="3_2_3"></a>
### ELB/ALB Health Checks

If you have associated your Auto Scaling group with a Classic Load Balancer, you can use the load
balancer health check to determine the health state of instances in your Auto Scaling group. By
default an Auto Scaling group periodically determines the health state of each instance.

Your Application Load Balancer periodically sends requests to its registered targets to test their
status. These tests are called health checks.

The status of the instances that are healthy at the time of the health check is `InService`. The
status of any instances that are unhealthy at the time of the health check is `OutOfService`.

<a name="3_2_4"></a>
### ELB Security

* Need end-to-end security
* Encrypt all communication
* Use HTTPS (layer 7) or SSL (layer 4)
* Need to deploy an X.509 certificate on ELB
* Can configure back-end authentication
  * Once configured ELB only communicates with an instance if it has a matching public key

<a name="3_3"></a>
## [↖](#top)[↑](#3_2_4)[↓](#3_3_1) EC2 Autoscaling Concepts

<a name="3_3_1"></a>
### Overview

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
### Components

<a name="3_3_2_1"></a>
#### Autoscaling Group

* Contains a collection of Amazon EC2 instances that are treated as a logical grouping for the purposes of automatic scaling and management
* To use Amazon EC2 Auto Scaling features such as health check replacements and scaling policies

<a name="3_3_2_2"></a>
#### Launch Configuration

* Instance configuration template that an Auto Scaling group uses to launch EC2 instances
* One LC per ASG, can be used in many ASGs though
* Can't be modified, needs to be recreated

<a name="3_3_2_3"></a>
#### Launch Template

* Similar to LC
* Allows to have multiple versions of the same template
* With versioning, you can create a subset of the full set of parameters and then reuse it to create other templates or template versions
* AWS recommends to use launch templates instead of launch configurations to ensure that you can use the latest features of Amazon EC2

<a name="3_3_2_4"></a>
#### Termination Policy

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
#### Auto Scaling Lifecycle Hooks

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
#### Scaling

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
### CLI/API/SDK

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
### Troubleshooting

<a name="3_3_4_1"></a>
#### Possible Problems

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
#### Suspending ASG processes

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

<a name="4"></a>
# [↖](#top)[↑](#3_3_4_2)[↓](#4_1) Services

<a name="4_1"></a>
## [↖](#top)[↑](#4)[↓](#4_1_1) API Gateway

<a name="4_1_1"></a>
### Overview
*Amazon API Gateway* is a fully managed service that makes it easy for developers to create, publish,
maintain, monitor, and secure APIs at any scale. With a few clicks in the AWS Management Console,
you can create REST and WebSocket APIs that act as a “front door” for applications to access data,
business logic, or functionality from your backend services, such as workloads running on Amazon
Elastic Compute Cloud (Amazon EC2), code running on AWS Lambda, any web application, or real-time
communication applications.

<a name="4_1_1_1"></a>
#### Benefits
* Efficient API development
  * API versioning
* Easy monitoring
* Performance at any scale
* Cost savings at scale
* Flexible Security Control
* Restful API endpoints
* Serverless APIs
  * Can invoke Lambda
* Websocket APIs

---

<a name="4_2"></a>
## [↖](#top)[↑](#4_1_1_1)[↓](#4_2_1) Cloudformation

<a name="4_2_1"></a>
### Overview
*AWS CloudFormation* provides a common language for you to describe and provision all the
infrastructure resources in your cloud environment. CloudFormation allows you to use a simple text
file to model and provision, in an automated and secure manner, all the resources needed for your
applications across all regions and accounts. This file serves as the single source of truth for
your cloud environment.

AWS CloudFormation is available at no additional charge, and you pay only for the AWS resources
needed to run your applications.

* Allows to create and provision **resources** in a reusable **template** fashion
	* A *CloudFormation* template is a `JSON` or `YAML` formatted text file
* Related resources are managed in a single unit called a **stack**
	* All the resources in a stack are defined by the stack's *CloudFormation* template
	* Controls lifecycle of managed resources
	* Stack has `name` & `id`
  * Can be updated *directly* or via *change set*
  * Will **rollback** stack if it fails to create (can be disabled via API / console)
  * Possible to detect **stack drift**, if supported by created rersources
  * Can enable **termination protection**
* A **stack policy** is an *IAM*-style policy statements that governs who can do what

<a name="4_2_2"></a>
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
		* MinLength / MaxLength
		* MinValue / MaxValue
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

<a name="4_2_3"></a>
### Intrinsic Function
* Used to pass in values that are not available until runtime
* Usable in `resource` properties, `metadata` attributes, and `update policy` attributes (auto-scaling)

Name|Attributes|.
-|-|-
`Ref`| *logicalName* | * Returns the *default* value of the specified parameter or resource, usually instance id
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
`Fn::Sub`| - *String*<br/> - { *key*: *Value*, ... } | * Substitutes variables in an input string with values that you specify string list
`Fn::Transform`| Name: *String*<br/> Parameters:<br/>   { *key*: *Value*, ... } | * Specifies a macro to perform custom processing on part of a stack template

<a name="4_2_4"></a>
### Stacks

TODO: stack sets and stack drift

<a name="4_2_4_1"></a>
#### Stacks Creation

<a name="4_2_4_1_1"></a>
##### Process
1. Template upload into S3 bucket
2. Template syntax check
3. Stack name & parameter verification & ingestion (apply default values)
4. Template processing & stack creation
	* **Resource ordering**
			* *WaitConditions* allow further control about what happens when
	* **Resource creation**
		* Will try to create as many resources as possible in parallel
		* Includes pausing and waiting for other resources to be created first
	* Output creation
5. Stack completion (or rollback)

<a name="4_2_4_1_2"></a>
##### Resource ordering

<a name="4_2_4_1_2_1"></a>
###### Natural ordering
CloudFormation knows about 'natural' dependencies between resources.

<a name="4_2_4_1_2_2"></a>
###### DependsOn
Also evaluates `DependsOn` field:
* Allows to direct *CloudFormation* on how to handle more complex dependencies
* Applies to *creation* as well as *deletion* & *rollback*
* `DependsOn` can be a single resource or a list of resources
* Will error on circular dependencies
* `DependsOn` is problematic if the target resource needs more complex setup than just stack creation

<a name="4_2_4_1_2_3"></a>
###### Creation Policy
* Can only be used for *EC2 Instances* and *AutoscalingGroup*
* Creation policy definion
	* Defines desired signal count & waiting period
* Signal configuration
	* Call to `cfn-signal` from EC2 user-data

```
AutoScalingGroup:
  Type: AWS::AutoScaling::AutoScalingGroup
  Properties:
    AvailabilityZones:
      Fn::GetAZs: ''
    LaunchConfigurationName:
      Ref: LaunchConfig
    DesiredCapacity: '3'
    MinSize: '1'
    MaxSize: '4'
  CreationPolicy:
    ResourceSignal:
      Count: '3'
      Timeout: PT15M
  UpdatePolicy:
    AutoScalingScheduledAction:
      IgnoreUnmodifiedGroupSizeProperties: 'true'
    AutoScalingRollingUpdate:
      MinInstancesInService: '1'
      MaxBatchSize: '2'
      PauseTime: PT1M
      WaitOnResourceSignals: 'true'
LaunchConfig:
  Type: AWS::AutoScaling::LaunchConfiguration
  Properties:
    ImageId: ami-16d18a7e
    InstanceType: t2.micro
    UserData:
      "Fn::Base64":
        !Sub |
          #!/bin/bash -xe
          yum update -y aws-cfn-bootstrap
          /opt/aws/bin/cfn-signal -e $? --stack ${AWS::StackName} --resource AutoScalingGroup --region ${AWS::Region}
```

<a name="4_2_4_1_2_4"></a>
###### Wait Conditions and Handlers
For other resources (*external* to the stack)
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
    AvailabilityZones:
      Fn::GetAZs: ""
    LaunchConfigurationName:
      Ref: "LaunchConfig"
    MinSize: "1"
    MaxSize: "5"
    DesiredCapacity:
      Ref: "WebServerCapacity"
    LoadBalancerNames:
      - Ref: "ElasticLoadBalancer"
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

<a name="4_2_4_1_3"></a>
##### Stacks Deletion

<a name="4_2_4_1_4"></a>
##### Resource deletion policy
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

<a name="4_2_4_2"></a>
#### Stacks Updates

<a name="4_2_4_2_1"></a>
##### Process
A CloudFormation *stack policy* is a JSON-based document that defines which actions can be performed
on specified resources. With CloudFormation stack policies you can protect all or certain
resources in your stacks from being unintentionally updated or deleted during the update process.

* Check **stack policy** if updates are allowed
	* No policy present -> all updates are allowed
	* Once a policy is applied
		* It cannot be deleted
		* *All* resources that not explicitely allowed are denied
		* Default deny can be explicitely overwritten
	* Policy format JSON
		* Contains *policy documents*

Element|.
-|-
`Effect`|.
`Resource`,`NotResource`|.
`Principal`|*Must* be wildcard for stack policies
`Action`|`Update:Modify`,`Update:Replace`,`Update:Delete`,`Update:(wildcard)`
`Condition`|Typically evaluates based on resource type

* Update can impact a resource in 4 possible ways
	* No interruption
		* E.g. change `ProvisionedThroughput` of a DynamoDB table
	* Some interruption
		* E.g. change `EbsOptimized` of an EC2 instance (EBS-backed)
		* E.g. change `InstanceType` of an EC2 instance (EBS-backed)
	* Replacement
		* E.g. change `AvailabilityZone` of an EC2 instance
		* E.g. change `ImageId` of an EC2 instance
		* E.g. change `Tablename` of a DynamoDB table
	* Deletion

<a name="4_2_4_3"></a>
#### Stacks Nesting
* *Resources* in a stack can be references to other stacks
* Output values of nested stack are returned to parent stack
* Benefits
	* Allows infrastructure to be split over many templates
	* Allows infrastructure reuse
	* Allows to workaround limitations like max resources or max template size
* How to nest
	* Declare resources as `AWS::CloudFormation::Stack`
	* Point `TemplateURL` to S3 URL of nested stack
	* Use `Parameters` to provide the nested stack with input values (defaults will be used otherwise)

<a name="4_2_5"></a>
### Custom Resources
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
		* Returns outcome of operation back to *CloudFormation*, typically includes custom data as well

TODO: Follow AWS example or reading the latest AMI id

<a name="4_2_6"></a>
### Limits
.|.
-|-
Max stacks per region|200
Max templates per region|unlimited
Max template size (stored in S3)|460kB
Parameters per stack|60
Mappings per stack|100
Resources per stack|200
Outputs per stack|60

TODO: cloudformation init directive
TODO: Compare chapter against LinuxAcademy

---

<a name="4_3"></a>
## [↖](#top)[↑](#4_2_6)[↓](#4_3_1) CloudWatch

<a name="4_3_1"></a>
### Overview

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

<a name="4_3_2"></a>
### Concepts

<a name="4_3_2_1"></a>
#### Logging

**Logs**
* *Log events* are records of some activity recorded by the application or resource being monitored
* *Log streams* are sequences of log events from the same source
* *Log groups* are groups of log streams that share the same retention, monitoring, and access control settings
* *Metric filters* allow to extract metric observations from ingested events and transform them to data points in a CloudWatch metric
* *Retention settings* can be used to specify how long log events are kept in CloudWatch Logs

Logs can be exported to S3 for durable storage

<a name="4_3_2_2"></a>
#### Metrics & Alarms

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

<a name="4_3_3"></a>
### Key metrics for EC2

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

<a name="4_3_4"></a>
### Key metrics for Auto Scaling Group

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

<a name="4_3_5"></a>
### Key metrics for ELB (classic load balancer)

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

<a name="4_3_6"></a>
### Key metrics for ALB (active load balancer)

Metric|Effect
-|-
`RequestCount`|Number of completed requests
`HealthyHostCount`,`UnhealthyHostCount`|Self explainatory
`TargetResponseTime`|The time elapsed after the request leaves the load balancer until a response from the target is received.
`HTTPCode_ELB_3XX_Count`<br/>`HTTPCode_ELB_4XX_Count`<br/>`HTTPCode_ELB_5XX_Count`|The number of HTTP XXX server error codes that originate from the *load balancer*. This count does *not* include any response codes generated by the targets.

<a name="4_3_7"></a>
### Key metrics for NLB (network load balancer)

Metric|Effect
-|-
`processedbyte `|The total number of bytes processed by the load balancer, including TCP/IP headers.
`tcp_client_reset_count`|the total number of reset (rst) packets sent from a client to a target.
`tcp_elb_reset_count`|the total number of reset (rst) packets generated by the load balancer.
`tcp_target_reset_coun`|the total number of reset (rst) packets sent from a target to a client.
---

<a name="4_4"></a>
## [↖](#top)[↑](#4_3_7)[↓](#4_4_1) CodeBuild

<a name="4_4_1"></a>
### Overview
*AWS CodeBuild* is a fully managed continuous integration service that compiles source code, Runs
tests, and produces software packages that are ready to deploy. With CodeBuild, you don’t need to
provision, manage, and scale your own build servers. CodeBuild scales continuously and processes
multiple builds concurrently, so your builds are not left waiting in a queue. You can get started
quickly by using prepackaged build environments, or you can create custom build environments that
use your own build tools. With CodeBuild, you are charged by the minute for the compute resources
you use.

<a name="4_4_1_1"></a>
#### Benefits
* Fully managed build service
* Continuous scaling
* Extensible
  * Can use own build tools and runtimes
* Pay as you go
* Enables CI/CD
* Secure

---

<a name="4_5"></a>
## [↖](#top)[↑](#4_4_1_1)[↓](#4_6) CodeCommit

<a name="4_6"></a>
### [↖](#top)[↑](#4_5)[↓](#4_6_1) Overview
*AWS CodeCommit* is a fully-managed source control service that hosts secure Git-based repositories.
It makes it easy for teams to collaborate on code in a secure and highly scalable ecosystem.
CodeCommit eliminates the need to operate your own source control system or worry about scaling
its infrastructure. You can use CodeCommit to securely store anything from source code to binaries,
and it works seamlessly with your existing Git tools.

<a name="4_6_1"></a>
### Benefits
* Fully managed
* Highly available
* Faster development cycle
  * Code lives close to actual environments
* Secure
  * Encryption, IAM integration
* Collaborate on code
* Use existing tools
  * CodeBuild, Jenkins, other CI tools
* Fully enabled for automation
	* Provides notifacations and triggers for all repository events

### How To

#### Protect branches

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

#### Send Notifications

Use CloudWatch Event Rules under the hood

* Set up notification / notification rules:
	* Pick triggering event (`on commit`, ..., `brunch updated`)
	* Pick SNS topic as target
	* Add subscriber to target

* Set up Cloudwatch Events directly:
	* Pick event *source* (AWS service)
	* Pick event *type* (different types, also includes CloudTrail)
	* Pick target (many different types, e.g. Lambda, SNS, SSM, Code*)

#### Trigger SNS / Lambda

More limited in scope than Notifications. Do not us CloudWatch Events under the hood.

* Configure CodeCommit as Lambda trigger

---

<a name="4_7"></a>
## [↖](#top)[↑](#4_6_1)[↓](#4_7_1) CodeDeploy

<a name="4_7_1"></a>
### Overview
*AWS CodeDeploy* is a fully managed deployment service that automates software deployments to a
variety of compute services such as Amazon EC2, AWS Fargate, AWS Lambda, and your on-premises
servers. AWS CodeDeploy makes it easier for you to rapidly release new features, helps you avoid
downtime during application deployment, and handles the complexity of updating your applications.
You can use AWS CodeDeploy to automate software deployments, eliminating the need for error-prone
manual operations. The service scales to match your deployment needs.

* Requires *agent* (ruby) running on instances
* Can deploy into
  * *autoscaling group*
  * EC2 instances (using tags)
  * On-prem instances
TODO: ECS/Fargate/Lambda?

* Takes code from S3 or github if invoked directly, does not directly support CodeCommit
  * Workaround: Use a simple 2 stage CodePipeline

* Provides hooks to configure deploy process
  * `appspec.yml` in source code

<a name="4_7_2"></a>
### Benefits
* Automated deployments
  * EC2, ECS, Fargate, Lambda
* Minimize downtime
* Centralized control
* Easy to adopt

---

<a name="4_8"></a>
## [↖](#top)[↑](#4_7_2)[↓](#4_8_1) CodePipeline

<a name="4_8_1"></a>
### Overview
*AWS CodePipeline* is a fully managed continuous delivery service that helps you automate your
release pipelines for fast and reliable application and infrastructure updates. CodePipeline
automates the build, test, and deploy phases of your release process every time there is a code
change, based on the release model you define. This enables you to rapidly and reliably deliver
features and updates. You can easily integrate AWS CodePipeline with third-party services such as
GitHub or with your own custom plugin. With AWS CodePipeline, you only pay for what you use. There
are no upfront fees or long-term commitments.

<a name="4_8_1_1"></a>
#### Benefits
* Rapid delivery
* Configurable workflow
* Get started fast
  * No CI/CD infastructue needs to be provisioned
* Easy to integrate
  * Plugin concept to integrate with other components

<a name="4_8_1_2"></a>
#### Components

* **stage**
  * **action group**
    * **action**

<a name="4_8_1_3"></a>
#### Pipeline Actions

<a name="4_8_1_3_1"></a>
##### Source
* S3
* CodeCommit
* Github

<a name="4_8_1_3_2"></a>
##### Build
* CodeBuild
* Jenkins
* TeamCity
* etc

<a name="4_8_1_3_3"></a>
##### Test
* CodeBuild
* Jenkins
* Ghost Inspector

<a name="4_8_1_3_4"></a>
##### Deploy
* CodeDeploy
* CloudFormation
* etc

<a name="4_8_1_3_5"></a>
##### Invoke
* Lambda

<a name="4_8_1_3_6"></a>
##### Approval
* SNS

---

<a name="4_9"></a>
## [↖](#top)[↑](#4_8_1_3_6)[↓](#4_9_1) Config

<a name="4_9_1"></a>
### Overview
*AWS Config* is a service that enables you to assess, audit, and evaluate the configurations of your
AWS resources. Config continuously monitors and records your AWS resource configurations and
allows you to automate the evaluation of recorded configurations against desired configurations.
With Config, you can review changes in configurations and relationships between AWS resources,
dive into detailed resource configuration histories, and determine your overall compliance against
the configurations specified in your internal guidelines. This enables you to simplify compliance
auditing, security analysis, change management, and operational troubleshooting.

---

<a name="4_10"></a>
## [↖](#top)[↑](#4_9_1)[↓](#4_10_1) ECS

<a name="4_10_1"></a>
### Overview
*Amazon Elastic Container Service* (Amazon ECS) is a highly scalable, fast, container management
service that makes it easy to run, stop, and manage Docker containers on a cluster. You can host
your cluster on a serverless infrastructure that is managed by Amazon ECS by launching your
services or tasks using the Fargate launch type. For more control you can host your tasks on a
cluster of Amazon Elastic Compute Cloud (Amazon EC2) instances that you manage by using the EC2
launch type.

<a name="4_10_1_1"></a>
#### Benefits
* Containers without servers
* Containerize Everything
* Secure
* Performance at Scale
* AWS Integration

<a name="4_10_2"></a>
### Components
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

TODO: Deploy container on fargate

---

<a name="4_11"></a>
## [↖](#top)[↑](#4_10_2)[↓](#4_11_1) Elastic Beanstalk

<a name="4_11_1"></a>
### Overview
AWS Elastic Beanstalk is an easy-to-use service for deploying and scaling web applications and
services developed with Java, .NET, PHP, Node.js, Python, Ruby, Go, and Docker on familiar servers
such as Apache, Nginx, Passenger, and IIS.

You can simply upload your code and Elastic Beanstalk automatically handles the deployment, from
capacity provisioning, load balancing, auto-scaling to application health monitoring. At the same
time, you retain full control over the AWS resources powering your application and can access the
underlying resources at any time.

* Allows to *deploy*, *monitor* and *scale* applications quickly
* Focusses on components and performance, *not* configuration and specification
* Aims to simplify or even remove infrastructure management

<a name="4_11_2"></a>
### Components
* Components
	* **Application**
		* Either application in the tradional sense
		* Or application component, e.g. service, frontend, backend
	* **Environment**
		* Isolated, self-contained set of components of infrastructure
			* *Web server* environment
				* Represents a web application
			* *Worker* environment
				* Act upon output created by another environment
				* Should only be loosely coupled to web server environments, eg. via *SQS*
		* Single-instance or multi-instance scalable
		* Application can have mulitple environments
			* Either represent development stages (PROD, STAGE, ...)
			* Or application component, e.g. service, frontend, backend
	* **Application Version**
		* Unique package that represents version of the *application*
		* Uploaded as a zipped *application source bundle*
		* Each application can have many application versions
		* Can be deployed to one or more *environment* within an application
* Supported platforms
	* Platform-specific application *source bundle* (e.g. Java `war` for Tomcat)
		* Go
		* Java SE/with Tomcat
		* .NET on Windows Server with IIS
		* Node.js
		* PHP
		* Python
		* Ruby Stanalone/Puma
    * Docker Single-/Multicontainer
    * Docker Preconfigured Glassfish/Python/Go

<a name="4_11_3"></a>
### `.ebextensions`
* *Folder* within application source bundle
* Allows granular configuration & customisation of the EB environment and its resources
* Contains `*.config` in *YAML* format with different sections like
	* `option_settings` - global Configuration options
	* `resources` - specify additional resources, allows granular configuration of these
	* `packages`, `sources`, `files`, `users`, `groups`, `commands`, `container_commands`, `service`

<a name="4_11_4"></a>
### Limits:
.|.
-|-
Applications|75
Application Versions|1000
Configuration Templates|2000
Environments|200

---

<a name="4_12"></a>
## [↖](#top)[↑](#4_11_4)[↓](#4_12_1) Lambda

<a name="4_12_1"></a>
### Overview
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

<a name="4_12_2"></a>
### Triggering

<a name="4_12_2_1"></a>
#### Services that Lambda reads events from
  * Amazon Kinesis
  * Amazon DynamoDB
  * Amazon Simple Queue Service

<a name="4_12_2_2"></a>
#### Services that invoke Lambda functions synchronously
  * Amazon Cognito
  * Amazon Lex
  * Amazon Alexa
  * Amazon API Gateway
  * Amazon CloudFront (Lambda@Edge)
  * Amazon Kinesis Data Firehose

<a name="4_12_2_3"></a>
#### Services that invoke Lambda functions asynchronously
	* Amazon Simple Storage Service
	* Amazon Simple Notification Service
	* Amazon Simple Email Service
	* AWS CloudFormation
	* Amazon CloudWatch Logs
	* Amazon CloudWatch Events
	* AWS CodeCommit
	* AWS Config

---

<a name="4_12_3"></a>
### Managed Services

<a name="4_12_4"></a>
### Overview
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

<a name="4_13"></a>
## [↖](#top)[↑](#4_12_4)[↓](#4_13_1) OpsWorks

<a name="4_13_1"></a>
### Overview
*AWS OpsWorks* is a configuration management service that provides managed instances of Chef and
Puppet. Chef and Puppet are automation platforms that allow you to use code to automate the
configurations of your servers. OpsWorks lets you use Chef and Puppet to automate how servers are
configured, deployed, and managed across your Amazon EC2 instances or on-premises compute
environments. OpsWorks has three offerings, *AWS Opsworks for Chef Automate*, *AWS OpsWorks for
Puppet Enterprise*, and *AWS OpsWorks Stacks*.

<a name="4_13_2"></a>
### OpsWorks Stacks

* Orchestration services that uses Chef
* Components
  * *Stack*
  * *Layer*
  * *Instance*
  * *Application*
* Runs *recipes* to maintain a consitent state

---

<a name="4_14"></a>
## [↖](#top)[↑](#4_13_2)[↓](#4_14_1) Organizations

<a name="4_14_1"></a>
### Overview
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

<a name="4_14_1_1"></a>
#### Benefits
* Centrally manage policies across multiple accounts
* Control access to AWS services
* Automate AWS account creation and management
* *Consolidated billing*
  * One *paying account* linked to many *linked accounts*
  * Pricing benefits (Volumes, Storage, Instances)

<a name="4_14_2"></a>
### Limits:
.|.
-|-
Maximum linked accounts|20

---

<a name="4_15"></a>
## [↖](#top)[↑](#4_14_2)[↓](#4_15_1) Step Functions

<a name="4_15_1"></a>
### Overview
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

<a name="4_16"></a>
## [↖](#top)[↑](#4_15_1)[↓](#4_16_1) X-Ray

<a name="4_16_1"></a>
### Overview
*AWS X-Ray* helps developers analyze and debug production, distributed applications, such as those
built using a microservices architecture. With X-Ray, you can understand how your application and
its underlying services are performing to identify and troubleshoot the root cause of performance
issues and errors. X-Ray provides an end-to-end view of requests as they travel through your
application, and shows a map of your application’s underlying components. You can use X-Ray to
analyze both applications in development and in production, from simple three-tier applications to
complex microservices applications consisting of thousands of services.

---

TODO: look at drawings from [awsgeek](https://www.awsgeek.com/)
