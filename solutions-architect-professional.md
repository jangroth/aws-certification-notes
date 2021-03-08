<!-- toc_start -->
<a name="top"></a>
---
* [Solutions Architect Professional](#1)
* [Exam Objectives](#2)
  * [Content](#2_1)
* [Identity and Federation](#3)
  * [Overview - possible ways to manage Identity and Federation in AWS](#3_1)
  * [Identity and Access Management (Core Topic)](#3_2)
  * [Security Token Service (Core Topic)](#3_3)
  * [Amazon Cognito (Core Topic)](#3_4)
  * [Identity Federation (Core Topic)](#3_5)
  * [AWS Single Sign-On](#3_6)
  * [AWS Active Directory Services (Core Topic)](#3_7)
  * [AWS Organization (Core Topic)](#3_8)
  * [AWS Resource Access Manager](#3_9)
* [Security](#4)
  * [CloudTrail](#4_1)
  * [KMS](#4_2)
  * [SSM Parameter Store](#4_3)
  * [Secrets Manager](#4_4)
  * [RDS Security](#4_5)
  * [SSL/SNI/MITM/DNSSEC](#4_6)
  * [AWS Certificate Manager](#4_7)
  * [CloudHSM](#4_8)
  * [S3 Security](#4_9)
  * [Network Security, DDOS, Shield, WAF and Firewall Manager](#4_10)
  * [Blocking IP addresses](#4_11)
  * [Amazon Inspector](#4_12)
  * [Config](#4_13)
  * [AWS Managed Logs (Core Topic)](#4_14)
  * [GuardDuty](#4_15)
* [Compute & Load Balancing](#5)
  * [AWS Solution Architectures](#5_1)
  * [EC2](#5_2)
  * [Auto Scaling (Core Topic)](#5_3)
  * [ECS (Core Topic)](#5_4)
  * [Fargate](#5_5)
  * [Lambda (Core Topic)](#5_6)
  * [Elastic Load Balancing (Core Topic)](#5_7)
  * [API Gateway](#5_8)
  * [Route 53 (Core Topic)](#5_9)
  * [Solution Architeture Comparision](#5_10)
* [Storage](#6)
  * [EBS](#6_1)
  * [Local Instance Store](#6_2)
  * [EFS](#6_3)
  * [Amazon S3](#6_4)
  * [S3 Solution Architecture](#6_5)
  * [S3 vs EFS vs EBS Comparison](#6_6)
* [Caching](#7)
  * [CloudFront (Core Topic)](#7_1)
  * [ElastiCache (Core Topic)](#7_2)
  * [Handling Extreme Rates](#7_3)
* [Databases](#8)
  * [DynamoDB](#8_1)
  * [ElasticSearch (Core Topic)](#8_2)
  * [RDS](#8_3)
  * [Aurora](#8_4)
* [Service Communication](#9)
  * [Step Functions](#9_1)
  * [Simple Workflow Service (SWF)](#9_2)
  * [Simple Queue Service (Core Topic)](#9_3)
  * [Amazon MQ](#9_4)
  * [Simple Notification Service (Core Topic)](#9_5)
* [Data Engineering](#10)
  * [Kinesis (Core Topic)](#10_1)
  * [AWS Batch](#10_2)
  * [Amazon EMR](#10_3)
  * [Running Jobs on AWS](#10_4)
  * [Amazon Redshift](#10_5)
  * [Athena](#10_6)
  * [QuickSight](#10_7)
  * [AWS Data Pipeline](#10_8)
  * [Big Data Architecture](#10_9)
* [Monitoring](#11)
  * [CloudWatch (Core Topic)](#11_1)
  * [X-Ray](#11_2)
* [Deployment and Instance Management](#12)
  * [Elastic Beanstalk (Core Topic)](#12_1)
  * [OpsWorks Stacks (Core Topic)](#12_2)
  * [CodeDeploy (Core Topic)](#12_3)
  * [CloudFormation (Core Topic)](#12_4)
  * [Service Catalog](#12_5)
  * [AWS Serverless Application Model](#12_6)
  * [Deployments (Core Topic)](#12_7)
  * [Systems Manager (Core Topic)](#12_8)
* [Cost Control](#13)
  * [Best practices of cost management](#13_1)
  * [AWS Cost Allocation Tags](#13_2)
  * [Trusted Advisor (Core Topic)](#13_3)
  * [EC2 Purchasing Options & Saving Plans (Core Topic)](#13_4)
  * [S3 Cost Savings](#13_5)
* [Migration](#14)
  * [The 6R Strategies](#14_1)
  * [On-Premises strategies with AWS](#14_2)
  * [Storage Gateway (Core Topic)](#14_3)
  * [Snowball](#14_4)
  * [Database Migration Service (Core Topic)](#14_5)
  * [Application Discovery Service (Core Topic)](#14_6)
  * [Server Migration Service](#14_7)
  * [AWS Cloud Adoption Readiness Tool (CART)](#14_8)
  * [Disaster Recovery](#14_9)
* [VPC](#15)
  * [Virtual Private Cloud (VPC)](#15_1)
  * [VPC Peering](#15_2)
  * [Transit Gateway](#15_3)
  * [VPC Endpoints (Core Topic)](#15_4)
  * [PrivateLink](#15_5)
  * [VPN (Core Topic)](#15_6)
  * [Direct Connect (Core Topic)](#15_7)
  * [Redundant connections beweteen on-premises and AWS](#15_8)
* [Other Services](#16)
  * [Alex for Business](#16_1)
  * [Amazon AppStream & Amazon Workspaces](#16_2)
  * [Amazon DocumentDB](#16_3)
  * [Amazon Lex](#16_4)
  * [Amazon Rekognition](#16_5)
  * [CloudSearch](#16_6)
  * [Kinesis Video Streams](#16_7)
  * [Amazon Mechanical Turk](#16_8)
  * [Device Farm](#16_9)
  * [Macie](#16_10)
  * [Amazon Pinpoint](#16_11)
  * [Private Marketplace](#16_12)
---
<!-- toc_end -->
<a name="1"></a>
# [↖](#top)[↓](#2) Solutions Architect Professional

> 10/2020 -

Following [Ultimate AWS Certified Solutions Architect Professional 2021](https://www.udemy.com/course/aws-solutions-architect-professional).

---

<a name="2"></a>
# [↖](#top)[↑](#1)[↓](#2_1) Exam Objectives
* Design and deploy dynamically scalable, highly available, fault-tolerant, and reliable applications on AWS
* Select appropriate AWS services to design and deploy an application based on given requirements
* Migrate complex, multi-tier applications on AWS
* Design and deploy enterprise-wide scalable operations on AWS
* Implement cost-control strategies

<a name="2_1"></a>
## [↖](#top)[↑](#2)[↓](#2_1_1) Content
<!-- toc_start -->
* [Domain 1: Design for Organizational Complexity](#2_1_1)
* [Domain 2: Design for New Solutions](#2_1_2)
* [Domain 3: Migration Planning](#2_1_3)
* [Domain 4: Cost Control](#2_1_4)
* [Domain 5: Continuous Improvement for Existing Solutions](#2_1_5)
<!-- toc_end -->

<a name="2_1_1"></a>
### [↖](#2_1)[↑](#2_1)[↓](#2_1_2) Domain 1: Design for Organizational Complexity
* Determine cross-account authentication and access strategy for complex organizations
  * for example, an organization with varying compliance requirements, multiple business units, and varying scalability requirements
* Determine how to design networks for complex organizations
  * for example, an organization with varying compliance requirements, multiple business units, and varying scalability requirements
* Determine how to design a multi-account AWS environment for complex organizations
  * for example, an organization with varying compliance requirements, multiple business units, and varying scalability requirements
<a name="2_1_2"></a>
### [↖](#2_1)[↑](#2_1_1)[↓](#2_1_3) Domain 2: Design for New Solutions
* Determine security requirements and controls when designing and implementing a solution
* Determine a solution design and implementation strategy to meet reliability requirements
* Determine a solution design to ensure business continuity
* Determine a solution design to meet performance objectives
* Determine a deployment strategy to meet business requirements when designing and implementing a solution
<a name="2_1_3"></a>
### [↖](#2_1)[↑](#2_1_2)[↓](#2_1_4) Domain 3: Migration Planning
* Select existing workloads and processes for potential migration to the cloud
* Select migration tools and/or services for new and migrated solutions based on detailed AWS knowledge
* Determine a new cloud architecture for an existing solution
* Determine a strategy for migrating existing on-premises workloads to the cloud
<a name="2_1_4"></a>
### [↖](#2_1)[↑](#2_1_3)[↓](#2_1_5) Domain 4: Cost Control
* Select a cost-effective pricing model for a solution
* Determine which controls to design and implement that will ensure costoptimization
* Identify opportunities to reduce cost in an existing solution
<a name="2_1_5"></a>
### [↖](#2_1)[↑](#2_1_4)[↓](#3) Domain 5: Continuous Improvement for Existing Solutions
* Troubleshoot solution architectures
* Determine a strategy to improve an existing solution for operational excellence
* Determine a strategy to improve the reliability of an existing solution
* Determine a strategy to improve the performance of an existing solution
* Determine a strategy to improve the securityof an existing solution
* Determine how to improve the deployment of an existing solution

---

<a name="3"></a>
# [↖](#top)[↑](#2_1_5)[↓](#3_1) Identity and Federation

<a name="3_1"></a>
## [↖](#top)[↑](#3)[↓](#3_2) Overview - possible ways to manage Identity and Federation in AWS

|.|.|.
|-|-|-
|**Identity only in AWS**|Users and accounts all in AWS|Simplest setup
| |AWS Organizations|In case we have multiple accounts<br/>Adds consolidated billing and compliance
|**Federation**|With SAML|With a SAML-compliant IdP
| |Without SAML|With a custom IdP (STS `GetFederationToken`)
| |AWS SSO|For multiple accounts within AWS Organizations and SAML
| |Web Identity Federation|Not recommended, use AWS Cognito
| |AWS Cognito|For most web and mobile applications<br/>Has anonymous mode & MFA
|**Active Directory on AWS**|Microsoft AD|Standalone or setup trust AD with on-premises<br/>Has MFA<br/>Seamless join<br/>RDS integration
| |AD Connector|Proxy requests to on-premises
| |Simple AD|Standalone & cheap AD-compatible with no MFA, no advanced capabilities

---

<a name="3_2"></a>
## [↖](#top)[↑](#3_1)[↓](#3_2_1) Identity and Access Management (Core Topic)
<!-- toc_start -->
* [Overview](#3_2_1)
* [Users](#3_2_2)
* [Groups](#3_2_3)
* [Roles](#3_2_4)
* [Policies](#3_2_5)
  * [Policy Conditions](#3_2_5_1)
  * [Policy Variables & Tags](#3_2_5_2)
  * [Identity-based vs resource-based policies](#3_2_5_3)
* [Automated Scanning](#3_2_6)
  * [Access Advisor](#3_2_6_1)
  * [Access Analyzer](#3_2_6_2)
<!-- toc_end -->

<a name="3_2_1"></a>
### [↖](#3_2)[↑](#3_2)[↓](#3_2_2) Overview
AWS Identity and Access Management (IAM) enables you to manage access to AWS services and resources securely. Using IAM, you can create and manage AWS users and groups, and use permissions to allow and deny their access to AWS resources.

Best practices:
* Lock away your AWS account root user access keys
* Create individual IAM users
* Use groups to assign permissions to IAM users
* Grant least privilege
* Get started using permissions with **AWS managed policies**
* Use **customer managed policies** instead of **inline policies**
* Use access levels (*full*, *limited*) to review IAM permissions
* Configure a strong password policy for your users
* Enable MFA
* Use roles for applications that run on Amazon EC2 instances
* Use roles to delegate permissions
* Do not share access keys
* Rotate credentials regularly
* Remove unnecessary credentials
* Use policy conditions for extra security
* Monitor activity in your AWS account

On AWS:
* <a href="https://aws.amazon.com/iam/" target="_blank">Service</a> - <a href="https://aws.amazon.com/iam/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html" target="_blank">User Guide</a>

<a name="3_2_2"></a>
### [↖](#3_2)[↑](#3_2_1)[↓](#3_2_3) Users
An entity that you create in AWS to represent the person or application that uses it to interact with AWS. A user in AWS consists of a name and credentials.
* Holds long-term credentials

<a name="3_2_3"></a>
### [↖](#3_2)[↑](#3_2_2)[↓](#3_2_4) Groups
A collection of IAM users. Groups let you specify permissions for multiple users, which can make it easier to manage the permissions for those users.
* Typically only provides permission to assume a role

<a name="3_2_4"></a>
### [↖](#3_2)[↑](#3_2_3)[↓](#3_2_5) Roles
An IAM identity that you can create in your account that has specific permissions. An IAM role has some similarities to an IAM user. Roles and users are both AWS identities with permissions policies that determine what the identity can and cannot do in AWS. However, instead of being uniquely associated with one person, a role is intended to be assumable by anyone who needs it. Also, a role does not have standard long-term credentials such as a password or access keys associated with it. Instead, when you assume a role, it provides you with temporary security credentials for your role session, provided by STS.
* **AWS service role** - A role that a service assumes to perform actions in your account on your behalf. When you set up some AWS service environments, you must define a role for the service to assume. This service role must include all the permissions required for the service to access the AWS resources that it needs. Service roles vary from service to service, but many allow you to choose your permissions, as long as you meet the documented requirements for that service. Service roles provide access only within your account and cannot be used to grant access to services in other accounts. You can create, modify, and delete a service role from within IAM.
	* **AWS service role for an EC2 instance** - A special type of service role that an application running on an Amazon EC2 instance can assume to perform actions in your account. This role is assigned to the EC2 instance when it is launched. Applications running on that instance can retrieve temporary security credentials and perform actions that the role allows.
	* **AWS service-linked role** - A unique type of service role that is linked directly to an AWS service. Service-linked roles are **predefined by the service** and include all the permissions that the service requires to call other AWS services on your behalf. The linked service also defines how you create, modify, and delete a service-linked role. A service might automatically create or delete the role. It might allow you to create, modify, or delete the role as part of a wizard or process in the service. Or it might require that you use IAM to create or delete the role. Regardless of the method, service-linked roles make setting up a service easier because you don't have to manually add the necessary permissions.
		* `aws iam create-service-linked-role --aws-service-name SERVICE-NAME.amazonaws.com`
		* <a href="https://aws.amazon.com/blogs/security/introducing-an-easier-way-to-delegate-permissions-to-aws-services-service-linked-roles/" target="_blank">AWS Blog</a>
* **Trust policy** - A JSON policy document in which you define the principals that you trust to assume the role. A role trust policy is a required resource-based policy that is attached to a role in IAM. The principals that you can specify in the trust policy include users, roles, accounts, and services.
* **Permissions boundary** - An advanced feature in which you use policies to limit the maximum permissions that an identity-based policy can grant to a role. You cannot apply a permissions boundary to a service-linked role.
* **Role for cross-account access** - A role that grants access to resources in one account to a trusted principal in a different account. Roles are the primary way to grant cross-account access. However, some AWS services allow you to attach a policy directly to a resource (instead of using a role as a proxy). These are called resource-based policies, and you can use them to grant principals in another AWS account access to the resource. Some of these resources include S3, S3 Glacier vaults, SNS and SQS.

```
Type: AWS::IAM::Role
Properties:
  RoleName: String
  Description: String
  Path: String
  AssumeRolePolicyDocument: Json (Trust policy)
  ManagedPolicyArns:
    - String (ARN)
  PermissionsBoundary: String (ARN)
  Policies:
    - Policy
  MaxSessionDuration: Integer
  Tags:
    - Tag
```

<a name="3_2_5"></a>
### [↖](#3_2)[↑](#3_2_4)[↓](#3_2_5_1) Policies
You manage access in AWS by creating policies and attaching them to IAM identities (users, groups of users, or roles) or AWS resources. A policy is an object in AWS that, when associated with an identity or resource, defines their permissions. AWS evaluates these policies when an *IAM principal* (user or role) makes a request. Permissions in the policies determine whether the request is allowed or denied. Most policies are stored in AWS as JSON documents.
* AWS supports six types of policies:
  * **Identity-based policies** – Attach managed and inline policies to IAM identities (users, groups to which users belong, or roles). Identity-based policies grant permissions to an identity.
  * **Resource-based policies** – Attach inline policies to resources. The most common examples of resource-based policies are Amazon S3 bucket policies and IAM role trust policies. Resource based policies grant permissions to the principal that is specified in the policy. Principals can be in the same account as the resource or in other accounts.
  * **Permissions boundaries** – Use a managed policy as the permissions boundary for an IAM entity (user or role). That policy defines the maximum permissions that the identity-based policies can grant to an entity, but does not grant permissions. Permissions boundaries do not define the maximum permissions that a resource-based policy can grant to an entity.
  * **Organizations SCPs** – Use an AWS Organizations service control policy (SCP) to define the maximum permissions for account members of an organization or organizational unit (OU). SCPs limit permissions that identity-based policies or resource-based policies grant to entities (users or roles) within the account, but do not grant permissions.
  * **Access control lists (ACLs)** – Use ACLs to control which principals in other accounts can access the resource to which the ACL is attached. ACLs are similar to resource-based policies, although they are the only policy type that does not use the JSON policy document structure. ACLs are cross-account permissions policies that grant permissions to the specified principal. ACLs cannot grant permissions to entities within the same account.
  * **Session policies** – Pass advanced session policies when you use the AWS CLI or AWS API to assume a role or a federated user. Session policies limit the permissions that the role or user's identity-based policies grant to the session. Session policies limit permissions for a created session, but do not grant permissions. For more information, see Session Policies.
* An **AWS managed policy** is a standalone policy that is created and administered by AWS. Standalone policy means that the policy has its own Amazon Resource Name (ARN) that includes the policy name.
* On AWS: <a href="https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_examples.html" target="_blank">Policy Examples</a>

```
Type: AWS::IAM::Policy
Properties:
  PolicyName: String
  PolicyDocument: Json (YAML in CFN)
    Version: 2012-10-17
    Statement:
      - Effect: Allow
        Action: '*'
        Resource: '*'
      - Effect: Allow
        NotAction: 's3:DeleteBucket' # <-- all S3 but deleteBucket
        Resource: '*'
      - Effect: Deny
        NotAction: 's3:DeleteBucket' # <-- no S3 but deleteBucket
        Resource: '*'
  Groups:
    - String (!Ref)
  Roles:
    - String (!Ref)
  Users:
    - String (!Ref)
```

<a name="3_2_5_1"></a>
#### [↖](#3_2)[↑](#3_2_5)[↓](#3_2_5_2) Policy Conditions
* String (`StringEquals`, `StringNotEquals`, `StringLike`...)
  * "Condition": {"StringEquals": {"aws:PrincipalTag/job-category": "iamuser-admin"}}
  * "Condition": {"StringLike": {"s3:prefix": [ "", "home/", "home/${aws:username}/" ]}}
* Numeric (`NumericEquals`, `NumericNotEquals`, `NumericLessThan`...)
* Date (`DateEquals`, `DateNotEquals`, `DateLessThan`...)
* Boolean (`Bool`):
  * “Condition": {"Bool": {"aws:SecureTransport": "true"}}
  * "Condition": {"Bool": {"aws:MultiFactorAuthPresent": "true"}}
* (`Not`)`IpAddress`:
  * "Condition": {"IpAddress": {"aws:SourceIp": "203.0.113.0/24"}}
* `ArnEquals`, `ArnLike`
* `Null`: "Condition":{"Null":{"aws:TokenIssueTime":"true"}}

<a name="3_2_5_2"></a>
#### [↖](#3_2)[↑](#3_2_5_1)[↓](#3_2_5_3) Policy Variables & Tags
* Example: `${aws:username}`
	* "Resource": ["arn:aws:s3:::mybucket/${aws:username}/*"]
* AWS Specific:
	* `aws:CurrentTime`, `aws:TokenIssueTime`, `aws:principaltype`, `aws:SecureTransport`, `aws:SourceIp`, `aws:userid`, `ec2:SourceInstanceARN`
* Service Specific:
	* `s3:prefix`, `s3:max-keys`, `s3:x-amz-acl`, `sns:Endpoint`, `sns:Protocol`...
* Tag Based:
	* `iam:ResourceTag/key-name`, `aws:PrincipalTag/key-name`...

<a name="3_2_5_3"></a>
#### [↖](#3_2)[↑](#3_2_5_2)[↓](#3_2_6) Identity-based vs resource-based policies
* **Identity-based policies** are attached to an IAM user, group, or role. These policies let you specify what that identity can do (its permissions).
* **Resource-based policies** are attached to a resource.
<a href="https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_aws-services-that-work-with-iam.html" target="_blank">AWS services that work with IAM</a>

<a name="3_2_6"></a>
### [↖](#3_2)[↑](#3_2_5_3)[↓](#3_2_6_1) Automated Scanning

<a name="3_2_6_1"></a>
#### [↖](#3_2)[↑](#3_2_6)[↓](#3_2_6_2) Access Advisor
Access Advisor shows the services that a certain user or role can access and when those services were last accessed. Review this data to remove unused permissions.

<a name="3_2_6_2"></a>
#### [↖](#3_2)[↑](#3_2_6_1)[↓](#3_3) Access Analyzer
Makes it simple for security teams and administrators to check that their policies provide only the intended access to resources. Resource policies allow customers to granularly control who is able to access a specific resource and how they are able to use it across the entire cloud environment.

IAM Access Analyzer continuously monitors policies for changes, meaning customers no longer need to rely on intermittent manual checks in order to catch issues as policies are added or updated. Using IAM Access Analyzer, customers can proactively address any resource policies that violate their security and governance best practices around resource sharing and protect their resources from unintended access. IAM Access Analyzer delivers comprehensive, detailed findings through the AWS IAM, Amazon S3, and AWS Security Hub consoles and also through its APIs. Findings can also be exported as a report for auditing purposes. IAM Access Analyzer findings provide definitive answers of who has public and cross-account access to AWS resources from outside an account.

---

<a name="3_3"></a>
## [↖](#top)[↑](#3_2_6_2)[↓](#3_3_1) Security Token Service (Core Topic)
<!-- toc_start -->
* [Overview](#3_3_1)
* [Providing access to an IAM user in another AWS account that you own](#3_3_2)
* [Providing access to an IAM user from a third party AWS account](#3_3_3)
<!-- toc_end -->

<a name="3_3_1"></a>
### [↖](#3_3)[↑](#3_3)[↓](#3_3_2) Overview
AWS Security Token Service (AWS STS) is a web service that enables you to request temporary, limited-privilege credentials for AWS Identity and Access Management (IAM) users or for users that
* Provide access for an IAM user in one AWS account that you own to access resources in another account that you own
* Provide access to IAM users in AWS accounts owned by third parties
* Provide access for services offered by AWS to AWS resources
* Provide access for externally authenticated users (identity federation)
* Ability to revoke active sessions and credentials for a role (by adding a policy using a time statement – AWSRevokeOlderSessions)

Whenever an IAM user assumes another role, it's *giving up* its original permissions.

STS on AWS:
* <a href="https://docs.aws.amazon.com/STS/latest/APIReference/welcome.html" target="_blank">API Reference</a>

<a name="3_3_2"></a>
### [↖](#3_3)[↑](#3_3_1)[↓](#3_3_3) Providing access to an IAM user in another AWS account that you own
* *Zone of trust* are accounts or organizations that you own
* In *target account*, create *target role* that should be assumed
  * Define trust policy that specifies *source account* as `Principal`
  * Share role ARN
* In *source account*, grant members of a group permission to assume that role
  ```
  {
    "Sid": "assumeIntoAirplanes",
    "Effect": "Allow",
    "Action": "sts:AssumeRole",
    "Resource": "arn:aws:iam::339228396083:role/OrganizationAccountAccessRole"
  }
  ```

<a name="3_3_3"></a>
### [↖](#3_3)[↑](#3_3_2)[↓](#3_4) Providing access to an IAM user from a third party AWS account
* *Outside Zone of Trust* are third parties
* Create role for third party
* Communicate role name and secret `ExternalId` to third party
  * `ExternalId` is *best practice* only, would also work without
  ```
  "Effect": "Allow",
  "Principal": {
    "AWS": "arn:aws:iam::123456789012:root"
  },
  "Action": "sts:AssumeRole",
  "Condition": {
    "StringEquals": {
      "sts:ExternalId": "secret"
    }
  }
  ```
* *Confused Deputy* refers to the fact that *without* `externalId`, it wouldn't be possible for service providers to make sure that they are accessing the right account (as role ARNs are guessable)

---

<a name="3_4"></a>
## [↖](#top)[↑](#3_3_3)[↓](#3_4_1) Amazon Cognito (Core Topic)
<!-- toc_start -->
* [Overview](#3_4_1)
* [User pools](#3_4_2)
* [Amazon Cognito Identity Pools (Federated Identities)](#3_4_3)
<!-- toc_end -->
<a name="3_4_1"></a>
### [↖](#3_4)[↑](#3_4)[↓](#3_4_2) Overview
Amazon Cognito provides authentication, authorization, and user management for your web and mobile apps. Your users can sign in directly with a user name and password, or through a third party such as Facebook, Amazon, Google or Apple.

The two main components of Amazon Cognito are **user pools** and **identity pools**. User pools are user directories that provide sign-up and sign-in options for your app users. Identity pools enable you to grant your users access to other AWS services. You can use identity pools and user pools separately or together.
* Supports MFA
* Data at-rest and in-transit encryption
* Log in via social identiy providers
* Support for SAML
* On AWS: <a href="https://aws.amazon.com/cognito/" target="_blank">Service</a> - <a href="https://aws.amazon.com/cognito/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/cognito/" target="_blank">User Guide</a>

<a name="3_4_2"></a>
### [↖](#3_4)[↑](#3_4_1)[↓](#3_4_3) User pools
A user pool is a user directory in Amazon Cognito. With a user pool, your users can sign in to your web or mobile app through Amazon Cognito. Your users can also sign in through social identity providers like Google, Facebook, Amazon, or Apple, and through SAML identity providers. Whether your users sign in directly or through a third party, all members of the user pool have a directory profile that you can access through a Software Development Kit (SDK).
* Provides a directory profile for all users which you can access through an SDK.
* Supports user federation through a third-party identity provider.
* Signed users receive authentication tokens.
* Tokens can be exchanged for AWS access via Amazon Cognito identity pools.

<a name="3_4_3"></a>
### [↖](#3_4)[↑](#3_4_2)[↓](#3_5) Amazon Cognito Identity Pools (Federated Identities)
Amazon Cognito identity pools (federated identities) enable you to create unique identities for your users and federate them with identity providers. With an identity pool, you can obtain temporary, limited-privilege AWS credentials to access other AWS services.

* Supports the following identity providers:
	* Public providers: Login with Amazon (Identity Pools), Facebook (Identity Pools), Google (Identity Pools), Sign in with Apple (Identity Pools).
	* Amazon Cognito user pools
	* Open ID Connect Providers (Identity Pools)
	* SAML Identity Providers (Identity Pools)
	* Developer Authenticated Identities (Identity Pools)
* Authenticates users with web identity providers, including Amazon Cognito user pools.
* Assigns temporary AWS credentials via AWS STS.
* Supports anonymous guest users.

---

<a name="3_5"></a>
## [↖](#top)[↑](#3_4_3)[↓](#3_5_1) Identity Federation (Core Topic)
<!-- toc_start -->
* [Overview](#3_5_1)
* [SAML 2.0](#3_5_2)
* [Custom Identity Broker](#3_5_3)
* [Federating users of a mobile or web-based app with Web Identity Federation (*not* using Amazon Cognito)](#3_5_4)
* [Federating users of a mobile or web-based app with Amazon Cognito](#3_5_5)
<!-- toc_end -->

<a name="3_5_1"></a>
### [↖](#3_5)[↑](#3_5)[↓](#3_5_2) Overview
> OAuth 2.0 is designed only for authorization, for granting access to data and features from one application to another.

> OpenID Connect is built on the OAuth 2.0 protocol and uses an additional JSON Web Token (JWT), called an ID token, to standardize areas that OAuth 2.0 leaves up to choice, such as scopes and endpoint discovery. It is specifically focused on user authentication and is widely used to enable user logins on consumer websites and mobile apps.

> Security Assertion Markup Language (**SAML**) is an open standard for exchanging authentication and authorization data between parties, in particular, between an identity provider and a service provider. SAML is independent of OAuth, relying on an exchange of messages to authenticate in XML SAML format, as opposed to JWT. It is more commonly used to help enterprise users sign in to multiple applications using a single login.

> An identity provider (**IdP**) is a system entity that creates, maintains, and manages identity information for principals and also provides authentication services to relying applications within a federation or distributed network.

> Active Directory Federation Services (**ADFS**) is a Single Sign-On (SSO) solution created by Microsoft. As a component of Windows Server operating systems, it provides users with authenticated access to applications that are not capable of using Integrated Windows Authentication (IWA) through Active Directory (**AD**).

* <a href="https://www.okta.com/identity-101/whats-the-difference-between-oauth-openid-connect-and-saml/" target="_blank">What’s the Difference Between OAuth, OpenID Connect, and SAML?</a>

If you already manage user identities outside of AWS, you can use IAM identity providers instead of creating IAM users in your AWS account. With an identity provider (IdP), you can manage your user identities outside of AWS and give these external user identities permissions to use AWS resources in your account. These users assume identity provided access *role*.

Federation can have many flavors:
* SAML 2.0
* Custom Identity Broker
* Web Identity Federation without Amazon Cognito
* Web Identity Federation with Amazon Cognito
* Single Sign-On
* Non-SAML with AWS Microsoft AD
<a name="3_5_2"></a>
### [↖](#3_5)[↑](#3_5_1)[↓](#3_5_3) SAML 2.0
* Overview
  * To integrate Active Directory/ADFS (or any SAML 2.0) with AWS
  * Access through console or CI
  * Client app authenticates against IdP, receives *SAML assertion* back
  * SAML assertion is exchanged with STS to reveive temporary credentials
* Need to establish trust between your organization's IdP and AWS
  * You begin by registering AWS with your IdP. In your organization's IdP you register AWS as a service provider (SP)
  * AD/ADFS
    * For *AD*, using your organization's IdP, you generate an equivalent metadata XML file that can describe your IdP as an IAM identity provider in AWS.
    * For *ADFS*, invoke ADFS instead of IdP
  * In the IAM console, you create a SAML identity provider entity.
  * In IAM, you create one or more IAM roles. In the role's trust policy, you set the SAML provider as the principal, which establishes a trust relationship between your organization and AWS.
  * In your organization's IdP, you define assertions that map users or groups in your organization to the IAM roles.
  * API/Console
    * For *API access*, in the application that you're creating, you call the STS `AssumeRoleWithSAML` API, passing it the ARN of the SAML provider you created in Step 3, the ARN of the role to assume that you created in Step 4, and the SAML assertion about the current user that you get from your IdP.
    * For *console access*, this goes against an AWS SSO endpoint instead, SSO then invokes STS
  * If the request is successful, the API returns a set of temporary security credentials,
* Note - federation through SAML is the 'old' way of doing things. Better to use AWS SSO

<a name="3_5_3"></a>
### [↖](#3_5)[↑](#3_5_2)[↓](#3_5_4) Custom Identity Broker
* If identity provider is not compatible with SAML 2.0
* The identity broker must determine the appropriate IAM policy (talks directly to STS, unlike SAML scenarios)
* Use STS `AssumeRole` or `GetFederationToken`
* <a href="https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_common-scenarios_federated-users.html" target="_blank">Documentation On AWS</a>

<a name="3_5_4"></a>
### [↖](#3_5)[↑](#3_5_3)[↓](#3_5_5) Federating users of a mobile or web-based app with Web Identity Federation (*not* using Amazon Cognito)
* Login with Web Identity Federation provider (Amazon, Google, Facebook or any other OpenID-Connect compatible IdP)
  * Retrieves OpenID-Connect token
* Get temporary credentials from STS
	* *This is harder than interacting with Cognito!*
* App calls STS `AssumeRoleWithWebIdentity` and receives token in exchange for OpenID Connect token
* Assume IAM role
* After being authenticated with Web Identity Federation, you can identify the user with an IAM policy variable:
  * `www.amazon.com:user_id`
  * `graph.facebook.com:id`
  * `accounts.google.com:sub`
* Not recommended, use Amazon Cognito instead
  * Does not support anonymous users
  * Does not support MFA
  * Does not support data syncronization
* <a href="https://docs.amazonaws.cn/en_us/amazondynamodb/latest/developerguide/WIF.html" target="_blank">Documentation On AWS</a>

<a name="3_5_5"></a>
### [↖](#3_5)[↑](#3_5_4)[↓](#3_6) Federating users of a mobile or web-based app with Amazon Cognito
If you create a mobile or web-based app that accesses AWS resources, the app needs security credentials in order to make programmatic requests to AWS. For most mobile application scenarios, we recommend that you use Amazon Cognito.
* Login with Web Identity Federation provider (Amazon, Google, Facebook or any other OpenID-Connect compatible IdP)
  * Retrieves OpenID-Connect token
* App calls Amazon Cognito and retrieves STS token in exchange for OpenID Connect token
* Assume IAM role
	* After being authenticated with Web Identity Federation, you can identify the user with an IAM policy variable:
		* `cognito-identity.amazonaws.com:sub`
* Requires trust relationship between Amazon Cognito and OpenID Connect IdP
* Amazon Cognito prefered over WebIdentiy federation
  * Supports anonymous users
  * Supports MFA
  * Supports data syncronization
* Amazon Cognito replaces old service called Token Vending Machine
* <a href="https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_providers_oidc_cognito.html" target="_blank">Documentation On AWS</a>

---

<a name="3_6"></a>
## [↖](#top)[↑](#3_5_5)[↓](#3_6_1) AWS Single Sign-On
<!-- toc_start -->
* [Overview](#3_6_1)
<!-- toc_end -->

<a name="3_6_1"></a>
### [↖](#3_6)[↑](#3_6)[↓](#3_7) Overview
AWS Single Sign-On is a cloud-based single sign-on (SSO) service that makes it easy to centrally manage SSO access to all of your AWS accounts and cloud applications. Specifically, it helps you manage SSO access and user permissions across all your AWS accounts in AWS Organizations. AWS SSO also helps you manage access and permissions to commonly used third-party software as a service (SaaS) applications, AWS SSO-integrated applications as well as custom applications that support Security Assertion Markup Language (SAML) 2.0. AWS SSO includes a user portal where your end-users can find and access all their assigned AWS accounts, cloud applications, and custom applications in one place.
* Centrally manage Single Sign-On to access multiple accounts and 3rd-party business applications.
  * No need for custom IdP login portal, AWS SSO communicates directly with SAML-compatible login portal
* Integrated with AWS Organizations
* Supports SAML 2.0 markup
* Integration with on-premises Active Directory
  * Standalone AWS Managed Microsoft AD
  * AD Connector to on-premises AD
  * AWS Managed Microsoft AD with two-way forest trust with on-premises AD
* Centralized permission management
* Centralized auditing with CloudTrail
* Uses exactly one of these identity sources
	* **AWS SSO identity store** – When you enable AWS SSO for the first time, it is automatically configured with an AWS SSO identity store as your default identity source. This is where you create your users and groups, and assign their level of access to your AWS accounts and applications.
	* **Active Directory** – Choose this option if you want to continue managing users in either your self-managed Active Directory (AD) or your AWS Managed Microsoft AD directory using AWS Directory Service.
	* **External identity provider** – Choose this option if you prefer to manage users in an external identity provider (IdP) such as Okta or Azure Active Directory.
* Does **not** help with federated access from mobile applications, supports single sign-on to business applications through web browsers only.
* Does **not** support OpenID Connect
* On AWS: <a href="https://aws.amazon.com/single-sign-on/" target="_blank">Service</a> - <a href="https://aws.amazon.com/single-sign-on/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/singlesignon/latest/userguide/what-is.html" target="_blank">User Guide</a>

---

<a name="3_7"></a>
## [↖](#top)[↑](#3_6_1)[↓](#3_7_1) AWS Active Directory Services (Core Topic)
<!-- toc_start -->
* [Overview](#3_7_1)
* [AWS Managed Microsoft AD](#3_7_2)
  * [Overview](#3_7_2_1)
  * [Integrations](#3_7_2_2)
  * [Connecting to on-premises AD](#3_7_2_3)
  * [Syncronizing with on-premises AD](#3_7_2_4)
* [AD Connector](#3_7_3)
* [Simple AD](#3_7_4)
<!-- toc_end -->

<a name="3_7_1"></a>
### [↖](#3_7)[↑](#3_7)[↓](#3_7_2) Overview

> Active Directory (**AD**) is a directory service developed by Microsoft for Windows domain networks. It is included in most Windows Server operating systems as a set of processes and services.

> Active Directory Federation Services (**ADFS**), a software component developed by Microsoft, can run on Windows Server operating systems to provide users with single sign-on access to systems and applications located across organizational boundaries.

> The Lightweight Directory Access Protocol (**LDAP**) is an open, vendor-neutral, industry standard application protocol for accessing and maintaining distributed directory information services over an Internet Protocol network.
* Three scenarios:
	* **AWS Managed Microsoft AD**
		* Create your own AD in AWS, manage users locally, supports MFA
		* Establish “trust" connections with on-premises AD
	* **Active Directory Connector**
		* Directory Gateway (proxy) to redirect to on-premises AD
		* Users are managed on the on-premises AD
	* **Simple Active Directory**
		* AD-compatible managed directory on AWS
		* Cannot be joined with on-premises AD!
* <a href="https://docs.aws.amazon.com/directoryservice/latest/admin-guide/what_is.html" target="_blank">Documentation On AWS</a>

<a name="3_7_2"></a>
### [↖](#3_7)[↑](#3_7_1)[↓](#3_7_2_1) AWS Managed Microsoft AD
<a name="3_7_2_1"></a>
#### [↖](#3_7)[↑](#3_7_2)[↓](#3_7_2_2) Overview
AWS Directory Service for Microsoft Active Directory, also known as AWS Managed Microsoft AD, enables your directory-aware workloads and AWS resources to use managed Active Directory (AD) in AWS. AWS Managed Microsoft AD is built on actual Microsoft AD and does not require you to synchronize or replicate data from your existing Active Directory to the cloud. You can use the standard AD administration tools and take advantage of the built-in AD features, such as group policy and single sign-on. With AWS Managed Microsoft AD, you can easily join Amazon EC2 and Amazon RDS for SQL Server instances to your domain, and use AWS End User Computing services, such as Amazon WorkSpaces, with AD users and groups.
* Managed Service
* Deploy *Domain Controllers*, different AZs for HA, multiple DCs per AZ for scaling
  * *Standalone* in cloud, or *joined* to on-premises AD
* *Seamless Domain Join* allows to join AD from different accounts or VPCs
* Automated backups are supported
* Can join on-premises AD
  * *AD two-way forest trust*
* On AWS: <a href="https://aws.amazon.com/directoryservice/" target="_blank">Service</a> - <a href="https://aws.amazon.com/directoryservice/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/directoryservice/latest/admin-guide/what_is.html" target="_blank">User Guide</a>

<a name="3_7_2_2"></a>
#### [↖](#3_7)[↑](#3_7_2_1)[↓](#3_7_2_3) Integrations
* Windows applications on EC2 can *join the domain* and run traditional AD applications
  * Sharepoint, ...
* RDS for SQL Server, AWS Workspaces, Quicksight, ...
* AWS SSO for 3rd party access (SAML)

<a name="3_7_2_3"></a>
#### [↖](#3_7)[↑](#3_7_2_2)[↓](#3_7_2_4) Connecting to on-premises AD
* Needs AWS Direct Connect or VPN
* Three kinds of of forest trust
  * One way on-premises -> AWS
  * One way AWS -> on-premises
  * Two way AWS <-> on-premises
* Forest trust is different to syncronize!
  * Replication not supported
  * Users on both ADs are independent from each other

<a name="3_7_2_4"></a>
#### [↖](#3_7)[↑](#3_7_2_3)[↓](#3_7_3) Syncronizing with on-premises AD
* Have to install Microsoft AD on EC2 yourself and setup replication
* Establish forest trust between this installation and AWS Managed Microsoft AD

<a name="3_7_3"></a>
### [↖](#3_7)[↑](#3_7_2_4)[↓](#3_7_4) AD Connector
* AD Connector is a directory gateway (*proxy*) to redirect directory requests to your on-premises Microsoft Active Directory
* No caching capability
  * Has latency
* Manage users solely on-premises, no possibility of setting up a trust
  * No MFA
* Requires VPN or Direct Connect -> can't function if connection goes down!
* Doesn’t work with SQL Server, doesn’t do seamless joining, can’t share directory

<a name="3_7_4"></a>
### [↖](#3_7)[↑](#3_7_3)[↓](#3_8) Simple AD
* Simple AD is an inexpensive AD–compatible service with the common directory features.
* Supports joining EC2 instances, manage users and groups
* Does not support MFA, RDS SQL server, AWS SSO
* Small: 500 users, large: 5000 users
* Powered by Samba 4, compatible with Microsoft AD
* Lower cost, low scale, basic AD compatible, or LDAP compatibility
* No trust relationship to on-premises Microsoft AD

---

<a name="3_8"></a>
## [↖](#top)[↑](#3_7_4)[↓](#3_8_1) AWS Organization (Core Topic)
<!-- toc_start -->
* [Overview](#3_8_1)
  * [Benefits](#3_8_1_1)
  * [Multi-account strategies](#3_8_1_2)
  * [Best Practices](#3_8_1_3)
* [Service Control Policies](#3_8_2)
* [Tag Policies](#3_8_3)
* [Reserved Instances](#3_8_4)
* [Trusted Access](#3_8_5)
<!-- toc_end -->
<a name="3_8_1"></a>
### [↖](#3_8)[↑](#3_8)[↓](#3_8_1_1) Overview
*AWS Organizations* offers policy-based management for multiple AWS accounts. With Organizations, you can create groups of accounts, automate account creation, apply and manage policies for those groups. Organizations enables you to centrally manage policies across multiple accounts, without requiring custom scripts and manual processes.

Using AWS Organizations, you can create Service Control Policies (SCPs) that centrally control AWS service use across multiple AWS accounts. You can also use Organizations to help automate the creation of new accounts through APIs. Organizations helps simplify the billing for multiple accounts by enabling you to setup a single payment method for all the accounts in your organization through consolidated billing. AWS Organizations is available to all AWS customers at no additional charge.
* Management accounts must invite child accounts
  * Invited accounts must approve enabling all features
* Management accounts can create child accounts
* Master can access child accounts using:
  * CloudFormation StackSets to create IAM roles in target accounts
  * Assume the roles using the STS Cross Account capability
* Recommended strategy is creating a dedicated account for logging or security
* API is available to automate AWS account creation
* Integration with AWS Single Sign-On (SSO)
* On AWS: <a href="https://aws.amazon.com/organizations/" target="_blank">Service</a> - <a href="https://aws.amazon.com/organizations/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/organizations/latest/userguide/" target="_blank">User Guide</a>

<a name="3_8_1_1"></a>
#### [↖](#3_8)[↑](#3_8_1)[↓](#3_8_1_2) Benefits
* Centrally manage policies across multiple accounts
* Control access to AWS services
* Automate AWS account creation and management
* *Consolidated billing*
  * One *paying account* linked to many *linked accounts*
  * Pricing benefits (Volumes, Storage, Instances)
* Create account hierachy with *Organizational Units* (OUs)
* Apply SCPs across the hierachy
  * Ability to apply an SCP to prevent member accounts from leaving the org
* Apply Tag Policies across the hierachy

<a name="3_8_1_2"></a>
#### [↖](#3_8)[↑](#3_8_1_1)[↓](#3_8_1_3) Multi-account strategies
* Create accounts per department, per cost center, per dev/test/prod, based on regulatory restrictions (using SCP), for better resource isolation (ex: VPC), to have separate per-account service limits, isolated account for logging,
* "Multi account" vs "one account, multi VPC"
* Use tagging standards for billing purposes
* Enable CloudTrail on all accounts, send logs to central S3 account
* Send CloudWatch logs to central logging account
* Establish cross account roles for admin purposes

<a name="3_8_1_3"></a>
#### [↖](#3_8)[↑](#3_8_1_2)[↓](#3_8_2) Best Practices
* For the management account
	* Use the management account only for tasks that require the management account
	* Use a group email address for the management account's root user
	* Use a complex password for the management account's root user
	* Enable MFA for your root user credentials
	* Add a phone number to the account contact information
	* Review and keep track of who has access
	* Document the processes for using the root user credentials
	* Apply controls to monitor access to the root user credentials
* For member accounts
	* Use a group email address for all member account root users
	* Use a complex password for member account root user
	* Enable MFA for your root user credentials
	* Add the management account's phone number to the member account contact information
	* Review and keep track of who has access
	* Document the processes for using the root user credentials
	* Use an SCP to restrict what the root user in your member accounts can do
	* Apply controls to monitor access to the root user credentials

<a name="3_8_2"></a>
### [↖](#3_8)[↑](#3_8_1_3)[↓](#3_8_3) Service Control Policies
Service control policies (SCPs) are one type of policy that you can use to manage your organization. SCPs offer central control over the maximum available permissions for all accounts in your organization, allowing you to ensure your accounts stay within your organization’s access control guidelines. SCPs are available only in an organization that has all features enabled. SCPs aren't available if your organization has enabled only the consolidated billing features. SCPs do *not* apply for the management account itself.
* Whitelist or blacklist IAM actions
  * Applied at the Root, OU or Account level
  * SCP is applied to all the users and roles of the account, including root (*no effect on root though*)
  * The SCP does not affect service-linked roles
    * Service-linked roles enable other AWS services to integrate with AWS Organizations and can't be restricted by SCPs.
* SCPs are inherit on OU level, *not* account level
  * Child *OU* inherits from parent *OU*, but child *account* does *not* inherit from parent *account*
* SCP must have an explicit `allow` (does not allow anything by default)
* Use cases:
  * Restrict access to certain services (for example: can’t use EMR)
  * Enforce PCI compliance by explicitly disabling services
* SCPs do **not** affect any service-linked role.
	* Service-linked roles enable other AWS services to integrate with AWS Organizations and can't be restricted by SCPs.
* Attaching an SCP to an AWS Organizations entity **just defines a guardrail** for what actions the principals can perform. You still need to attach identity-based or resource-based policies to principals or resources in your organization's accounts to actually grant permission to them.
* AWS strongly recommends that you don't attach SCPs to the root of your organization as this may impact the policies on child accounts and possibly lockout key features.
* On AWS: <a href="https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_evaluation-logic.html" target="_blank">IAM policy evaluation logic</a>

<a name="3_8_3"></a>
### [↖](#3_8)[↑](#3_8_2)[↓](#3_8_4) Tag Policies
Tag policies are a type of policy that can help you standardize tags across resources in your organization's accounts. In a tag policy, you specify tagging rules applicable to resources when they are tagged.

<a name="3_8_4"></a>
### [↖](#3_8)[↑](#3_8_3)[↓](#3_8_5) Reserved Instances
* For billing purposes, the consolidated billing feature of AWS Organizations treats all the accounts in the organization as one account.
* This means that all accounts in the organization can receive the hourly cost benefit of Reserved Instances that are purchased by any other account.
* The management account of an organization can turn off Reserved Instance (RI) discount and Savings Plans discount sharing for any accounts in that organization, including the management account
* This means that RIs and Savings Plans discounts aren't shared between any accounts that have sharing turned off.
* To share an RI or Savings Plans discount with an account, both accounts must have sharing turned on.

<a name="3_8_5"></a>
### [↖](#3_8)[↑](#3_8_4)[↓](#3_9) Trusted Access
You can use trusted access to enable a supported AWS service that you specify, called the trusted service, to perform tasks in your organization and its accounts on your behalf. This involves granting permissions to the trusted service but does not otherwise affect the permissions for IAM users or roles.
* When you enable access, the trusted service can create an IAM role called a service-linked role in every account in your organization whenever that role is needed.

---

<a name="3_9"></a>
## [↖](#top)[↑](#3_8_5)[↓](#3_9_1) AWS Resource Access Manager
<!-- toc_start -->
* [Overview](#3_9_1)
<!-- toc_end -->
<a name="3_9_1"></a>
### [↖](#3_9)[↑](#3_9)[↓](#4) Overview
AWS RAM lets you share your resources with any AWS account or through AWS Organizations. If you have multiple AWS accounts, you can create resources centrally and use AWS RAM to share those resources with other accounts.
* Avoids resource duplication
* Key resources that can be shared
  * VPC Subnets
    * allow to have all the resources launched in the same subnets
    * must be from the same AWS Organizations.
    * Cannot share security groups and default VPC
    * Participants can manage their own resources in there
    * Participants can't view, modify, delete resources that belong to other participants or the owner
	* VPC sharing allows customers to share subnets with other AWS accounts within the same AWS Organization. This is a very powerful concept that allows for a number of benefits:
		* Separation of duties: centrally controlled VPC structure, routing, IP address allocation.
		* Application owners continue to own resources, accounts, and security groups.
		* VPC sharing participants can reference security group IDs of each other.
		* Efficiencies: higher density in subnets, efficient use of VPNs and AWS Direct Connect.
		* Hard limits can be avoided, for example, 50 VIFs per AWS Direct Connect connection through simplified network architecture.
		* Costs can be optimized through reuse of NAT gateways, VPC interface endpoints, and intra-Availability Zone traffic.
  * AWS Transit Gateway
  * Route 53 Resolver Rules
  * License Manager Configurations
* Can enable trusted access with AWS Organizations via CLI command
* On AWS: <a href="https://aws.amazon.com/ram/" target="_blank">Service</a> - <a href="https://aws.amazon.com/ram/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/ram/latest/userguide/what-is.html" target="_blank">User Guide</a>

---

<a name="4"></a>
# [↖](#top)[↑](#3_9_1)[↓](#4_1) Security

<a name="4_1"></a>
## [↖](#top)[↑](#4)[↓](#4_1_1) CloudTrail
<!-- toc_start -->
* [Overview](#4_1_1)
* [Concepts](#4_1_2)
  * [Event](#4_1_2_1)
* [Trail](#4_1_3)
* [Notification options](#4_1_4)
<!-- toc_end -->

<a name="4_1_1"></a>
### [↖](#4_1)[↑](#4_1)[↓](#4_1_2) Overview
AWS CloudTrail is a service that enables governance, compliance, operational auditing, and risk auditing of your AWS account. With CloudTrail, you can log, continuously monitor, and retain account activity related to actions across your AWS infrastructure. CloudTrail provides event history of your AWS account activity, including actions taken through the AWS Management Console, AWS SDKs, command line tools, and other AWS services. This event history simplifies security analysis, resource change tracking, and troubleshooting. In addition, you can use CloudTrail to detect unusual activity in your AWS accounts. These capabilities help simplify operational analysis and troubleshooting.

CloudTrail is enabled by default in every account. All activities in an AWS account are being recorded as CloudTrail events.
* On AWS: <a href="https://aws.amazon.com/cloudtrail/" target="_blank">Service</a> - <a href="https://aws.amazon.com/cloudtrail/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/awscloudtrail/latest/userguide" target="_blank">User Guide</a>

<a name="4_1_2"></a>
### [↖](#4_1)[↑](#4_1_1)[↓](#4_1_2_1) Concepts

<a name="4_1_2_1"></a>
#### [↖](#4_1)[↑](#4_1_2)[↓](#4_1_3) Event
* JSON format, who did what (API calls).
* Up to 15min delay
* Stored for 90 days

<a name="4_1_3"></a>
### [↖](#4_1)[↑](#4_1_2_1)[↓](#4_1_4) Trail
* Can configure what type of events to log
	* Management events
	* CloudWatch Insights events
	* Data events
* One region/all regions/organization-wide
* Store data in nominated S3 bucket, this can be encrypted as well
  * Every 5 min
	* Can be in a different region
* Can also deliver and analyse events in a trail with CloudWatch Logs and CloudWatch Events
* Can validate integrity of log files using digest files
* Can deliver trails from multiple accounts into the same bucket
  * Change bucket policy to allow that
* For global services such as IAM, STS, CloudFront, and Route 53, events are delivered to any trail that includes global services (`IncludeGlobalServiceEvents` flag).

<a name="4_1_4"></a>
### [↖](#4_1)[↑](#4_1_3)[↓](#4_2) Notification options
.|.
-|-
SNS|Can notify SQS/Lambda from there
S3|Can use bucket events from there
Stream into CloudWatch Logs|Can utilize metric filtering and raise alarms
CloudWatch Events|Fastest way, works for every API call

---

<a name="4_2"></a>
## [↖](#top)[↑](#4_1_4)[↓](#4_2_1) KMS
<!-- toc_start -->
* [Overview](#4_2_1)
* [Concepts](#4_2_2)
* [Keys, ownership and management responsibilities](#4_2_3)
  * [Customer master keys (CMKs)](#4_2_3_1)
  * [Customer managed CMKs](#4_2_3_2)
  * [AWS managed CMKs](#4_2_3_3)
  * [AWS owned CMKs](#4_2_3_4)
<!-- toc_end -->
<a name="4_2_1"></a>
### [↖](#4_2)[↑](#4_2)[↓](#4_2_2) Overview
AWS Key Management Service (KMS) makes it easy for you to create and manage cryptographic keys and control their use across a wide range of AWS services and in your applications. AWS KMS is a secure and resilient service that uses hardware security modules that have been validated under FIPS 140-2, or are in the process of being validated, to protect your keys. AWS KMS is integrated with AWS CloudTrail to provide you with logs of all key usage to help meet your regulatory and compliance needs.
* Fully managed
* Centralized key management
* Manage Encryption for AWS services
* Encrypt data in your application
* Built-in auditing
* Low cost
* Secure
* Compliance
* On AWS: <a href="https://aws.amazon.com/kms/" target="_blank">Service</a> - <a href="https://aws.amazon.com/kms/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/kms/latest/developerguide/overview.html" target="_blank">User Guide</a>

<a name="4_2_2"></a>
### [↖](#4_2)[↑](#4_2_1)[↓](#4_2_3) Concepts
* The value in KMS is that the CMK used to encrypt data can never be retrieved by the user, and the CMK can be rotated for extra security
* KMS can only help in encrypting up to 4KB of data per call
* If data > 4 KB, use Envelope Encryption
* To give access to KMS to someone:
  * Make sure the Key Policy allows the user
  * Make sure the IAM Policy allows the API calls
* Track API calls made to KMS in CloudTrail

<a name="4_2_3"></a>
### [↖](#4_2)[↑](#4_2_2)[↓](#4_2_3_1) Keys, ownership and management responsibilities
<a name="4_2_3_1"></a>
#### [↖](#4_2)[↑](#4_2_3)[↓](#4_2_3_2) Customer master keys (CMKs)
* Customer master keys are the primary resources in AWS KMS.
* A customer master key (CMK) is a logical representation of a master key. The CMK includes metadata, such as the key ID, creation date, description, and key state. The CMK also contains the key material used to encrypt and decrypt data.
* Create, manage and use, can enable or disable
* Possibility of rotation policy (new key generated every year, old key preserved)
* Can add a key policy (resource policy)
* Leverage for envelope encryption

<a name="4_2_3_2"></a>
#### [↖](#4_2)[↑](#4_2_3_1)[↓](#4_2_3_3) Customer managed CMKs
Customer managed CMKs are CMKs in your AWS account that you create, own, and manage. You have full control over these CMKs, including establishing and maintaining their key policies, IAM policies, and grants, enabling and disabling them, rotating their cryptographic material, adding tags, creating aliases that refer to the CMK, and scheduling the CMKs for deletion.

<a name="4_2_3_3"></a>
#### [↖](#4_2)[↑](#4_2_3_2)[↓](#4_2_3_4) AWS managed CMKs
AWS managed CMKs are CMKs in your account that are created, managed, and used on your behalf by an AWS service that is integrated with AWS KMS. Some AWS services support only an AWS managed CMK. Others use an AWS owned CMK or offer you a choice of CMKs.

<a name="4_2_3_4"></a>
#### [↖](#4_2)[↑](#4_2_3_3)[↓](#4_3) AWS owned CMKs
AWS owned CMKs are a collection of CMKs that an AWS service owns and manages for use in multiple AWS accounts. Although AWS owned CMKs are not in your AWS account, an AWS service can use its AWS owned CMKs to protect the resources in your account.

---

<a name="4_3"></a>
## [↖](#top)[↑](#4_2_3_4)[↓](#4_3_1) SSM Parameter Store
<!-- toc_start -->
* [Overview](#4_3_1)
<!-- toc_end -->
<a name="4_3_1"></a>
### [↖](#4_3)[↑](#4_3)[↓](#4_4) Overview
AWS Systems Manager Parameter Store provides secure, hierarchical storage for configuration data management and secrets management. You can store data such as passwords, database strings, Amazon Machine Image (AMI) IDs, and license codes as parameter values. You can store values as plain text or encrypted data. You can reference Systems Manager parameters in your scripts, commands, SSM documents, and configuration and automation workflows by using the unique name that you specified when you created the parameter.
* Secure storage for configuration and secrets
* Optional Seamless Encryption using KMS
* Serverless, scalable, durable, easy SDK, free
* Version tracking of configuration/secrets
* Configuration management using path & IAM
* Notifications with CloudWatch Events
* Integration with CloudFormation
* Can retrieve secrets from Secrets Manager using the SSM Parameter Store API
* On AWS: <a href="https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-parameter-store.html" target="_blank">User Guide</a>

---

<a name="4_4"></a>
## [↖](#top)[↑](#4_3_1)[↓](#4_4_1) Secrets Manager
<!-- toc_start -->
* [Overview](#4_4_1)
<!-- toc_end -->
<a name="4_4_1"></a>
### [↖](#4_4)[↑](#4_4)[↓](#4_5) Overview
AWS Secrets Manager helps you protect secrets needed to access your applications, services, and IT resources. The service enables you to easily rotate, manage, and retrieve database credentials, API keys, and other secrets throughout their lifecycle. Users and applications retrieve secrets with a call to Secrets Manager APIs, eliminating the need to hardcode sensitive information in plain text. Secrets Manager offers secret rotation with built-in integration for Amazon RDS, Amazon Redshift, and Amazon DocumentDB. Also, the service is extensible to other types of secrets, including API keys and OAuth tokens. In addition, Secrets Manager enables you to control access to secrets using fine-grained permissions and audit secret rotation centrally for resources in the AWS Cloud, third-party services, and on-premises.
* Newer service, meant for storing secrets
* Capability to force rotation of secrets every X days
* Automate generation of secrets on rotation (uses Lambda)
* Integration with Amazon RDS (MySQL, PostgreSQL, Aurora)
* Secrets are encrypted using KMS
* Mostly meant for RDS integration
* On AWS: <a href="https://aws.amazon.com/secrets-manager/" target="_blank">Service</a> - <a href="https://aws.amazon.com/secrets-manager/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/secretsmanager/latest/userguide/intro.html" target="_blank">User Guide</a>

---

<a name="4_5"></a>
## [↖](#top)[↑](#4_4_1)[↓](#4_5_1) RDS Security
<!-- toc_start -->
* [Overview](#4_5_1)
<!-- toc_end -->
<a name="4_5_1"></a>
### [↖](#4_5)[↑](#4_5)[↓](#4_6) Overview
* KMS encryption at rest for underlying EBS volumes/snapshots
* Transparent Data Encryption (TDE) for Oracle and SQL Server
* SSL encryption to RDS is possible for all DB (in-flight)
* IAM authentication (only) for MySQL and PostgreSQL
* Authorization still happens within RDS (not in IAM)
* Can copy an un-encrypted RDS snapshot into an encrypted one
* CloudTrail cannot be used to track queries made within RDS

---

<a name="4_6"></a>
## [↖](#top)[↑](#4_5_1)[↓](#4_6_1) SSL/SNI/MITM/DNSSEC
<!-- toc_start -->
* [SSL Basics](#4_6_1)
* [SSL Handshake](#4_6_2)
* [Server Name Indication (SNI)](#4_6_3)
* [Man-In-The-Middle (MITM)](#4_6_4)
<!-- toc_end -->

<a name="4_6_1"></a>
### [↖](#4_6)[↑](#4_6)[↓](#4_6_2) SSL Basics
* SSL refers to Secure Sockets Layer, used to encrypt connections
* TLS refers to Transport Layer Security, which is a newer version
* Nowadays, TLS certificates are mainly used, but people still refer as SSL
* Public SSL certificates are issued by Certificate Authorities (CA)
  * Comodo, Symantec, GoDaddy, GlobalSign, Digicert, Letsencrypt, etc...
* SSL certificates have an expiration date (you set) and must be renewed

<a name="4_6_2"></a>
### [↖](#4_6)[↑](#4_6_1)[↓](#4_6_3) SSL Handshake
Client|Server
-|-
Client sends hello, cipher suits & random|.
.|Server Response with server random & SSL certificate (Public Key)
Master key (symmetric) generated and sent encrypted using the Public Key|.
.|Server verifies Client SSL cert (optional)
.|Master key is decrypted using Private Key
Secure Symmetric ..|..Communication in Place

* Asymmetric encrytion (expensive) for handshake only, symmetric after that
* Possibility of client sending an SSL certificate as well (two-way certificate)

<a name="4_6_3"></a>
### [↖](#4_6)[↑](#4_6_2)[↓](#4_6_4) Server Name Indication (SNI)
* SNI solves the problem of loading multiple SSL certificates onto one web server (to serve multiple websites)
  * `www.aaa.com`, `www.bbb.com`, ...
* It’s a “newer” protocol, and requires the client to indicate the hostname of the target server in the initial SSL handshake
* The server will then find the correct certificate, or return the default one
  * Has multiple certificates configured
* Supported by ALB and NLB only, not supported by ELB

<a name="4_6_4"></a>
### [↖](#4_6)[↑](#4_6_3)[↓](#4_7) Man-In-The-Middle (MITM)
* The attacker secretly relays and possibly alters the communications between two parties who believe that they are directly communicating with each other.
* How to prevent
  * Don’t use public-facing HTTP, use HTTPS (meaning, use SSL/TLS certicates)
  * Use a DNS that has DNSSEC
    * To end send a client to a pirate server, a DNS response needs to be “forged” by a server which intercepts them
    * It is possible to protect your domain name by configuring DNSSEC
		* Route 53 now supports full DNSSEC (12/2020)
    * ~~Amazon Route 53 supports DNSSEC for domain registration. However, Route 53 does not support DNSSEC for DNS service, regardless of whether the domain is registered with Route 53. If you want to configure DNSSEC for a domain that is registered with Route 53, you must use another DNS service provider.~~
    * You can also run a custom DNS server on EC2

---

<a name="4_7"></a>
## [↖](#top)[↑](#4_6_4)[↓](#4_7_1) AWS Certificate Manager
<!-- toc_start -->
* [Overview](#4_7_1)
<!-- toc_end -->
<a name="4_7_1"></a>
### [↖](#4_7)[↑](#4_7)[↓](#4_8) Overview
AWS Certificate Manager is a service that lets you easily provision, manage, and deploy public and private Secure Sockets Layer/Transport Layer Security (SSL/TLS) certificates for use with AWS services and your internal connected resources. SSL/TLS certificates are used to secure network communications and establish the identity of websites over the Internet as well as resources on private networks. AWS Certificate Manager removes the time-consuming manual process of purchasing, uploading, and renewing SSL/TLS certificates.

With AWS Certificate Manager, you can quickly request a certificate, deploy it on ACM-integrated AWS resources, such as Elastic Load Balancers, Amazon CloudFront distributions, and APIs on API Gateway, and let AWS Certificate Manager handle certificate renewals. It also enables you to create private certificates for your internal resources and manage the certificate lifecycle centrally. Public and private certificates provisioned through AWS Certificate Manager for use with ACM-integrated services are free. You pay only for the AWS resources you create to run your application. With AWS Certificate Manager Private Certificate Authority, you pay monthly for the operation of the private CA and for the private certificates you issue.
* To host public SSL certificates in AWS, you can:
  * Buy your own and upload them using the CLI
  * Have ACM provision and renew public SSL certificates for you (free of cost)
* ACM loads SSL certificates on the following integrations:
  * Load Balancers (including the ones created by EB)
  * CloudFront distributions
  * APIs on API Gateways
* Possibility of creating public certificates
  * Must verify public DNS (verify that you own or control all of the domain names that you specified in your request)
  * Must be issued by a trusted public certificate authority (CA)
* Possibility of creating private certificates
  * For your internal applications
  * You create your own private CA
  * Your applications must trust your private CA
* Certificate renewal:
  * Automatically done if generated provisioned by ACM
  * Any manually uploaded certificates must be renewed manually and re-uploaded
* ACM is a regional service
  * To use with a global application (multiple ALB for example), you need to issue an SSL certificate **in each region** where you application is deployed.
  * You cannot copy certs across regions
* On AWS: <a href="https://aws.amazon.com/certificate-manager/" target="_blank">Service</a> - <a href="https://aws.amazon.com/certificate-manager/faqs/?nc=sn&loc=5" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/acm/latest/userguide/acm-overview.html" target="_blank">User Guide</a>

---

<a name="4_8"></a>
## [↖](#top)[↑](#4_7_1)[↓](#4_8_1) CloudHSM
<!-- toc_start -->
* [Overview](#4_8_1)
* [CloudHSM vs KMS](#4_8_2)
<!-- toc_end -->
<a name="4_8_1"></a>
### [↖](#4_8)[↑](#4_8)[↓](#4_8_2) Overview
AWS CloudHSM provides hardware security modules in the AWS Cloud. A hardware security module (HSM) is a computing device that processes cryptographic operations and provides secure storage for cryptographic keys.

When you use an HSM from AWS CloudHSM, you can perform a variety of cryptographic tasks:
* Generate, store, import, export, and manage cryptographic keys, including symmetric keys and asymmetric key pairs.
* Use symmetric and asymmetric algorithms to encrypt and decrypt data.
* Use cryptographic hash functions to compute message digests and hash-based message authentication codes (HMACs).
* Cryptographically sign data (including code signing) and verify signatures.
* Generate cryptographically secure random data.

If you want a managed service for creating and controlling your encryption keys, but you don't want or need to operate your own HSM, consider using AWS KMS.
* You manage your own encryption keys entirely (not AWS)
* HSM device is tamper resistant, FIPS 140-2 Level 3 compliance
* Supports both symmetric and asymmetric encryption (SSL/TLS keys)
* No free tier available
* Must use the CloudHSM Client Software
* Redshift supports CloudHSM for database encryption and key management
* Good option to use with SSE-C encryption
* Can be deployed into a cluster for HA
* Can perform SSL offloading, to free up compute on the server
  * Also, this keeps the private key on CloudHSM
* CloudHSM is deployed in a cluster
	* A cluster is a collection of individual HSMs that AWS CloudHSM keeps in sync
	* You can place the HSMs in different Availability Zones in an AWS Region
	* When you create an HSM, AWS CloudHSM puts an elastic network interface (ENI) in the specified subnet in your AWS account.
* On AWS: <a href="https://aws.amazon.com/cloudhsm/" target="_blank">Service</a> - <a href="https://aws.amazon.com/cloudhsm/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/cloudhsm/latest/userguide/introduction.html" target="_blank">User Guide</a>

<a name="4_8_2"></a>
### [↖](#4_8)[↑](#4_8_1)[↓](#4_9) CloudHSM vs KMS

Feature|KMS|CloudHSM
-|-|-
Tenancy|Uses multi-tenant key storage|Single tenant key storage, dedicated to one customer
Keys|Keys owned and managed by AWS|Customer managed Keys
Encryption|Symmetric and asymmetric (*new*) encryption|Supports both symmetric and asymmetric encryption
Cryptographic Acceleration|None|SSL/TLS Acceleration Oracle TDE Acceleration
Key Storage and Management|Accessible from multiple regions<br/>Centralized management from IAM|Deployed and managed from a customer VPC.<br/>Accessible and can be shared across VPCs using VPC peering<br/>No IAM integration on user/key level
Free Tier Availability|Yes|No

---

<a name="4_9"></a>
## [↖](#top)[↑](#4_8_2)[↓](#4_9_1) S3 Security
<!-- toc_start -->
* [S3 Encryption for objects](#4_9_1)
* [Encryption in transit](#4_9_2)
* [Events in S3 buckets](#4_9_3)
* [S3 Security](#4_9_4)
  * [User-based](#4_9_4_1)
  * [Resource-based](#4_9_4_2)
* [S3 pre-signed URLs](#4_9_5)
* [S3 WORM](#4_9_6)
<!-- toc_end -->

<a name="4_9_1"></a>
### [↖](#4_9)[↑](#4_9)[↓](#4_9_2) S3 Encryption for objects
* There are 4 methods of encrypting objects in S3
  * **SSE-S3**: encrypts S3 objects using keys handled & managed by AWS
  * **SSE-KMS**: leverage AWS Key Management Service to manage encryption keys
  * **SSE-C**: when you want to manage your own encryption keys
  * **Client Side Encryption**
* Glacier
  * All data is AES-256 encrypted, key under AWS control

<a name="4_9_2"></a>
### [↖](#4_9)[↑](#4_9_1)[↓](#4_9_3) Encryption in transit
AWS S3 exposes:
* HTTP endpoint: non encrypted
* HTTPS endpoint: encryption in flight
  * Mandatory for SSE-C
* Encryption in flight is also called SSL/TLS

<a name="4_9_3"></a>
### [↖](#4_9)[↑](#4_9_2)[↓](#4_9_4) Events in S3 buckets
S3 Access Logs:
* Detailed records for the requests that are made to a bucket
* Might take hours to deliver
* Might be incomplete (best effort)

S3 Events Notifications:
* Receive notifications when certain events happen in your bucket
  * E.g.: new objects created, object removal, restore objects, replication events
  * Destinations: SNS, SQS queue, Lambda
* Typically delivered in seconds but can take minutes, notification for every object if versioning
is enabled, else risk of one notification for two same object write done simultaneously

Trusted Advisor:
* Check the bucket permission (is the bucket public?)

CloudWatch Events:
* Need to enable CloudTrail object level logging on S3 first
* Target can be Lambda, SQS, SNS, etc...

<a name="4_9_4"></a>
### [↖](#4_9)[↑](#4_9_3)[↓](#4_9_4_1) S3 Security
<a name="4_9_4_1"></a>
#### [↖](#4_9)[↑](#4_9_4)[↓](#4_9_4_2) User-based
**IAM**
* IAM policies (in general) specify what actions are allowed or denied on what AWS resources
* Defined as JSON
* Attached to IAM users, groups, or roles (so they cannot grant access to anonymous users)
* Use if you’re more interested in *“What can this user do in AWS?”*

<a name="4_9_4_2"></a>
#### [↖](#4_9)[↑](#4_9_4_1)[↓](#4_9_5) Resource-based
**Bucket policies**
* Specify what actions are allowed or denied for which principals on the bucket that the policy is attached to
* Defined as JSON
* Attached *only* to S3 buckets. Can however effect object in buckets.
* Contain *principal* element (unnecessary for IAM)
* Use if you’re more interested in *“Who can access this S3 bucket?”*
* Easiest way to grant *cross-account permissions* for all `s3:*` permission. (Cannot do this with ACLs.)
* Optional Conditions on:
  * Public IP or Elastic IP (*not* on Private IP)
  * Source VPC or Source VPC Endpoint – only works with VPC Endpoints
  * CloudFront Origin Identity
  * MFA
* <a href="https://docs.aws.amazon.com/AmazonS3/latest/dev/example-bucket-policies.html" target="_blank">On AWS</a>
**ACL**
* Defined as XML. Legacy, not recomended any more.
* Can
	* be attached to individual objects (bucket policies only bucket level)
	* control access to object uploaded into a bucket from a *different* account.
* Cannot..
	* have conditions
	* cannot explicitely deny actions
	* grant permission to bucket sub-resources (eg. lifecycle or static website configurations)
* Other than *object ACL*s there are *bucket ACL*s as well - only for writing access log objects to a bucket.
  * Bucket Policies - bucket wide rules from the S3 console - allows cross account

<a name="4_9_5"></a>
### [↖](#4_9)[↑](#4_9_4_2)[↓](#4_9_6) S3 pre-signed URLs
Can generate pre-signed URLs using SDK or CLI
* For downloads (easy, can use the CLI)
* For uploads (harder, must use the SDK)
* Valid for a default of 3600 seconds, can change timeout with `--expires-in [TIME_BY_SECONDS]` argument
* Users given a pre-signed URL inherit the permissions of the person who generated the URL for GET/PUT
* Examples
  * Allow only logged-in users to download a premium video on your S3 bucket
  * Allow an ever changing list of users to download files by generating URLs dynamically
  * Allow temporarily a user to upload a file to a precise location in our bucket

<a name="4_9_6"></a>
### [↖](#4_9)[↑](#4_9_5)[↓](#4_10) S3 WORM
**S3 Object Lock**
* Adopt a WORM (Write Once Read Many) model
* Block an object version deletion for a specified amount of time Object
**Glacier Vault Lock**
* Adopt a WORM (Write Once Read Many) model
* Lock the policy for future edits (can no longer be changed)
* Helpful for compliance and data retention

---

<a name="4_10"></a>
## [↖](#top)[↑](#4_9_6)[↓](#4_10_1) Network Security, DDOS, Shield, WAF and Firewall Manager
<!-- toc_start -->
* [Network Security](#4_10_1)
* [Preventing Infrastructure Attacks](#4_10_2)
  * [Types of attacks](#4_10_2_1)
  * [DDOS Protection](#4_10_2_2)
* [AWS Shield](#4_10_3)
* [AWS WAF](#4_10_4)
* [AWS Firewall Manager](#4_10_5)
<!-- toc_end -->
<a name="4_10_1"></a>
### [↖](#4_10)[↑](#4_10)[↓](#4_10_2) Network Security
**Security Groups**
* Attached to ENI (Elastic Network Interfaces) – EC2, RDS, Lambda in VPC, etc
* Are stateful (any traffic in is allowed to go out, any traffic out can go back in)
* Can reference by CIDR and security group id
* Supports security group references for VPC peering
* Default: inbound denied, outbound all allowed
**NACL (Network ACL)**
* Attached at the subnet level
* Are stateless (inbound and outbound rules apply for all traffic)
* Can only reference a CIDR range (no hostname)
* Default: allow all inbound, allow all outbound
* New NACL: denies all inbound, denies all outbound
**Host Firewall**
* Software based, highly customizable

<a name="4_10_2"></a>
### [↖](#4_10)[↑](#4_10_1)[↓](#4_10_2_1) Preventing Infrastructure Attacks

<a name="4_10_2_1"></a>
#### [↖](#4_10)[↑](#4_10_2)[↓](#4_10_2_2) Types of attacks
* DDOS
  * Flooding - layer 4
* Application level attacks
  * E.g. cache burst via http - layer 7

<a name="4_10_2_2"></a>
#### [↖](#4_10)[↑](#4_10_2_1)[↓](#4_10_3) DDOS Protection
* AWS Shield Standard: protects against DDoS attack for your website and applications, for all customers at no additional costs
* AWS Shield Advanced: 24/7 premium DDoS protection
* AWS WAF: Filter specific requests based on rules
* CloudFront and Route 53
  * Availability protection using global edge network
  * Combined with AWS Shield, provides DDoS attack mitigation at the edge
* Be ready to scale – leverage AWS Auto Scaling
* Separate static resources (S3/CloudFront) from dynamic ones (EC2/ALB)

<a name="4_10_3"></a>
### [↖](#4_10)[↑](#4_10_2_2)[↓](#4_10_4) AWS Shield
You can use AWS WAF web access control lists (web ACLs) to help minimize the effects of a distributed denial of service (DDoS) attack. For additional protection against DDoS attacks, AWS also provides AWS Shield Standard and AWS Shield Advanced. AWS Shield Standard is automatically included at no extra cost beyond what you already pay for AWS WAF and your other AWS services. AWS Shield Advanced provides expanded DDoS attack protection for your Amazon EC2 instances, Elastic Load Balancing load balancers, CloudFront distributions, Route 53 hosted zones, and AWS Global Accelerator accelerators. AWS Shield Advanced incurs additional charges.
* AWS Shield Standard
  * Free service that is activated for every AWS customer
  * Provides protection from attacks such as SYN/UDP Floods, Reflection attacks and other layer 3/layer 4 attacks
* AWS Shield Advanced
  * Optional DDoS mitigation service ($3,000 per month per organization)
  * Protect against more sophisticated attack on Amazon EC2, Elastic Load Balancing (ELB), Amazon CloudFront, AWS Global Accelerator, and Route 53
  * 24/7 access to AWS DDoS response team (DRP)
  * Protect against higher fees during usage spikes due to DDoS
* On AWS: <a href="https://aws.amazon.com/shield/" target="_blank">Service</a> - <a href="https://aws.amazon.com/shield/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/waf/latest/developerguide/shield-chapter.html" target="_blank">User Guide</a>

<a name="4_10_4"></a>
### [↖](#4_10)[↑](#4_10_3)[↓](#4_10_5) AWS WAF
AWS WAF is a web application firewall that lets you monitor the HTTP and HTTPS requests that are forwarded to an Amazon CloudFront distribution, an Amazon API Gateway REST API, an Application Load Balancer, or an AWS AppSync GraphQL API. AWS WAF also lets you control access to your conten . Based on conditions that you specify, such as the IP addresses that requests originate from or the values of query strings, Amazon CloudFront, Amazon API Gateway, Application Load Balancer, or AWS AppSync responds to requests either with the requested content or with an HTTP 403 status code (Forbidden). You also can configure CloudFront to return a custom error page when a request is blocked.
* Protects your web applications from common web exploits (Layer 7)
* Deploy on Application Load Balancer (localized rules)
* Deploy on API Gateway (rules running at the regional or edge level)
* Deploy on CloudFront (rules globally on edge locations)
  * Used to front other solutions: CLB, EC2 instances, custom origins, S3 websites)
* WAF is not for DDoS protection
* Define Web ACL (Web Access Control List):
  * Rules can include: IP addresses, HTTP headers, HTTP body, or URI strings
  * Protects from common attack - SQL injection and Cross-Site Scripting (XSS)
  * Size constraints, Geo match
  * Rate-based rules (to count occurrences of events)
	* Web ACL can be associated with CloudFront distribution
* On AWS: <a href="https://aws.amazon.com/waf/" target="_blank">Service</a> - <a href="https://aws.amazon.com/waf/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/waf/latest/developerguide/what-is-aws-waf.html" target="_blank">User Guide</a>

<a name="4_10_5"></a>
### [↖](#4_10)[↑](#4_10_4)[↓](#4_11) AWS Firewall Manager
AWS Firewall Manager simplifies your administration and maintenance tasks across multiple accounts and resources for AWS WAF, AWS Shield Advanced, Amazon VPC security groups, and AWS Network Firewall. With Firewall Manager, you set up your AWS WAF firewall rules, Shield Advanced protections, Amazon VPC security groups, and Network Firewall firewalls just once. The service automatically applies the rules and protections across your accounts and resources, even as you add new resources.

Firewall Manager provides these benefits:
* Helps to protect resources across accounts
* Helps to protect all resources of a particular type, such as all Amazon CloudFront distributions
* Helps to protect all resources with specific tags
* Automatically adds protection to resources that are added to your account
* Allows you to subscribe all member accounts in an AWS Organizations organization to AWS Shield Advanced, and automatically subscribes new in-scope accounts that join the organization
* Allows you to apply security group rules to all member accounts or specific subsets of accounts in an AWS Organizations organization, and automatically applies the rules to new in-scope accounts that join the organization
* Lets you use your own rules, or purchase managed rules from AWS Marketplace

Summary
* Manage rules in all accounts of an AWS Organization
* Common set of security rules
* WAF rules (Application Load Balancer, API Gateways, CloudFront)
* AWS Shield Advanced (ALB, CLB, Elastic IP, CloudFront)
* Security Groups for EC2 and ENI resources in VPC
* On AWS: <a href="https://aws.amazon.com/firewall-manager/" target="_blank">Service</a> - <a href="https://aws.amazon.com/firewall-manager/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/waf/latest/developerguide/fms-chapter.html" target="_blank">User Guide</a>

---

<a name="4_11"></a>
## [↖](#top)[↑](#4_10_5)[↓](#4_12) Blocking IP addresses
* `client` -> `vpc` -> `ec2`
  * Use NACL, firewall on ec2
* `client` -> `vpc` -> `ALB/ELB` -> `ec2`
  * Use NACL
  * Use WAF on ALB/ELB
* `client` -> `vpc` -> `NLB` -> `ec2`
  * Use NACL
* `client` -> `CloudFront` -> `vpc` -> `NLB` -> `ec2`
  * Can't use NACL as CloudFront forwards from its own IP range
  * USe WAF on CloudFront

---

<a name="4_12"></a>
## [↖](#top)[↑](#4_11)[↓](#4_12_1) Amazon Inspector
<!-- toc_start -->
* [Overview](#4_12_1)
<!-- toc_end -->

<a name="4_12_1"></a>
### [↖](#4_12)[↑](#4_12)[↓](#4_13) Overview
Amazon Inspector is an automated security assessment service that helps improve the security and compliance of applications deployed on AWS. Amazon Inspector automatically assesses applications for exposure, vulnerabilities, and deviations from best practices. After performing an assessment, Amazon Inspector produces a detailed list of security findings prioritized by level of severity. These findings can be reviewed directly or as part of detailed assessment reports which are available via the Amazon Inspector console or API.

Amazon Inspector security assessments help you check for unintended network accessibility of your Amazon EC2 instances and for vulnerabilities on those EC2 instances. Amazon Inspector assessments are offered to you as pre-defined rules packages mapped to common security best practices and vulnerability definitions. Examples of built-in rules include checking for access to your EC2 instances from the internet, remote root login being enabled, or vulnerable software versions installed. These rules are regularly updated by AWS security researchers.
* **Network Assessments**
  * Does not require agent
* **Host Assessments**
  * Requires agent
* Can automate assessments via scheduled CloudWatch Events
  * Can use tag to find instances to asses
  * Cannot launch AMI, requires instance
* Assessment templates can notify SNS
  * Could trigger Lambda to remediate EC2 findings via SSM documents
* On AWS: <a href="https://aws.amazon.com/inspector/" target="_blank">Service</a> - <a href="https://aws.amazon.com/inspector/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/inspector/latest/userguide/" target="_blank">User Guide</a>

---

<a name="4_13"></a>
## [↖](#top)[↑](#4_12_1)[↓](#4_13_1) Config
<!-- toc_start -->
* [Overview](#4_13_1)
* [Config Rules](#4_13_2)
* [Automation](#4_13_3)
* [Aggregation](#4_13_4)
<!-- toc_end -->

<a name="4_13_1"></a>
### [↖](#4_13)[↑](#4_13)[↓](#4_13_2) Overview
*AWS Config* is a service that enables you to assess, audit, and evaluate the configurations of your
AWS resources. Config continuously monitors and records your AWS resource configurations and allows you to automate the evaluation of recorded configurations against desired configurations. With Config, you can review changes in configurations and relationships between AWS resources, dive into detailed resource configuration histories, and determine your overall compliance against the configurations specified in your internal guidelines. This enables you to simplify compliance auditing, security analysis, change management, and operational troubleshooting.
* Evaluate your AWS resource configurations for desired settings.
* Get a snapshot of the current configurations of the supported resources that are associated with your AWS account.
* Retrieve configurations of one or more resources that exist in your account.
* Retrieve historical configurations of one or more resources.
* Receive a notification whenever a resource is created, modified, or deleted.
* View relationships between resources. For example, you might want to find all resources that use a particular security group.
* Do not prevent actions from happening (no deny)
* Can have auto-remediation
  * Via SSM Automations
* On AWS: <a href="https://aws.amazon.com/config/" target="_blank">Service</a> - <a href="https://aws.amazon.com/config/faq/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/config/latest/developerguide/WhatIsConfig.html" target="_blank">User Guide</a>

<a name="4_13_2"></a>
### [↖](#4_13)[↑](#4_13_1)[↓](#4_13_3) Config Rules
* Evaluate the configuration settings of AWS resources
* A Config rule represents your ideal configuration settings
* Predefined rules called *managed rules* to help you get started
* Can also create *custom rules*
* AWS Config continuously tracks the configuration changes that occur among your resources
	* Checks whether these changes violate any of the conditions in your rules.
	* If a resource violates a rule, AWS Config flags the resource and the rule as *noncompliant*.
* Can remediate using AWS Systems Manager Automation Documents

<a name="4_13_3"></a>
### [↖](#4_13)[↑](#4_13_2)[↓](#4_13_4) Automation
* SNS notification on *all* Config events (cannot configure which events)
* CloudWatch Events to observe *specific* events/rules

<a name="4_13_4"></a>
### [↖](#4_13)[↑](#4_13_3)[↓](#4_14) Aggregation
An aggregator is an AWS Config resource type that collects AWS Config configuration and compliance data from the following:
* Multiple accounts and multiple regions.
* Single account and multiple regions.
* An organization in AWS Organizations and all the accounts in that organization.
* Is limited to 50 per account
  * *"We are unable to complete the request at this time. Try again later or contact AWS Support"*

---

<a name="4_14"></a>
## [↖](#top)[↑](#4_13_4)[↓](#4_15) AWS Managed Logs (Core Topic)

.|S3|CloudWatch<br/>Logs|.
-|-|-|-
**Load Balancer** Access Logs (ALB, NLB, ELB)|+|.|Access logs for your Load Balancers
**CloudTrail** Logs|+|+|Logs for API calls made within your account
**VPC Flow Logs**|+|+|Information about IP traffic going to and from network interfaces in your VPC
**Route 53** Access Logs|.|+|Log information about the queries that Route 53 receives
**S3 Access Logs**|+|.|Server access logging provides detailed records for the requests that are made to a bucket
**CloudFront** Access Logs|+|.|Detailed information about every user request that CloudFront receives
**CloudWatch Logs**|.|+|.
**AWS Config**|+|.|Provides an inventory of your AWS resources and records changes to their configuration

---

<a name="4_15"></a>
## [↖](#top)[↑](#4_14)[↓](#4_15_1) GuardDuty
<!-- toc_start -->
* [Overview](#4_15_1)
<!-- toc_end -->

<a name="4_15_1"></a>
### [↖](#4_15)[↑](#4_15)[↓](#5) Overview
Amazon GuardDuty is a threat detection service that continuously monitors for malicious activity and unauthorized behavior to protect your AWS accounts and workloads. With the cloud, the collection and aggregation of account and network activities is simplified, but it can be time consuming for security teams to continuously analyze event log data for potential threats. With GuardDuty, you now have an intelligent and cost-effective option for continuous threat detection in the AWS Cloud. The service uses machine learning, anomaly detection, and integrated threat intelligence to identify and prioritize potential threats. GuardDuty analyzes tens of billions of events across multiple AWS data sources, such as AWS CloudTrail, Amazon VPC Flow Logs, and DNS log. With a few clicks in the AWS Management Console, GuardDuty can be enabled with no software or hardware to deploy or maintain. By integrating with Amazon CloudWatch Events, GuardDuty alerts are actionable, easy to aggregate across multiple accounts, and straightforward to push into existing event management and workflow systems.
* Analyses AWS CloudTrail, Amazon VPC Flow Logs, and DNS log
* Integrates with CloudWatch Events
* On AWS: <a href="https://aws.amazon.com/guardduty/" target="_blank">Service</a> - <a href="https://aws.amazon.com/guardduty/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/guardduty/latest/userguide/" target="_blank">User Guide</a>
* See also: <a href="https://www.awsgeek.com/Amazon-GuardDuty/Amazon-GuardDuty.jpg" target="_blank">AWS Geek 2020</a>

---

<a name="5"></a>
# [↖](#top)[↑](#4_15_1)[↓](#5_1) Compute & Load Balancing
<a name="5_1"></a>
## [↖](#top)[↑](#5)[↓](#5_1_1) AWS Solution Architectures
<!-- toc_start -->
* [Web/Internet Layer](#5_1_1)
* [Computer Layer](#5_1_2)
* [Backend](#5_1_3)
<!-- toc_end -->

<a name="5_1_1"></a>
### [↖](#5_1)[↑](#5_1)[↓](#5_1_2) Web/Internet Layer

DNS|Static Content|Dynamic Contnet
-|-|-
Route 53|CloudFront|Elastic LB, API Gateway, Elastic IP

<a name="5_1_2"></a>
### [↖](#5_1)[↑](#5_1_1)[↓](#5_1_3) Computer Layer

Computer|Serverless|Other
-|-|-
EC2, ASG, ECS|Lambda, Fargate|Batch, EMR

<a name="5_1_3"></a>
### [↖](#5_1)[↑](#5_1_2)[↓](#5_2) Backend

Caching/Session Layer|Database Layer|Decoupling Orchestration Layer|Storage Layer|Static Assets Layer (storage)
-|-|-|-|-
ElastiCache, DAX,<br/>DynamoDB, RDS|RDS, Aurora, DynamoDB<br/>ElasticSearch, S3, Redshift|SQS, SNS, Kinesis<br/>Amazon MQ, Step Functions|EBS, EFS, Instance Store<br/>CDN Layer|S3, Glacier

---

<a name="5_2"></a>
## [↖](#top)[↑](#5_1_3)[↓](#5_2_1) EC2
<!-- toc_start -->
* [Overview](#5_2_1)
* [Instance Types](#5_2_2)
* [Placement Groups](#5_2_3)
* [Key metrics for EC2](#5_2_4)
* [EC2 Instance Recovery](#5_2_5)
<!-- toc_end -->
<a name="5_2_1"></a>
### [↖](#5_2)[↑](#5_2)[↓](#5_2_2) Overview
Amazon Elastic Compute Cloud (Amazon EC2) is a web service that provides secure, resizable compute capacity in the cloud. It is designed to make web-scale cloud computing easier for developers. Amazon EC2’s simple web service interface allows you to obtain and configure capacity with minimal friction. It provides you with complete control of your computing resources and lets you run on Amazon’s proven computing environment. Amazon EC2 offers the broadest and deepest compute platform with choice of processor, storage, networking, operating system, and purchase model. We offer the fastest processors in the cloud and we are the only cloud with 400 Gbps ethernet networking. We have the most powerful GPU instances for machine learning training and graphics workloads, as well as the lowest cost-per-inference instances in the cloud.
* On AWS: <a href="https://aws.amazon.com/ec2/" target="_blank">Service</a> - <a href="https://aws.amazon.com/ec2/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/ec2/" target="_blank">User Guide</a>

<a name="5_2_2"></a>
### [↖](#5_2)[↑](#5_2_1)[↓](#5_2_3) Instance Types
Family|Mnemomic|Description
-|-|-
**F**|FPGA|Can be reprogrammed on the fly and be tuned for  specific applications, making them faster than traditional CPU/GPU combinations
**I**(*)|IOPS|(NVMe) SSD-backed instance storage optimized for low latency
**G**(*)|Graphics|GPU optimized
**H**|High disk throughput|HDD-based local storage
**T**|Cheap general purpose|Balance of computer, memory and networking, bustable
**D**|Density|Lowest price per disk throughput performance
**R**(*)|RAM|Lowest prize for *memory* performance
**M**(*)|Main choice for general purpose apps|Balance of computer, memory and networking (think: medium)
**C**(*)|Compute|Lowest prize for *compute* performance
**P**|Graphics (pics)|GPU optimized
**X**|eXtreme memory|Lowest prize for *memory* performance

(*) - main types

<a name="5_2_3"></a>
### [↖](#5_2)[↑](#5_2_2)[↓](#5_2_4) Placement Groups
* Determine how instances are placed on underlying hardware
* Recommendation to stick to one instance family
* Cannot move running instance into placement group
  * First stop, then use CLI (`modify-instance-placement`)

Strategy|Pro|Con|Use case
-|-|-|-
**Cluster**|Oldest/original placement group<br/>Only certain instances can be launched into a clustered placement group<br/>Should use instances with *enhanced networking*|Great network (10 Gbps bandwidth between instances)|If the rack fails, all instances fails at the same time|Big Data job that needs to complete fast<br/>Application that needs extremely low latency and high network throughput
**Spread**|Spreads instances across underlying hardware<br/>Minimizes risk as instances are spread<br/>Opposite of clustered placement group<br/>Up to 7 instances per AZ|Can span across Availability Zones (AZ)<br/>Reduced risk is simultaneous failure<br/>EC2 Instances are on different physical hardware|Limited to 7 instances per AZ per placement group|Application that needs to maximize high availability<br/>Critical Applications where each instance must be isolated from failure from each other
**Partitions**|Spreads instances across many partitions (different sets of racks) within one AZ<br/>Groups of instances in one partition do not share the underlying hardware with groups of instances in different partitions.<br/>Typically used by large distributed and replicated workloads, such as Hadoop, Cassandra, and Kafka.|Increased resilience|./.|Hadoop, Cassandra, and Kafka

<a href="https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/placement-groups.html" target="_blank">On AWS</a>

<a name="5_2_4"></a>
### [↖](#5_2)[↑](#5_2_3)[↓](#5_2_5) Key metrics for EC2
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

<a name="5_2_5"></a>
### [↖](#5_2)[↑](#5_2_4)[↓](#5_3) EC2 Instance Recovery
You can create an Amazon CloudWatch alarm that monitors an Amazon EC2 instance and automatically recovers the instance if it becomes impaired due to an underlying hardware failure or a problem that requires AWS involvement to repair (`StatusCheckFailed_System`). Terminated instances cannot be recovered. A recovered instance is identical to the original instance, including the instance ID, private IP addresses, Elastic IP addresses, and all instance metadata. If the impaired instance is in a placement group, the recovered instance runs in the placement group.

If your instance has a public IPv4 address, it retains the public IPv4 address after recovery.

---

<a name="5_3"></a>
## [↖](#top)[↑](#5_2_5)[↓](#5_3_1) Auto Scaling (Core Topic)
<!-- toc_start -->
* [Overview](#5_3_1)
* [Components](#5_3_2)
  * [Auto Scaling Group](#5_3_2_1)
  * [Launch Configuration](#5_3_2_2)
  * [Launch Template](#5_3_2_3)
  * [Termination Policy](#5_3_2_4)
  * [Scaling Processes](#5_3_2_5)
  * [Deploying with ASGs](#5_3_2_6)
<!-- toc_end -->

<a name="5_3_1"></a>
### [↖](#5_3)[↑](#5_3)[↓](#5_3_2) Overview
*Amazon EC2 Auto Scaling* helps you ensure that you have the correct number of Amazon EC2 instances available to handle the load for your application. You create collections of EC2 instances, called *Auto Scaling Groups*. You can specify the **minimum** number of instances in each Auto Scaling Group, and Amazon EC2 Auto Scaling ensures that your group never goes below this size. You can specify the **maximum** number of instances in each Auto Scaling Group, and Amazon EC2 Auto Scaling ensures that your group never goes above this size. If you specify the **desired** capacity, either when you create the group or at any time thereafter, Amazon EC2 Auto Scaling ensures that your group has this many instances. If you specify **scaling policies**, then Amazon EC2 Auto Scaling can launch or terminate instances as demand on your application increases or decreases.
* *Spot Fleet* support (mix on Spot and On-Demand instances)
  * Also configure ratio between these instance options
* To upgrade an AMI, must update the launch configuration/template
  * How do you phase out older launch configurations?
  * How do you test a new launch configuration?
  * You must terminate instances manually (new feature: *Instance Refresh within Auto Scaling Groups*)
* Scheduled scaling actions:
  * Modify the ASG settings (min/max/desired) at pre-defined time
  * Helpful when patterns are known in advance
* Auto scaling can play a major role in deployments
  * Need to avoid downtime during deployments
  * How long does it take to deploy code and configure an instance?
* Use lifecycle hooks for custom actions
* Scale out/scale in
* On AWS: <a href="https://aws.amazon.com/autoscaling/" target="_blank">Service</a> - <a href="https://aws.amazon.com/autoscaling/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/autoscaling" target="_blank">User Guide</a>

<a name="5_3_2"></a>
### [↖](#5_3)[↑](#5_3_1)[↓](#5_3_2_1) Components

<a name="5_3_2_1"></a>
#### [↖](#5_3)[↑](#5_3_2)[↓](#5_3_2_2) Auto Scaling Group
* Contains a collection of Amazon EC2 instances that are treated as a logical grouping for the purposes of automatic scaling and management
* To use Amazon EC2 Auto Scaling features such as health check replacements and scaling policies

<a name="5_3_2_2"></a>
#### [↖](#5_3)[↑](#5_3_2_1)[↓](#5_3_2_3) Launch Configuration
* Instance configuration template that an Auto Scaling Group uses to launch EC2 instances
* One Launch Configuration per ASG, can be used in many ASGs though
* Can't be modified, needs to be recreated
* To change instance type, copy the old Launch Configuration, change instance type, double *max* and *desired*, wait till new values have propagated, revert *max* and *desired*

<a name="5_3_2_3"></a>
#### [↖](#5_3)[↑](#5_3_2_2)[↓](#5_3_2_4) Launch Template
* Similar to Launch Configuration
* Launch Templates can be used to launch regular instances as well as Spot Fleets.
* Allows to have multiple versions of the same template
* Can source another template to build a hierachy
* With versioning, you can create a subset of the full set of parameters and then reuse it to create other templates or template versions
* AWS recommends to use Launch Templates instead of Launch Configurations to ensure that you can use the latest features of Amazon EC2

<a name="5_3_2_4"></a>
#### [↖](#5_3)[↑](#5_3_2_3)[↓](#5_3_2_5) Termination Policy
* To specify which instances to terminate first during scale in, configure a Termination Policy for the Auto Scaling Group.
* Policies will be applied to the AZ with the most instances
* Can be combined with *instance protection* to prevent termination of specific instances, this starts as soon as the instance is *in service*.
  * Instances can still be terminated manually (unless *termination protection* has been enabled)
  * Unhealthy instance will still be replaced
  * Spot instance interuptions can still occur
	* *Instance protection* can also be applied to an Auto Scaling Group - protecting the whole group: *protect from scale in*
* Can specify *multiple* policies, will be executed in order until an instance has been found
* *Default* policy being last in a list of multiple policies is like `catchAll`, will always find an instance
  * Determine which AZ has most instances and at least one instance that's not protected from scale in
  * [For ASG with multiple instance types and purchase options]: Try to align remaining instances to allocation strategy
  * [For ASG that uses Launch Templates]: Terminate one of the instances with the oldest Launch Template
  * [For ASG that uses Launch Configuration]: Terminate one of the instances with the oldest Launch Configuration
  * If there are multiple instances to choose from, pick the one nearest to the next billing hour
  * Choose one at random

.|.|.
-|-|-
0|**Default**|Designed to help ensure that your instances span Availability Zones evenly for high availability<br/>`3`->`4`->`random`
1|**OldestInstance**|Useful when upgrading to a new EC2 instance type
2|**NewestInstance**|Useful when testing a new launch configuration
3|**OldestLaunchConfiguration**|Useful when updating a group and phasing out instances
5|**OldestLaunchTemplate**|Useful when you're updating a group and phasing out the instances from a previous configuration
4|**ClosestToNextInstanceHour**|Next billing hour - useful to maximize instance us
6|**AllocationStrategy**|Useful when preferred instance types have changed

<a name="5_3_2_5"></a>
#### [↖](#5_3)[↑](#5_3_2_4)[↓](#5_3_2_6) Scaling Processes
You can suspend and then resume one or more of the scaling processes for your Auto Scaling Group. This can be useful for investigating a configuration problem or other issues with your web application and making changes to your application without invoking the scaling processes.

Process|Impact|On Suspension
-|-|-
`Launch`|Add a new EC2 to the group, increasing the capacity|Disrupts other processes as no more scale out
`Terminate`|Removes an EC2 instance from the group, decreasing its capacity.|Disrupts other processes as no more scale in
`HealthCheck`|Checks the health of the instances|.
`ReplaceUnhealthy`|Terminate unhealthy instances and re-create them|.
`AZRebalance`|Balancer the number of EC2 instances across AZ|.
`AlarmNotification`|Accept notification from CloudWatch|Suspends actions normally triggered by alarms
`ScheduledAction`|Performs scheduled actions that you create|.
`AddToLoadBalancer`|Adds instances to the load balancer or target group|Will *not* automatically add instances later

<a name="5_3_2_6"></a>
#### [↖](#5_3)[↑](#5_3_2_5)[↓](#5_4) Deploying with ASGs
* `ALB` - `ASG` - `Launch Template v1` **&** `Launch Template v2`
  * Different application versions in same ASG
* `ALB` - `ASG 1` - `Launch Template v1` **&** `ASG 2` - `Launch Template v2`
* `ALB 1` - `ASG 1` - `Launch Template v1` **&** `ALB 2` - `ASG 2` - `Launch Template v2`
  * Needs DNS (takes time to roll back)
  * Good for testing v2 before cutting over

---

<a name="5_4"></a>
## [↖](#top)[↑](#5_3_2_6)[↓](#5_4_1) ECS (Core Topic)
<!-- toc_start -->
* [Overview](#5_4_1)
  * [Benefits](#5_4_1_1)
* [Components](#5_4_2)
* [Auto Scaling](#5_4_3)
* [Logging](#5_4_4)
* [Load Balancing](#5_4_5)
* [Security](#5_4_6)
<!-- toc_end -->
<a name="5_4_1"></a>
### [↖](#5_4)[↑](#5_4)[↓](#5_4_1_1) Overview
*Amazon Elastic Container Service* (Amazon ECS) is a highly scalable, fast, container management service that makes it easy to run, stop, and manage Docker containers on a cluster. You can host your cluster on a serverless infrastructure that is managed by Amazon ECS by launching your services or tasks using the Fargate launch type. For more control you can host your tasks on a cluster of Amazon Elastic Compute Cloud (Amazon EC2) instances that you manage by using the EC2 launch type.
* On AWS: <a href="https://aws.amazon.com/ecs/" target="_blank">Service</a> - <a href="https://aws.amazon.com/ecs/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/ecs/latest/userguide/" target="_blank">User Guide</a>
* See also: <a href="https://www.awsgeek.com/AWS-re-Invent-2019/CI-CD-with-Fargate-ECS/CI-CD-with-Fargate-ECS.jpg" target="_blank">AWS Geek 2020</a>
* See also: <a href="https://www.awsgeek.com/AWS-re-Invent-2017/Container-Networking-Deep-Dive-with-Amazon-ECS/Container-Networking-Deep-Dive-with-Amazon-ECS.jpg" target="_blank">AWS Geek 2017</a>
* See also: <a href="https://www.awsgeek.com/Amazon-ECS/Amazon-ECS.jpg" target="_blank">AWS Geek 2017</a>

<a name="5_4_1_1"></a>
#### [↖](#5_4)[↑](#5_4_1)[↓](#5_4_2) Benefits
* Containers without servers
* Containerize Everything
* Secure
* Performance at Scale
* AWS Integration

<a name="5_4_2"></a>
### [↖](#5_4)[↑](#5_4_1_1)[↓](#5_4_3) Components
```
[Cluster
  [Services
    [Task Definitions
      [Family]
      [Task role/execution role]
      [Network mode]
      [Container Definitions
        [Name/Image]
        [Memory/Port Mappings]
        [Health Check]
        [Environment]
        [Network Settings]
        [Storage and Logging]
        [Security]
        [Resource Limit]
        [Docker labels]
      ]
    ]
  ]
]
```
* **Cluster**
  * Logical grouping of EC2 instances that you can place tasks on
  * Instances run ECS agent as a Docker container
  * Cluster is an *Auto Scaling Group* with a Launch Configuration using a special ECS AMI
* **Service**
  * Runs and maintains a specified number of tasks simultaneously
  * Created on cluster-level, launch type EC2 or Fargate
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
* **Task Definition**
  * ECS allows to run and maintain a specified number containers in a task definition
    * Group by responsility, e.g. separate task definitions for frontend and backend
  * The task definition is a text file, in JSON format, that describes one or more *containers*, up to a maximum of ten, that form your application
  * Specify various parameters, eg:
    * Container image to use
    * Data volumes
    * Port to be opened & networking
      * **none**: no network connectivity, no port mappings
      * **bridge**: uses Docker’s virtual container-based network
      * **host**: bypass Docker’s network, uses the underlying host network interface
      * **awsvpc**:
          * Every tasks launched on the instance gets its own ENI and a private IP address
          * Simplified networking, enhanced security, security groups, monitoring, VPC flow logs
          * Default mode for Fargate
  * Either for ECS or Fargate
* **Container Definitions**
  * Can mark container as *essential* - if that container fails or stops for any reason, all other containers that are part of the task are stopped
* **Task**
  * A *task* is the instantiation of a *task definition* within a cluster
  * If a task should fail or stop, the ECS scheduler launches another instance of the task definition to replace it and to maintain the desired count of tasks in service
  * Static host port mapping: Only one task per container instance allowed, e.g. mapping host port 80 to container port
  * Dynamic host port mapping: Uses randomized host ports, can work together with ALB to run multiple task instances per container instance
  * Tasks can have individual IAM roles

<a name="5_4_3"></a>
### [↖](#5_4)[↑](#5_4_2)[↓](#5_4_4) Auto Scaling
* Use *Service Auto Scaling* for
  * Target Tracking Scaling Poilicy
  * Step Scaling Policy
  * Sdcheduled Scaling
* For ECS, we also need to scale the cluster
  * This is really tricky, but in essence there's an ASG around the EC2 instances that form the cluster
  * Could use Fargate, obviously
  * Or even Elastic Beanstalk

<a name="5_4_4"></a>
### [↖](#5_4)[↑](#5_4_3)[↓](#5_4_5) Logging
* For tasks, configure logging agent with task definition
  * Typically CloudWatch, also supports Splunk
* For cluster instances, install CloudWatch Agent
* Various ECS-specific CloudWatch metrics available
* Various ECS-specific CloudWatch Events available
* Can enable CloudWatch Container Insights
  * Sends per-container metrics into CloudWatch metrics

<a name="5_4_5"></a>
### [↖](#5_4)[↑](#5_4_4)[↓](#5_4_6) Load Balancing
Application Load Balancer (ALB) has a direct integration feature with ECS called “port mapping”
* This allows you to run multiple instances of the same application on the same EC2 machine
Use Cases:
* Increased resiliency even if running on one EC2 instance
* Maximize utilization of CPU/cores
* Ability to perform rolling upgrades without impacting application uptime

<a name="5_4_6"></a>
### [↖](#5_4)[↑](#5_4_5)[↓](#5_5) Security
* IAM security
  * EC2 Instance Role must have basic ECS permissions
  * ECS Task level should have an IAM Task Role (maximum security)
* Secrets and Configuration injection into parameters, environment variables:
  * Integration with SSM Parameter Store & Secrets Manager

---

<a name="5_5"></a>
## [↖](#top)[↑](#5_4_6)[↓](#5_5_1) Fargate
<!-- toc_start -->
* [Overview](#5_5_1)
<!-- toc_end -->
<a name="5_5_1"></a>
### [↖](#5_5)[↑](#5_5)[↓](#5_6) Overview
AWS Fargate is a serverless compute engine for containers that works with both Amazon Elastic Container Service (ECS) and Amazon Elastic Kubernetes Service (EKS). Fargate makes it easy for you to focus on building your applications. Fargate removes the need to provision and manage servers, lets you specify and pay for resources per application, and improves security through application isolation by design.

Fargate allocates the right amount of compute, eliminating the need to choose instances and scale cluster capacity. You only pay for the resources required to run your containers, so there is no over-provisioning and paying for additional servers. Fargate runs each task or pod in its own kernel providing the tasks and pods their own isolated compute environment. This enables your application to have workload isolation and improved security by design. This is why customers such as Vanguard, Accenture, Foursquare, and Ancestry have chosen to run their mission critical applications on Fargate.
* Don't need to provision cluster
  * Does not need EC2 instance roles to create cluster
* Requires VPC
* On AWS: <a href="https://aws.amazon.com/fargate/" target="_blank">Service</a> - <a href="https://aws.amazon.com/fargate/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/AmazonECS/latest/developerguide/AWS_Fargate.html" target="_blank">User Guide</a

---

<a name="5_6"></a>
## [↖](#top)[↑](#5_5_1)[↓](#5_6_1) Lambda (Core Topic)
<!-- toc_start -->
* [Overview](#5_6_1)
* [Security/IAM](#5_6_2)
* [Managing Functions](#5_6_3)
  * [Versions](#5_6_3_1)
  * [Aliases](#5_6_3_2)
  * [Layers](#5_6_3_3)
  * [Network](#5_6_3_4)
  * [Database](#5_6_3_5)
* [Invoking Functions](#5_6_4)
  * [Synchronous/Asynchronous/Event Source Invocation](#5_6_4_1)
  * [Function Scaling](#5_6_4_2)
  * [Logging, Monitoring and Troubleshooting](#5_6_4_3)
* [Connection Lambdas to a VPC](#5_6_5)
* [Limits and Latencies](#5_6_6)
<!-- toc_end -->
<a name="5_6_1"></a>
### [↖](#5_6)[↑](#5_6)[↓](#5_6_2) Overview
*AWS Lambda* lets you run code without provisioning or managing servers. You pay only for the compute time you consume - there is no charge when your code is not running. With Lambda, you can run code for virtually any type of application or backend service - all with zero administration. Just upload your code and Lambda takes care of everything required to run and scale your code with high availability. You can set up your code to automatically trigger from other AWS services or call it directly from any web or mobile app.
* Features
  * No servers
  * Continuous scaling
    * Cold Start - if no idle container is available to run the Lambda
  * Very cheap
  * Can give more RAM which will proportionaly increase CPU as well
* Supported languages
  * `nodejs`, `Java`, `C#/PowerShell`, `C#/.NET`, `Python`, `Golang`, `Ruby`
  * Any programming language via custom runtime
* Can pass in *environment variables*
  * These can be KMS-encrypted as well (need SDK to decrypt)
* On AWS: <a href="https://aws.amazon.com/lambda/" target="_blank">Service</a> - <a href="https://aws.amazon.com/lambda/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/lambda/latest/userguide/" target="_blank">User Guide</a>
* See also: <a href="https://www.awsgeek.com/AWS-Lambda/AWS-Lambda.jpg" target="_blank">AWS Geek 2020</a>
* See also: <a href="https://www.awsgeek.com/AWS-Modern-App-Series/AWS-Lambda/AWS-Lambda.jpg" target="_blank">AWS Geek 2020</a>

<a name="5_6_2"></a>
### [↖](#5_6)[↑](#5_6_1)[↓](#5_6_3) Security/IAM
* IAM Roles for Lambda to grant access to other AWS services
* Resource-based Policies for Lambda (similar to S3 bucket policies):
  * Allow other accounts to invoke or manage Lambda
  * Allow other services to invoke or manage Lambda

<a name="5_6_3"></a>
### [↖](#5_6)[↑](#5_6_2)[↓](#5_6_3_1) Managing Functions
`triggers` -> `function & layers` -> `destinations`

<a name="5_6_3_1"></a>
#### [↖](#5_6)[↑](#5_6_3)[↓](#5_6_3_2) Versions
* If you work on a Lambda function, you work on `$LATEST`
* The system creates a new version of your Lambda function each time that you *publish* the function. The new version is a copy of the *unpublished* version of the function.
* Version is code *and* configuration
* Versions are immutable, you can change the function code and settings (including environment variables) only on the unpublished version of a function.
* Each version gets its own ARN

<a name="5_6_3_2"></a>
#### [↖](#5_6)[↑](#5_6_3_1)[↓](#5_6_3_3) Aliases
* You can create one or more aliases for your AWS Lambda function. A Lambda alias is like a *pointer* to a specific Lambda function *version*.
* Aliases are mutable
* Users can access the function version using the alias ARN.
* Can create e.g. `dev`, `test` and `prod`.
  * Aliases can point to multiple versions with a *weight* - for canary-style deployments
* Can use *alias routing*, where weights are assigned to up to two published Lambda function versions that the alias points to
  * This allows to canary/blue-green deploy
* Aliases integrate well with **API Gateway**, where gateway *stages* point to Lambda aliases
* **CodeDeploy** allow to automate the traffic shift between aliases
  * Lambda deploys a new version under an alias, and traffic is shifted between old and new version
    * `LambdaCanary10Percent5Minutes/10/15/30`
    * `LambdaLinear10PercentEvery1Minute/2/3/10`
    * `LambdaAllAtOnce`
  * Pre/post traffic hooks allow to invoke funcitons for health checking etc

<a name="5_6_3_3"></a>
#### [↖](#5_6)[↑](#5_6_3_2)[↓](#5_6_3_4) Layers
* You can configure your Lambda function to pull in additional code and content in the form of layers.
* A layer is a ZIP archive that contains libraries, a custom runtime, or other dependencies.
* With layers, you can use libraries in your function without needing to include them in your deployment package.

<a name="5_6_3_4"></a>
#### [↖](#5_6)[↑](#5_6_3_3)[↓](#5_6_3_5) Network
* You can configure a function to connect to private subnets in a VPC in your account.
* Use VPC to create a private network for resources such as databases, cache instances, or internal services.
* Connect your function to the VPC to access private resources during execution.
* Provisioning process for Lambda takes longer

<a name="5_6_3_5"></a>
#### [↖](#5_6)[↑](#5_6_3_4)[↓](#5_6_4) Database
* You can use the Lambda console to create an RDS database proxy for your function.
* A database proxy manages a pool of database connections and relays queries from a function.
* This enables a function to reach high concurrency levels without exhausting database connections.

<a name="5_6_4"></a>
### [↖](#5_6)[↑](#5_6_3_5)[↓](#5_6_4_1) Invoking Functions

<a name="5_6_4_1"></a>
#### [↖](#5_6)[↑](#5_6_4)[↓](#5_6_4_2) Synchronous/Asynchronous/Event Source Invocation
* When you invoke a function **synchronously**, Lambda runs the function and waits for a response.
  * -> API Gateway, ALB, Cognito, Lex, Alexa, CloudFront (Lambda@Edge), Kinesis Data Firehose
* When you invoke a function **asynchronously**, Lambda sends the event to a queue. A separate
process reads events from the queue and runs your function.
  * Lambda manages the function's asynchronous invocation queue and attempts to retry failed events automatically. If the function returns an error, Lambda attempts to run it two more times
  * For retries, Lambda needs to be idempotent
  * You can also configure Lambda to send an invocation record to another service.
    * Lambda supports the following **destinations** for asynchronous invocation recordings: SQS, SNS, AWS Lambda, EventBridge
    * The invocation record contains details about the request and response in JSON format. You can configure separate destinations for events that are processed successfully, and events that fail all processing attempts. Alternatively, you can configure an SQS queue or SNS topic as a dead letter queue for discarded events. For dead-letter queues, Lambda only sends the content of the event, without details about the response.
  * When all attempts to process an asynchronous invocation fail, Lambda can send the event to an Amazon SQS queue or an Amazon SNS topic (DLQ).
    * Less information than *destinations*, not recommended any more by AWS
  * -> S3, SNS, SES, CloudFormation, CloudWatch Logs & Events, CodeCommit, Config
* An **event source mapping** is an AWS Lambda resource that reads from an event source and invokes a Lambda function.
  * -> Kinesis Data Streams, DynamoDB Streams, SQS, SQS FIFO
  * Common denominator: records need to be polled from the source
  * All records are respect ordering properties except for SQS standard
  * If your function returns an error, the entire batch is reprocessed until success
    * Kinesis, DynamoDB Stream: stop shard processing
    * SQS FIFO: stop, unless a SQS DLQ has been defined
    * Need to make sure your Lambda function is idempotent
  * Supports SQS and SNS as *destination* for  discarded event batches

<a name="5_6_4_2"></a>
#### [↖](#5_6)[↑](#5_6_4_1)[↓](#5_6_4_3) Function Scaling
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
* Default Burst concurrency limits
    * `3000` – US West (Oregon), US East (N. Virginia), Europe (Ireland)
    * `1000` – Asia Pacific (Tokyo), Europe (Frankfurt)
    * `500` – Other Regions

<a name="5_6_4_3"></a>
#### [↖](#5_6)[↑](#5_6_4_2)[↓](#5_6_5) Logging, Monitoring and Troubleshooting
* **CloudWatch**
  * AWS Lambda execution logs are stored in AWS CloudWatch Logs
  * AWS Lambda metrics are displayed in AWS CloudWatch Metrics (successful invocations, error rates, latency, timeouts, etc...)
  * Make sure your AWS Lambda function has an execution role with an IAM policy that authorizes writes to CloudWatch Logs
* **X-Ray**
  * It’s possible to trace Lambda with X-Ray
  * Enable in Lambda configuration (runs the X-Ray daemon for you)
  * Use AWS SDK in Code
  * Ensure Lambda Function has correct IAM Execution Role
* AWS Lambda automatically monitors Lambda functions on your behalf and reports metrics through Amazon CloudWatch. To help you monitor your code as it executes, Lambda automatically tracks the
  *number of requests*, the *execution duration per request*, and the *number of requests that result in an error*.
* It also publishes the associated CloudWatch metrics.
* Need *custom metric* for memory usage

<a name="5_6_5"></a>
### [↖](#5_6)[↑](#5_6_4_3)[↓](#5_6_6) Connection Lambdas to a VPC
You can configure a Lambda function to connect to private subnets in a VPC. Use VPC to create a private network for resources such as databases, cache instances, or internal services. Connect your function to the VPC to access private resources while the function is running.

* When you connect a function to a VPC, Lambda creates an elastic network interface for each subnet in your function's VPC configuration.
* Lambda attaches to subnets and security groups
* Internet access goes through VPC

<a name="5_6_6"></a>
### [↖](#5_6)[↑](#5_6_5)[↓](#5_7) Limits and Latencies

.|Limit
-|-
RAM|128 MB to 10GB
CPU|Linked to RAM (cannot be set manually)<br/>2 vCPU are allocated after 1.5G of RAM
Timeout|Up to 15 minutes
/tmp storage|512 MB (can’t process BIG files)
Deployment package limit|250 MB including layers
Concurrency execution|1000 – soft limit that can be increased

.|Latency
-|-
Cold Lambda Invocation|~100ms<br/>New feature of “provisioned concurrency” (Dec 2019) to reduce # of cold starts
Warm Lambda Invocation|~ms
API Gateway invocation|100 ms
CloudFront invocation|100 ms

* If you chain with other services (API Gateway, CloudFront, ALB, Lambda, SQS, Step Functions...), add their latencies as well
* X-Ray can help visualize the end-to-end latency

---

<a name="5_7"></a>
## [↖](#top)[↑](#5_6_6)[↓](#5_7_1) Elastic Load Balancing (Core Topic)
<!-- toc_start -->
* [Overview](#5_7_1)
* [ELB (Classic Load Balancer)](#5_7_2)
* [ALB](#5_7_3)
  * [Overview](#5_7_3_1)
  * [Routing](#5_7_3_2)
  * [Target Groups](#5_7_3_3)
  * [SSL Certificates](#5_7_3_4)
* [NLB](#5_7_4)
  * [Overview](#5_7_4_1)
  * [Target Groups](#5_7_4_2)
  * [Proxy protocol](#5_7_4_3)
* [Cross-Zone Load Balancing](#5_7_5)
* [Load Balancer Stickiness](#5_7_6)
<!-- toc_end -->

<a name="5_7_1"></a>
### [↖](#5_7)[↑](#5_7)[↓](#5_7_2) Overview
Elastic Load Balancing automatically distributes incoming application traffic across multiple targets, such as Amazon EC2 instances, containers, IP addresses, Lambda functions, and virtual appliances. It can handle the varying load of your application traffic in a single Availability Zone or across multiple Availability Zones. Elastic Load Balancing offers four types of load balancers that all feature the high availability, automatic scaling, and robust security necessary to make your applications fault tolerant.
* <a href="https://aws.amazon.com/elasticloadbalancing/" target="_blank">Service</a> - <a href="https://aws.amazon.com/elasticloadbalancing/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/elasticloadbalancing/" target="_blank">User Guide</a>

.|**ALB** (2016)|**NLB** (2017)|**ELB** (2009)
-|-|-|-
.|Active Load Balancer|Network Load Balancer|Classic Load Balancer
Layer|7 (application layer)|4 (transport layer)|EC2-classic network (deprecated)
Protocoll|HTTP, HTTPS|TCP, TLS (secure TCP), UDP|TCP, SSL, HTTP, HTTPS

* `x-forwarder-for` header has IP address of end user
* ELBs don't have ipv4 address, need to be resolved by DNS name
* ALBs now supports host-based and path-based routing
  * `api.example.com/production`, `mobile.example.com/test`

<a name="5_7_2"></a>
### [↖](#5_7)[↑](#5_7_1)[↓](#5_7_3) ELB (Classic Load Balancer)
* `Client` -> [listener] -> `CLB` -> [internal] -> EC2

Listener|Internal
-|-
HTTP (L7)|HTTP<br/>HTTPS (must install certificate on EC2)
HTTPS (L7)<br/>SSL termination<br/>Must install certificate on CLB|HTTP<br/>HTTPS (must install certificate on EC2)
TCP (L4)|TCP<br/>SSL (must install certificate on EC2)
SSL secure TCP (L4)<br/>Must install certificate on CLB TCP|SSL<br/>(must install certificate on EC2)

* Before you start using Elastic Load Balancing, you must configure one or more *listeners* for your Classic Load Balancer. A listener is a process that checks for connection requests. It is configured with a protocol and a port for front-end (client to load balancer) connections, and a protocol and a port for back-end (load balancer to back-end instance) connections.
* When you use TCP (layer 4) for both front-end and back-end connections, your load balancer forwards the request to the back-end instances without modifying the headers. After your load balancer receives the request, it attempts to open a TCP connection to the back-end instance on the port specified in the listener configuration.
  * Because load balancers intercept traffic between clients and your back-end instances, the access logs for your back-end instance contain the IP address of the load balancer instead of the originating client.
  * You can enable proxy protocol, which adds a header with the connection information of the client, such as the source IP address, destination IP address, and port numbers
* When you use HTTP (layer 7) for both front-end and back-end connections, your load balancer parses the headers in the request and terminates the connection before sending the request to the back-end instances.
  * The HTTP requests and HTTP responses use header fields to send information about HTTP messages. Elastic Load Balancing supports X-Forwarded-For headers.
  * Because load balancers intercept traffic between clients and servers, your server access logs contain only the IP address of the load balancer. To see the IP address of the client, use the X-Forwarded-For request header.
* Health Checks can be HTTP (L7) or TCP (L4) based
* Supports only one SSL certificate
  * The SSL certificate can have many SAN (Subject Alternate Name), but the SSL certificate must be changed anytime a SAN is added/edited/removed
  * Better to use ALB with SNI (Server Name Indication) if possible
  * Can use multiple CLB if you want distinct SSL certificates
* TCP => TCP passes all the traffic to the EC2 instance
  * Only way to use 2-way SSL authentication (*client-authenticated TLS handshake*)

<a name="5_7_3"></a>
### [↖](#5_7)[↑](#5_7_2)[↓](#5_7_3_1) ALB
<a name="5_7_3_1"></a>
#### [↖](#5_7)[↑](#5_7_3)[↓](#5_7_3_2) Overview
An Application Load Balancer functions at the application layer, the seventh layer of the Open Systems Interconnection (OSI) model. After the load balancer receives a request, it evaluates the listener rules in priority order to determine which rule to apply, and then selects a target from the target group for the rule action. You can configure listener rules to route requests to different target groups based on the content of the application traffic. Routing is performed independently for each target group, even when a target is registered with multiple target groups. You can configure the routing algorithm used at the target group level. The default routing algorithm is round robin; alternatively, you can specify the least outstanding requests routing algorithm.
* Application load balancers is Layer 7 (HTTP)
* Load balancing to multiple HTTP applications *across machines*
  * **Target group** represents an application
* Load balancing to multiple applications *on the same machine*
  * Example: containers
* Support for HTTP/2 and WebSocket
* Support redirects (from HTTP to HTTPS for example)
* ALB are a great fit for micro services & container-based application (example: Docker & Amazon ECS)
* Has a port mapping feature to redirect to a dynamic port in ECS
* In comparison, we would need multiple Classic Load Balancer per application
* <a href="https://docs.aws.amazon.com/elasticloadbalancing/latest/application/introduction.html" target="_blank">On AWS</a>

<a name="5_7_3_2"></a>
#### [↖](#5_7)[↑](#5_7_3_1)[↓](#5_7_3_3) Routing
* Routing tables to different target groups:
  * Routing based on path in URL (example.com/users & example.com/posts)
  * Routing based on hostname in URL (one.example.com & other.example.com)
  * Routing based on Query String, Headers (example.com/users?id=123&order=false)

<a name="5_7_3_3"></a>
#### [↖](#5_7)[↑](#5_7_3_2)[↓](#5_7_3_4) Target Groups
* EC2 instances (can be managed by an ASG) – HTTP
* ECS tasks (managed by ECS itself) – HTTP
* Lambda functions – HTTP request is translated into a JSON event
* IP Addresses – must be private IPs (example: instances in peered VPC, on-premise)
* ALB can route to multiple target groups
* Health checks are at the target group level

<a name="5_7_3_4"></a>
#### [↖](#5_7)[↑](#5_7_3_3)[↓](#5_7_4) SSL Certificates
* Supports multiple listeners
* Supports SNI - Server Name Indication

<a name="5_7_4"></a>
### [↖](#5_7)[↑](#5_7_3_4)[↓](#5_7_4_1) NLB
<a name="5_7_4_1"></a>
#### [↖](#5_7)[↑](#5_7_4)[↓](#5_7_4_2) Overview
A Network Load Balancer functions at the fourth layer of the Open Systems Interconnection (OSI) model. It can handle millions of requests per second. After the load balancer receives a connection request, it selects a target from the target group for the default rule. It attempts to open a TCP connection to the selected target on the port specified in the listener configuration. When you enable an Availability Zone for the load balancer, Elastic Load Balancing creates a load balancer node in the Availability Zone. By default, each load balancer node distributes traffic across the registered targets in its Availability Zone only. If you enable cross-zone load balancing, each load balancer node distributes traffic across the registered targets in all enabled Availability Zones.
* Network load balancers (Layer 4) allow to do:
  * Forward TCP and/or UDP traffic to your instances
  * Handle millions of request per seconds
  * NLB has one static IP per AZ, and supports assigning Elastic IP (helpful for whitelisting specific IP)
  * Less latency ~100 ms (vs 400 ms for ALB)
  * Support for TLS
  * Support for WebSockets
* Network Load Balancers are mostly used:
  * for extreme performance, TCP or UDP traffic
  * with AWS Private Link to expose a service internally
* <a href="https://docs.aws.amazon.com/elasticloadbalancing/latest/network/introduction.html" target="_blank">On AWS</a>

<a name="5_7_4_2"></a>
#### [↖](#5_7)[↑](#5_7_4_1)[↓](#5_7_4_3) Target Groups
Each target group is used to route requests to one or more registered targets. When you create a listener, you specify a target group for its default action. Traffic is forwarded to the target group specified in the listener rule. You can create different target groups for different types of requests. For example, create one target group for general requests and other target groups for requests to the microservices for your application.

You define health check settings for your load balancer on a per target group basis. Each target group uses the default health check settings, unless you override them when you create the target group or modify them later on. After you specify a target group in a rule for a listener, the load balancer continually monitors the health of all targets registered with the target group that are in an Availability Zone enabled for the load balancer. The load balancer routes requests to the registered targets that are healthy.
* EC2 instances (can be managed by an ASG) – TCP
* ECS tasks (managed by ECS itself) – TCP
* IP addresses – Private IP only, even outside your VPC

<a name="5_7_4_3"></a>
#### [↖](#5_7)[↑](#5_7_4_2)[↓](#5_7_5) Proxy protocol
Network Load Balancers use proxy protocol version 2 to send additional connection information such as the source and destination. Proxy protocol version 2 provides a binary encoding of the proxy protocol header. The load balancer prepends a proxy protocol header to the TCP data. It does not discard or overwrite any existing data, including any proxy protocol headers sent by the client or any other proxies, load balancers, or servers in the network path. Therefore, it is possible to receive more than one proxy protocol header. Also, if there is another network path to your targets outside of your Network Load Balancer, the first proxy protocol header might not be the one from your Network Load Balancer.
* Send additional connection information such as the source and destination
* The load balancer prepends a proxy protocol header to the TCP data
* Helpful when you have the “IP addresses” target group type
  * You can retrieve the source IP address of the originating client

<a name="5_7_5"></a>
### [↖](#5_7)[↑](#5_7_4_3)[↓](#5_7_6) Cross-Zone Load Balancing
* With Cross Zone Load Balancing: each load balancer instance distributes evenly across all registered instances in all AZ
* Otherwise, each load balancer node distributes requests evenly across the registered instances in its Availability Zone only.

Type|Default|Costs
-|-|-
Classic|Disabled|No charges for inter-AZ data
ALB|Always on|No charges for inter-AZ data
NLB|Disabled|Charges for inter-AZ data

<a name="5_7_6"></a>
### [↖](#5_7)[↑](#5_7_5)[↓](#5_8) Load Balancer Stickiness
* It is possible to implement stickiness so that the same client is always redirected to the same instance behind a load balancer
* This works for Classic Load Balancers & Application Load Balancers
* The “cookie” used for stickiness has an expiration date you control
* Use case: make sure the user doesn’t lose his session data
* Enabling stickiness may bring imbalance to the load over the backend EC2 instances
* Alternative is to cache session data in ElastiCache, DynamoDB, etc

---

<a name="5_8"></a>
## [↖](#top)[↑](#5_7_6)[↓](#5_8_1) API Gateway
<!-- toc_start -->
* [Overview](#5_8_1)
  * [Limits](#5_8_1_1)
* [Concepts](#5_8_2)
  * [Endpoint](#5_8_2_1)
  * [Stage](#5_8_2_2)
  * [Deployment](#5_8_2_3)
  * [Canary Deployments](#5_8_2_4)
  * [Integration](#5_8_2_5)
  * [Mapping Template](#5_8_2_6)
  * [Model](#5_8_2_7)
  * [Throttling](#5_8_2_8)
  * [Caching API responses](#5_8_2_9)
  * [Errors](#5_8_2_10)
* [Security & Authentication](#5_8_3)
  * [Security](#5_8_3_1)
  * [Authentication](#5_8_3_2)
* [Logging, Monitoring, Tracing](#5_8_4)
<!-- toc_end -->

<a name="5_8_1"></a>
### [↖](#5_8)[↑](#5_8)[↓](#5_8_1_1) Overview
*Amazon API Gateway* is a fully managed service that makes it easy for developers to create, publish, maintain, monitor, and secure APIs at any scale. With a few clicks in the AWS Management Console, you can create *REST* and *WebSocket* APIs that act as a “front door” for applications to access data, business logic, or functionality from your backend services, such as workloads running on Amazon Elastic Compute Cloud (Amazon EC2), code running on AWS Lambda, any web application, or real-time communication applications.
* **Benefits**
  * **RESTful** (stateless) or **Websocket** (stateful) APIs
  * Powerful, flexible **authentication** mechanisms, such as AWS IAM policies, Lambda authorizer functions, and Amazon Cognito user pools.
  * API **versioning**
  * Traffic management (API Keys, throtteling)
  * **Developer portal** for publishing your APIs.
  * **Canary release deployments** for safely rolling out changes.
  * *CloudTrail* logging and monitoring of API usage and API changes.
  * *CloudWatch* access logging and execution logging, including the ability to set alarms.
  * Ability to use *AWS CloudFormation* templates to enable API creation
  * Support for custom domain names.
  * Integration with *AWS WAF* for protecting your APIs against common web exploits.
  * Integration with *AWS X-Ray* for understanding and triaging performance latencies.
* On AWS: <a href="https://aws.amazon.com/api-gateway/" target="_blank">Service</a> - <a href="https://aws.amazon.com/api-gateway/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/apigateway/latest/developerguide/welcome.html" target="_blank">User Guide</a>
* See also: <a href="https://www.awsgeek.com/AWS-Modern-App-Series/Amazon-API-Gateway/Amazon-API-Gateway.jpg" target="_blank">AWS Geek 2020</a>
* See also: <a href="https://www.awsgeek.com/Amazon-API-Gateway/Amazon-API-Gateway.jpg" target="_blank">AWS Geek 2018</a>

<a name="5_8_1_1"></a>
#### [↖](#5_8)[↑](#5_8_1)[↓](#5_8_2) Limits
.|.
-|-
Timeout|29 sec
Max payload size|10 MB

<a name="5_8_2"></a>
### [↖](#5_8)[↑](#5_8_1_1)[↓](#5_8_2_1) Concepts

<a name="5_8_2_1"></a>
#### [↖](#5_8)[↑](#5_8_2)[↓](#5_8_2_2) Endpoint
A hostname for an API in API Gateway that is deployed to a specific region. The hostname is of the form `{api-id}.execute-api.{region}.amazonaws.com`.

The following types of API endpoints are supported:
* *Regional* - deployed to the specified region and intended to serve clients in the same AWS region.
  * Can be combined with CloudFront (caching, distributions, ...)
* *Edge Optimized* - deployed to the specified region while using a *CloudFront distribution* to facilitate client access typically from across AWS regions
  * API Gateway still lives in one region
* *Private* - exposed through interface VPC endpoints
  * Create resource policy to define access

<a name="5_8_2_2"></a>
#### [↖](#5_8)[↑](#5_8_2_1)[↓](#5_8_2_3) Stage
A logical reference to a lifecycle state of your REST or WebSocket API (for example, `dev`, `prod`, `beta`, `v2`). API changes are deployed to stages.
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

<a name="5_8_2_3"></a>
#### [↖](#5_8)[↑](#5_8_2_2)[↓](#5_8_2_4) Deployment
After creating your API, you *must* deploy it to make it callable by your users. To deploy an API, you create an *API deployment* and associate it with a *stage*. Each stage is a snapshot of the API and is made available for client apps to call.

<a name="5_8_2_4"></a>
#### [↖](#5_8)[↑](#5_8_2_3)[↓](#5_8_2_5) Canary Deployments
* Use stage variables for canary deployments
  * Integrate Lambda via alias: `GetStartedLambdaProxyIntegration:${stageVariables.lambdaAlias}`
  * Overwrite stage variable in canary deployment
* Could also use Lambda's canary functionality with weighted aliases

<a name="5_8_2_5"></a>
#### [↖](#5_8)[↑](#5_8_2_4)[↓](#5_8_2_6) Integration
* HTTP
  * Expose HTTP endpoints in the backend
  * Example: Internal HTTP API on-premises, Application Load Balancer...
  * Why? Add rate limiting, caching, user authentications, API keys, etc...
* *Lambda Proxy* - request is passed through straight to a Lambda
  * Proxy Lambda deals with complete `http` request
* *Lambda Non-Proxy/Custom*
  * Allows integration of *mapping template*
  * Can transform request as well as response
  * Allows to evolve the API while keeping Lambda function static
* *Any service*
  * **All** AWS services support dedicated APIs to expose their features. However, the application protocols or programming interfaces are likely to differ from service to service. An API Gateway API with the AWS integration has the advantage of providing a consistent application protocol for your client to access different AWS services.

<a name="5_8_2_6"></a>
#### [↖](#5_8)[↑](#5_8_2_5)[↓](#5_8_2_7) Mapping Template
* A scripts in Velocity Template Language (VTL) that transforms a request body from the frontend
data format to the backend data format.
* Cannot add default values to fields, only add new static fields

<a name="5_8_2_7"></a>
#### [↖](#5_8)[↑](#5_8_2_6)[↓](#5_8_2_8) Model
A data schema specifying the data structure of a request or response payload.

<a name="5_8_2_8"></a>
#### [↖](#5_8)[↑](#5_8_2_7)[↓](#5_8_2_9) Throttling
* Account-wide limit of 10,000 requests per second.
  * Applies at service/account level
* Can create *usage plan*:
  * *Rate*, *burst*, *quota*
  * Can assoicate with stage/method/API key (to limit certain clients)

<a name="5_8_2_9"></a>
#### [↖](#5_8)[↑](#5_8_2_8)[↓](#5_8_2_10) Caching API responses
* Caching reduces the number of calls made to the backend
* Default TTL (time to live) is 300 seconds (min: 0s, max: 3600s)
* Caches are defined per stage
* Possible to override cache settings per method
* Clients can invalidate the cache with header: `Cache-Control: max-age=0` (with proper IAM authorization)
* Able to flush the entire cache (invalidate it) immediately
* Cache encryption option
* Cache capacity between 0.5GB to 237GB

<a name="5_8_2_10"></a>
#### [↖](#5_8)[↑](#5_8_2_9)[↓](#5_8_3) Errors
Client-side|Server-side|.
-|-|-
400|.|Bad Request
403|.|Access Denied, WAF filtered
429|.|Quota exceeded, Throttle
|.|502|Bad Gateway Exception<br/>usually for an incompatible output returned from a Lambda proxy integration backend and occasionally for out-of-order invocations due to heavy loads.
|.|503|Service Unavailable Exception
|.|504|Integration Failure<br/>Eg Endpoint Request Timed-out Exception API Gateway requests time out after 29 second maximum

<a name="5_8_3"></a>
### [↖](#5_8)[↑](#5_8_2_10)[↓](#5_8_3_1) Security & Authentication
<a name="5_8_3_1"></a>
#### [↖](#5_8)[↑](#5_8_3)[↓](#5_8_3_2) Security
* Load SSL certificates and use Route53 to define a CNAME
* Resource Policy (~S3 Bucket Policy):
  * Control who can access the API
  * Users from AWS accounts, IP or CIDR blocks, VPC or VPC Endpoints
* IAM Execution Roles for API Gateway at the API level
  * To invoke a Lambda Function, an AWS service...
* CORS (Cross-origin resource sharing):
  * Browser based security
  * Control which domains can call your API

<a name="5_8_3_2"></a>
#### [↖](#5_8)[↑](#5_8_3_1)[↓](#5_8_4) Authentication
* IAM based access
  * Good for providing access within your own infrastructure
  * Pass IAM credentials in headers through Sig V4
* Lambda Authorizer (formerly Custom Authorizer)
  * Use Lambda to verify a custom OAuth/SAML/3rd party authentication
* Cognito User Pools
  * Client authenticates with Cognito
  * Client passes the token to API Gateway
  * API Gateway knows out-of-the-box how to verify the token

<a name="5_8_4"></a>
### [↖](#5_8)[↑](#5_8_3_2)[↓](#5_9) Logging, Monitoring, Tracing
* CloudWatch Logs
  * Enable CloudWatch logging at the Stage level (with Log Level – ERROR, INFO)
  * Can log full requests/responses data
  * Can send API Gateway Access Logs (customizable)
  * Can send logs directly into Kinesis Data Firehose (as an alternative to CloudWatch Logs)
* CloudWatch Metrics
  * Metrics are by stage, possibility to enable detailed metrics
  * IntegrationLatency, Latency, CacheHitCount, CacheMissCount
* X-Ray
  * Enable tracing to get extra information about requests in API Gateway
  * X-Ray API Gateway + AWS Lambda gives you the full picture

---

<a name="5_9"></a>
## [↖](#top)[↑](#5_8_4)[↓](#5_9_1) Route 53 (Core Topic)
<!-- toc_start -->
* [Overview](#5_9_1)
  * [Terminology](#5_9_1_1)
* [ How it works](#5_9_2)
  * [Basic Flow](#5_9_2_1)
  * [Resolving DNS queries between VPCs and your network](#5_9_2_2)
  * [Zone File & Records](#5_9_2_3)
  * [Route 53 Routing Policies](#5_9_2_4)
* [Health Checks with Route 53](#5_9_3)
  * [Trigger automated DNS failover](#5_9_3_1)
  * [Setup](#5_9_3_2)
  * [Private Hosted Zones](#5_9_3_3)
* [Sharing a Private Zone across multiple VPCs](#5_9_4)
<!-- toc_end -->
<a name="5_9_1"></a>
### [↖](#5_9)[↑](#5_9)[↓](#5_9_1_1) Overview
Amazon Route 53 is a highly available and scalable Domain Name System (DNS) web service. You can use Route 53 to perform three main functions in any combination: domain registration, DNS routing, and health checking. If you choose to use Route 53 for all three functions, perform the steps in this order:
* Register domain names
  * Your website needs a name, such as example.com. Route 53 lets you register a name for your website or web application, known as a domain name.
* Route internet traffic to the resources for your domain
  * When a user opens a web browser and enters your domain name (example.com) or subdomain name acme.example.com) in the address bar, Route 53 helps connect the browser with your website or web application
* Check the health of your resources
  * Route 53 sends automated requests over the internet to a resource, such as a web server, to verify that it's reachable, available, and functional. You also can choose to receive notifications when a resource becomes unavailable and choose to route internet traffic away from unhealthy resources.
* Private DNS:
  * Can use Route 53 for internal private DNS
  * Must enable the VPC settings `enableDnsHostNames` and `enableDnsSupport`
* DNSSEC (protect against Man In the Middle attack):
  * Amazon Route 53 supports DNSSEC for domain registration
  * ~~Route 53 does not support DNSSEC for DNS service~~
  * ~~To configure DNSSEC for a Route 53 domain, use another DNS provider or custom DNS server on Amazon EC2 (Bind, dnsmasq, KnotDNS, PowerDNS)~~
* 3rd party registrar:
  * You can buy the domain out of AWS and use Route 53 as your DNS provider
    * Update the NS records on the 3rd party registrar
* On AWS: <a href="https://aws.amazon.com/route53/" target="_blank">Service</a> - <a href="https://aws.amazon.com/route53/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/Welcome.html" target="_blank">User Guide</a>

<a name="5_9_1_1"></a>
#### [↖](#5_9)[↑](#5_9_1)[↓](#5_9_2) Terminology
* **Hosts** - Computers or services accessible within a domain
* **Name Server** - Translates domain names into IP addresses
* **Zone File** - Text file that contains mappings between domain names and IP addresses
* **Records** - Entries in zone file, mappings beween resources and names
* A **hosted zone** is a container for records, and records contain information about how you want to route traffic for a specific domain, such as example.com, and its subdomains (acme.example.com, zenith.example.com). A hosted zone and the corresponding domain have the same name. There are two types of hosted zones:
	* **Public hosted zones** contain records that specify how you want to route traffic on the internet.
	* A **private hosted zone** is a container that holds information about how you want Amazon Route 53 to respond to DNS queries for a domain and its subdomains within one or more VPCs that you create with the Amazon VPC service. Your VPC has attributes that determine whether your EC2 instance receives public DNS hostnames, and whether DNS resolution through the Amazon DNS server is supported.

<a name="5_9_2"></a>
### [↖](#5_9)[↑](#5_9_1_1)[↓](#5_9_2_1)  How it works

<a name="5_9_2_1"></a>
#### [↖](#5_9)[↑](#5_9_2)[↓](#5_9_2_2) Basic Flow
* `Root Server` -> `TLD Server` -> `Domain-Level Name Server` -> `Zone File`
* Client requests Route 53, receives A record (host name to ip4) and TTL, client requests IP address from A record

<a name="5_9_2_2"></a>
#### [↖](#5_9)[↑](#5_9_2_1)[↓](#5_9_2_3) Resolving DNS queries between VPCs and your network
When you create a VPC using Amazon VPC, **Route 53 Resolver** automatically answers DNS queries for local VPC domain names for EC2 instances (ec2-192-0-2-44.compute-1.amazonaws.com) and records in private hosted zones (acme.example.com). For all other domain names, Resolver performs recursive lookups against public name servers.

You also can integrate DNS resolution between Resolver and DNS resolvers on your network by configuring forwarding rules. Your network can include any network that is reachable from your VPC, such as the following:
* The VPC itself
* Another peered VPC
* An on-premises network that is connected to AWS with AWS Direct Connect, a VPN, or a network address translation (NAT) gateway
Before you start to forward queries, you create Resolver inbound and/or outbound endpoints in the connected VPC. These endpoints provide a path for inbound or outbound queries:
* **Inbound endpoint**: DNS resolvers on your network can forward DNS queries to Route 53 Resolver via this endpoint
* **Outbound endpoint**: Resolver conditionally forwards queries to resolvers on your network via this endpoint

<a name="5_9_2_3"></a>
#### [↖](#5_9)[↑](#5_9_2_2)[↓](#5_9_2_4) Zone File & Records
Zone file stores records. Various records exists:

Type|Definition|Example
-|-|-
**A**|Map host name to ip4 address|`px01.vc.example.com.  198.51.100.40`
**AAAA**|Map host name to ip6 address|`px01.vc.example.com.  2a00:1450:4014:80c:0:0:0:2004`
**CNAME**|Defines alias for host name<br/>(maps one domain name to another)|`www.dnsimple.com. dnsimple.com.`
**SOA**|State of Authority - Mandatory first entry, defines various things,<br/>eg name servers & admin contact|`ns1.dnsimple.com admin.dnsimple.com 2013022001 86400 7200 604800 300`
**MX**|Defines mail exchange|`example.com.  1800  MX  mail1.example.com.  10`
**PTR**|Maps ip4 address to host name (inverse to A record)|`10.27/1.168.192.in-addr.arpa.  1800  PTR mail.example.com.`
**SVR**|Points one domain to another domain name using a specific destination port|`_sip._tcp.example.com. 86400 IN SRV 0 5 5060 sipserver.example.com.`

Route 53 specific:
* **Alias** record
	* Amazon Route 53 alias records provide a Route 53–specific extension to DNS functionality. Alias records let you route traffic to selected AWS resources, such as CloudFront distributions and Amazon S3 bucket. They also let you route traffic from one record in a hosted zone to another record.
	* Unlike a CNAME record, you can create an alias record at the top node of a DNS namespace, also known as the *zone apex*. For example, if you register the DNS name example.com, the zone apex is example.com. You can't create a CNAME record for example.com, but you can create an alias record for example.com that routes traffic to www.example.com
	* Preferred choice over CNAME
	* To route domain traffic to an ELB load balancer, use Amazon Route 53 to create an alias record that points to your load balancer. An alias record is a Route 53 extension to DNS. It's similar to a CNAME record, but you can create an alias record both for the root domain, such as example.com, and for subdomains, such as www.example.com. (You can create CNAME records only for subdomains).
		* For EC2 instances, always use a Type A Record without an Alias.
		* For ELB, Cloudfront and S3, always use a Type A Record with an Alias
		* For RDS, always use the CNAME Record with no Alias.

<a name="5_9_2_4"></a>
#### [↖](#5_9)[↑](#5_9_2_3)[↓](#5_9_3) Route 53 Routing Policies
  * **Simple**
    * Default policy, typically used if only a single resource performs functionality
    * If multiple values are returned, one is picked at random *by the client*
    * Can't attach health checks
  * **Weighted**
    * Control distribution of traffic with DNS entries
      * This can be based on a certain percentage
      * Set *routing policy* to weighted (instead of failover)
      * Can attach health checks
    * Helpful to split traffic between regions
  * **Latency**
    * Control distribution of traffic based on latency.
    * Has a failover capability if you enable health checks
  * **Failover**
    * Setup *primary* route with mandatory health check
    * Setup *secondary* route with optional health check
      * Good for disaster recovery
    * Can set up *health checks* for endpoints or domains from within *Route 53*
      * Route 53 has health checkers in locations around the world. When you create a health check that monitors an endpoint, health checkers start to send requests to the endpoint that you specify to determine whether the endpoint is healthy.
      * `evaluate target health`
    * DNS entries are then being associated with health checks and can be configured to failover as well (1 primary and n secondary recordsets)
  * **Geo location**
    * Geolocation routing lets you choose the resources that serve your traffic based on the geographic location of your users, meaning the location that DNS queries originate from. For example, you might want all queries from Europe to be routed to an ELB load balancer in the Frankfurt region.
    * Should create a “default” policy (in case there’s no match on location)
  * **Geo proximity Routing (Traffic Flow Only)**
    * Geoproximity routing lets Amazon Route 53 route traffic to your resources based on the geographic location of your users and your resources. You can also optionally choose to route more traffic or less to a given resource by specifying a value, known as a bias. A bias expands or shrinks the size of the geographic region from which traffic is routed to a resource.
  * **Multivalue Answer Routing**
    * Multivalue answer routing lets you configure Amazon Route 53 to return multiple values, such as IP addresses for your web servers, in response to DNS queries. You can specify multiple values for almost any record, but multivalue answer routing also lets you check the health of each resource, so Route 53 returns only values for healthy resources. It's not a substitute for a load balancer, but the ability to return multiple health-checkable IP addresses is a way to use DNS to improve availability and load balancing.
  * **Complex/Nested records**
    * Can combine different routing policies by routing to alias records that point to Route 53 again.
      * E.g. can use *latency* policy to route into certain region
      * From there (in the regions) a *weighted* routing policy distributes traffic further

<a name="5_9_3"></a>
### [↖](#5_9)[↑](#5_9_2_4)[↓](#5_9_3_1) Health Checks with Route 53
<a name="5_9_3_1"></a>
#### [↖](#5_9)[↑](#5_9_3)[↓](#5_9_3_2) Trigger automated DNS failover
* Monitor an **endpoint** (application, server, other AWS resource)
* Monitor other **health checks** (calculated health checks)
* Monitor **CloudWatch alarms** (full control !!) – e.g. throttles of DynamoDB, alarms on RDS, custom metrics, etc
* Health Checks are integrated with CloudWatch metric

<a name="5_9_3_2"></a>
#### [↖](#5_9)[↑](#5_9_3_1)[↓](#5_9_3_3) Setup
* Health Checks can be setup to pass/fail based on text in the first 5120 bytes of the response
* Health Checks pass only with the 2xx and 3xx status response
* Calculated health checks
  * Create separate individual health checks
  * Specify how many of the health checks need to pass to make the parent pass
* Health Checks can trigger CloudWatch Alarms

<a name="5_9_3_3"></a>
#### [↖](#5_9)[↑](#5_9_3_2)[↓](#5_9_4) Private Hosted Zones
* Route 53 health checkers are outside the VPC
* They can’t access private endpoints (private VPC or on-premises resource)

Options:
* To check a resource within a VPC, you must assign a public IP address.
* You can configure the health checker to check the health of an external resource the instance relies on, for example a database server.
* You can create a CloudWatch metric and associate an alarm. You then create a health check that checks the alarm itself.

<a name="5_9_4"></a>
### [↖](#5_9)[↑](#5_9_3_3)[↓](#5_10) Sharing a Private Zone across multiple VPCs
* Having a central private “Shared Services” DNS can ease management
* Oher accounts may want to access the central private DNS records
  * Connectivity between VPC must be established (VPC peering, TGW)
  * Must programmatically (CLI) *associate the VPC* with the central hosted zone
* One association must be created for each new account

---

<a name="5_10"></a>
## [↖](#top)[↑](#5_9_4)[↓](#5_10_1) Solution Architeture Comparision
<!-- toc_start -->
* [EC2 on its own with Elastic IP](#5_10_1)
* [EC2 with Route53](#5_10_2)
* [ALB + ASG](#5_10_3)
* [ALB + ECS on EC2](#5_10_4)
* [ALB + ECS on Fargate](#5_10_5)
* [ALB + Lambda](#5_10_6)
* [API Gateway + Lambda](#5_10_7)
* [API Gateway + AWS Service](#5_10_8)
* [API Gateway + HTTP backend (ex: ALB)](#5_10_9)
<!-- toc_end -->
<a name="5_10_1"></a>
### [↖](#5_10)[↑](#5_10)[↓](#5_10_2) EC2 on its own with Elastic IP
* Quick failover
* The client should not see the change happen
* Helpful if the client needs to resolve by static Public IP address
* Does not scale
* Cheap

<a name="5_10_2"></a>
### [↖](#5_10)[↑](#5_10_1)[↓](#5_10_3) EC2 with Route53
* “DNS-based load balancing”
* Ability to use multiple instances
* Route53 TTL implies client may get outdated information
* Clients must have logic to deal with hostname resolution failures
* Adding an instance may not receive full traffic right away due to DNS TTL

<a name="5_10_3"></a>
### [↖](#5_10)[↑](#5_10_2)[↓](#5_10_4) ALB + ASG
* Scales well, classic architecture
* New instances are in service right away.
* Users are not sent to instances that are out-of-service
* Time to scale is slow (EC2 instance startup + bootstrap) – AMI can help
* ALB is elastic but can’t handle sudden, huge peak of demand (pre-warm)
* Could lose a few requests if instances are overloaded
* CloudWatch used for scaling
* Cross-Zone balancing for even traffic distribution
* Target utilization should be between 40% and 70%

<a name="5_10_4"></a>
### [↖](#5_10)[↑](#5_10_3)[↓](#5_10_5) ALB + ECS on EC2
* Same properties as ALB + ASG
* Application is run on Docker
* ASG + ECS allows to have dynamic port mappings
* Tough to orchestrate ECS service auto-scaling + ASG auto-scaling

<a name="5_10_5"></a>
### [↖](#5_10)[↑](#5_10_4)[↓](#5_10_6) ALB + ECS on Fargate
* Application is run on Docker
* Service Auto Scaling is easy
* Time to be in-service is quick (no need to launch an EC2 instance in advance)
* Still limited by the ALB in case of sudden peaks
* “serverless” application tier
* “managed” load balancer

<a name="5_10_6"></a>
### [↖](#5_10)[↑](#5_10_5)[↓](#5_10_7) ALB + Lambda
* Limited to Lambda’s runtimes
* Seamless scaling thanks to Lambda
* Simple way to expose Lambda functions as HTTP/S without all the features from API Gateway
* Can combine with WAF (Web Application Firewall)
* Good for hybrid microservices
* Example: use ECS for some requests, use Lambda for others

<a name="5_10_7"></a>
### [↖](#5_10)[↑](#5_10_6)[↓](#5_10_8) API Gateway + Lambda
* Pay per request, seamless scaling, fully serverless
* Soft limits: 10000/s API Gateway, 1000 concurrent Lambda
* API Gateway features: authentication, rate limiting, caching, etc...
* Lambda Cold Start time may increase latency for some requests
* Fully integrated with X-Ray

<a name="5_10_8"></a>
### [↖](#5_10)[↑](#5_10_7)[↓](#5_10_9) API Gateway + AWS Service
* Lower latency, cheaper
* Not using Lambda concurrent capacity, no custom code
* Expose AWS APIs securely through API Gateway
* SQS, SNS, Step Functions...
* Remember API Gateway has a payload limit of 10 MB (can be a problem for S3 proxy)

<a name="5_10_9"></a>
### [↖](#5_10)[↑](#5_10_8)[↓](#6) API Gateway + HTTP backend (ex: ALB)
* Use API Gateway features on top of custom HTTP backend (authentication, rate control, API keys, caching...)
* Can connect to...
  * On-premises service
  * Application Load Balancer
  * 3rd party HTTP service

---

<a name="6"></a>
# [↖](#top)[↑](#5_10_9)[↓](#6_1) Storage
<a name="6_1"></a>
## [↖](#top)[↑](#6)[↓](#6_1_1) EBS
<!-- toc_start -->
* [Overview](#6_1_1)
* [Volume options](#6_1_2)
* [Snaphosts](#6_1_3)
* [Moving Instances/Volumes To A Different AZ/Region](#6_1_4)
* [Encrypting root volumes](#6_1_5)
<!-- toc_end -->

<a name="6_1_1"></a>
### [↖](#6_1)[↑](#6_1)[↓](#6_1_2) Overview
Amazon Elastic Block Store (EBS) is an easy to use, high-performance, block-storage service designed for use with Amazon Elastic Compute Cloud (EC2) for both throughput and transaction intensive workloads at any scale. A broad range of workloads, such as relational and non-relational databases, enterprise applications, containerized applications, big data analytics engines, file systems, and media workflows are widely deployed on Amazon EBS.

You can choose from six different volume types to balance optimal price and performance. You can achieve single-digit-millisecond latency for high-performance database workloads such as SAP HANA or gigabyte per second throughput for large, sequential workloads such as Hadoop. You can change volume types, tune performance, or increase volume size without disrupting your critical applications, so you have cost-effective storage when you need it.

Designed for mission-critical systems, EBS volumes are replicated within an Availability Zone (AZ) and can easily scale to petabytes of data. Also, you can use EBS Snapshots with automated lifecycle policies to back up your volumes in Amazon S3, while ensuring geographic protection of your data and business continuity.
* **Permanent block storage**, independent to instance
* Attachable to running EC2 instances (same AZ)
* Only accessible by a *single instance*
* Can be resized while attached to an instance
* Volume type and throughput can be changed while attached to an instance
* Can be encrypted
* Can be stopped, data will persist
* Stores redundantly in *single* AZ
* Only root volumes are terminated if instance gets terminate
* Can be striped together to RAID
* Pick instance type that's *EBS-optimized*
* On AWS: <a href="https://aws.amazon.com/ebs/" target="_blank">Service</a> - <a href="https://aws.amazon.com/ebs/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AmazonEBS.html" target="_blank">User Guide</a>

<a name="6_1_2"></a>
### [↖](#6_1)[↑](#6_1_1)[↓](#6_1_3) Volume options
.|.|.|.
-|-|-|-
**General purpose SSD** (cheap)|gp2|`100 IOPS >= x <= 16,000 IOPS`|1 GiB - 16 TiB<br/>+1 TiB = 3,000 IOPS
**Provisioned IOPS** (expensive)|io1|`100 IOPS >= x <= 32,000 IOPS (other) <= 64,000 IOPS (Nitro)`|4 GiB - 16 TiB<br/>Size of volume and IOPS are independent
**Magnetic volumes, throughput optimized**|st1, hs1|* Frequently accessed workload<br/>* Cannot be boot volume|500 GiB – 16 TiB<br/>500 MiB/s throughput
**Magnetic volumes, cold**|sc1|* Less frequently accessed workload<br/>* Cannot be boot volume|250 GiB – 16 TiB<br/>250 MiB/s throughput
**Magnetic volumes, standard**|.|Can be boot volume|.

* Can change volume size on the fly, also storage type

<a name="6_1_3"></a>
### [↖](#6_1)[↑](#6_1_2)[↓](#6_1_4) Snaphosts
* Stored incrementally on S3
* Should stop instance if taking a snapshot of root volume
  * Or detach volume (recommended)
* Snaphots of encrypted volumes are encrypted automatically
* Snapshots can be shared with other account or made public - only if unencrypted
  * Can copy snapshots across region (for DR)
* Can create AMIs from EBS-backed instances and snapshots
* In order to take snapshots from RAID arrays, make sure all applications are stopped and caches are flushed to disk
* EBS volumes restored by snapshots need to be pre-warmed
  * Using `fio` or `dd` command to read the entire volume
* Lifecycle policies have been introduced for snapshots
* Snapshots can be automated using Amazon Data Lifecycle Manager

<a name="6_1_4"></a>
### [↖](#6_1)[↑](#6_1_3)[↓](#6_1_5) Moving Instances/Volumes To A Different AZ/Region
* Create snapshot in AZ1
* Use that to create volume in AZ2
* Also could have *copied* snapshot into different region

<a name="6_1_5"></a>
### [↖](#6_1)[↑](#6_1_4)[↓](#6_2) Encrypting root volumes
* Stop instance
* Create snapshot
* Copy to different region
  * Can encrypt while copying, resulting in an encrypted snapshot in the target region
* Create image from snapshot
* Launch instance from that image

---

<a name="6_2"></a>
## [↖](#top)[↑](#6_1_5)[↓](#6_2_1) Local Instance Store
<!-- toc_start -->
* [EBS vs Instance Store](#6_2_1)
<!-- toc_end -->
* Physical disk attached to the physical server where your EC2 is
* Very High IOPS (because physical)
* Disks up to 7.5 TiB (can change over time), striped (RAID 0) to reach 30 TiB (can change over time...)
* Block Storage (just like EBS)
* Cannot be increased in size
* Risk of data loss if hardware fails

<a name="6_2_1"></a>
### [↖](#6_2)[↑](#6_2)[↓](#6_3) EBS vs Instance Store
* Some instance do not come with Root EBS volumes
* Instead, they come with “Instance Store” (= ephemeral storage)
* Instance store is physically attached to the machine (EBS is a network drive)
* Pros:
  * Better I/O performance (EBS gp2 has an max IOPS of 16000, io1 of 64000)
  * Good for buffer/cache/scratch data/temporary content
  * Data survives reboots
* Cons:
  * On stop or termination, the instance store is lost
  * You can’t resize the instance store
  * Backups must be operated by the user

---

<a name="6_3"></a>
## [↖](#top)[↑](#6_2_1)[↓](#6_3_1) EFS
<!-- toc_start -->
* [Overview](#6_3_1)
* [Performance & Storage Classes](#6_3_2)
<!-- toc_end -->
<a name="6_3_1"></a>
### [↖](#6_3)[↑](#6_3)[↓](#6_3_2) Overview
Amazon Elastic File System (Amazon EFS) provides a simple, scalable, fully managed elastic NFS file system for use with AWS Cloud services and on-premises resources. It is built to scale on demand to petabytes without disrupting applications, growing and shrinking automatically as you add and remove files, eliminating the need to provision and manage capacity to accommodate growth.

Amazon EFS offers two storage classes: the Standard storage class, and the Infrequent Access storage class (EFS IA). EFS IA provides price/performance that's cost-optimized for files not accessed every day. By simply enabling EFS Lifecycle Management on your file system, files not accessed according to the lifecycle policy you choose will be automatically and transparently moved into EFS IA. The EFS IA storage class costs only $0.025/GB-month*.

While workload patterns vary, customers typically find that 80% of files are infrequently accessed (and suitable for EFS IA), and 20% are actively used (suitable for EFS Standard), resulting in an effective storage cost as low as $0.08/GB-month*. Amazon EFS transparently serves files from both storage classes in a common file system namespace.

Amazon EFS is designed to provide massively parallel shared access to thousands of Amazon EC2 instances, enabling your applications to achieve high levels of aggregate throughput and IOPS with consistent low latencies.

Amazon EFS is well suited to support a broad spectrum of use cases from home directories to business-critical applications. Customers can use EFS to lift-and-shift existing enterprise applications to the AWS Cloud. Other use cases include: big data analytics, web serving and content management, application development and testing, media and entertainment workflows, database backups, and container storage.

Amazon EFS is a regional service storing data within and across multiple Availability Zones (AZs) for high availability and durability. Amazon EC2 instances can access your file system across AZs, regions, and VPCs, while on-premises servers can access using AWS Direct Connect or AWS VPN.
* Managed NFS (network file system) that can be mounted on many EC2
* EFS works with EC2 instances in multi-AZ, & on–premises (via Direct Connect or Site-To-Site VPN)
* Highly available, scalable, expensive (3x gp2), pay per GB used
* Use cases: content management, web serving, data sharing, Wordpress
* Compatible with Linux based AMI (not Windows), POSIX-compliant
* Uses NFSv4.1 protocol
* Uses security group to control access to EFS
* Encryption at rest using KMS
* Can only attach to one VPC, create *one ENI per AZ* (mount target)
  * Other VPC can access EFS via VPC peering
* On AWS: <a href="https://aws.amazon.com/efs/" target="_blank">Service</a> - <a href="https://aws.amazon.com/efs/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/efs/latest/ug/whatisefs.html" target="_blank">User Guide</a>
* See also: <a href="https://www.awsgeek.com/amazon-efs/" target="_blank">AWS Geek 2020</a>

<a name="6_3_2"></a>
### [↖](#6_3)[↑](#6_3_1)[↓](#6_4) Performance & Storage Classes
* EFS Scale
  * 1000s of concurrent NFS clients, 10 GB+/s throughput
  * Grow to Petabyte-scale network file system
* Performance mode (set at EFS creation time)
  * *General purpose* (default): latency-sensitive use cases (web server, CMS, etc...)
  * *Max I/O* – higher latency, higher throughput, highly parallel (big data, media processing)
* Throughput Mode
  * *Bursting Mode*: common for filesystems (intensive work, then almost nothing), linked to FS size
  * *Provisioned IO Mode*: high throughput to storage ratio (if burst is not enough) – expensive
* Storage Tiers (lifecycle management feature – move file after N days)
  * *Standard*: for frequently accessed file
  * *Infrequent access*: higher cost to retrieve the file, lower price point to store the file

---

<a name="6_4"></a>
## [↖](#top)[↑](#6_3_2)[↓](#6_4_1) Amazon S3
<!-- toc_start -->
* [Overview](#6_4_1)
* [Getting Data In And Out](#6_4_2)
  * [Perfomance & Consistency](#6_4_2_1)
  * [Versioning](#6_4_2_2)
  * [S3 Events Notifications](#6_4_2_3)
  * [Logging](#6_4_2_4)
  * [Perfomance](#6_4_2_5)
  * [Cross Region Replication/Same Region Replication](#6_4_2_6)
  * [Hosting Static Websites](#6_4_2_7)
  * [Storage classes](#6_4_2_8)
* [Access Control](#6_4_3)
  * [Defaults](#6_4_3_1)
  * [IAM](#6_4_3_2)
  * [Bucket policies](#6_4_3_3)
  * [ACLs](#6_4_3_4)
  * [How to specify resources in a policy:](#6_4_3_5)
* [Pre-signed URLs](#6_4_4)
* [Encryption](#6_4_5)
  * [Protecting data in transit](#6_4_5_1)
  * [Protecting data at rest](#6_4_5_2)
* [Etc](#6_4_6)
  * [Pricing](#6_4_6_1)
  * [Limits](#6_4_6_2)
<!-- toc_end -->

<a name="6_4_1"></a>
### [↖](#6_4)[↑](#6_4)[↓](#6_4_2) Overview
Amazon Simple Storage Service (S3) is object storage with a simple web service interface to store and retrieve any amount of data from anywhere on the web. It is designed to deliver 11x9 *durability* and scale past trillions of objects worldwide.
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
* Anti patterns:
  * Lots of small files
  * POSIX file system (use EFS instead), file locks
  * Search features, queries, rapidly changing data
  * Website with dynamic content
* On AWS: <a href="https://aws.amazon.com/s3/" target="_blank">Service</a> - <a href="https://aws.amazon.com/s3/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html" target="_blank">User Guide</a>
<a name="6_4_2"></a>
### [↖](#6_4)[↑](#6_4_1)[↓](#6_4_2_1) Getting Data In And Out

<a name="6_4_2_1"></a>
#### [↖](#6_4)[↑](#6_4_2)[↓](#6_4_2_2) Perfomance & Consistency
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

<a name="6_4_2_2"></a>
#### [↖](#6_4)[↑](#6_4_2_1)[↓](#6_4_2_3) Versioning
* Works on bucket level (for *all* objects)
* Versioning can either be *unversioned* (default), *enabled* or *suspended*
* **Version ids** are automatically assigned to objects
	* Ids cannot changed.
	* As long as versioning is *disabled*, id is set to `null`
	* Once enabled, versioning can only be suspended (but not disabled)
		* `null` is the version id of the first version after enabling
	* `PUT` creates a new version, `GET` returns the latest version. Specific versions can be requested.
	* `DELETE` (without version) marks latest version as deleted and returns a `404` for subsequent `GET`s.
		* Older versions (pre-delete) can still be requested.
		* Restore old version by deleting the new version or by copying the old version on top of the bucket.
	* `DELETE` (with a version) permanently deletes that version.
	* If versioning is *suspendend*, S3 automatically adds a `null` version ID to every subsequent object stored thereafter
* *Lifecycle Management policies* can automatically handle old versions, e.g. permanently delete or move to *AWS Glacier*.
* Different versions of the same object can have different permissions.
* Can enable *MFA delete* for an extra layer of security.
* Versioning integrates with lifecycle rules.

<a name="6_4_2_3"></a>
#### [↖](#6_4)[↑](#6_4_2_2)[↓](#6_4_2_4) S3 Events Notifications
* `S3:ObjectCreated`, `S3:ObjectRemoved`, `S3:ObjectRestore`, `S3:Replication`...
* Object name filtering possible (`*.jpg`)
* Use case: generate thumbnails of images uploaded to S3
* S3 event notifications typically deliver events in seconds but can sometimes take a minute or longer
* If two writes are made to a single non- versioned object at the same time, it is possible that only a single event notification will be sent
* If you want to ensure that an event notification is sent for every successful write, you can enable versioning on your bucket.

<a name="6_4_2_4"></a>
#### [↖](#6_4)[↑](#6_4_2_3)[↓](#6_4_2_5) Logging
* *AWS CloudTrail* logs S3-API calls for *bucket-level* operations (and many other information) and stores them in an S3 bucket. Could also send email notifications or trigger *SNS* notifications for specific events.
* You can also get *AWS CloudTrail* logs for *object-level* Amazon S3 actions. To do this, enable data events for your S3 bucket or all buckets in your account.
* *S3 Server Access Logs* log on *object-level*.
  * Provide detailed records for the requests that are made to a bucket
  * Needs to be enabled on bucket level

<a name="6_4_2_5"></a>
#### [↖](#6_4)[↑](#6_4_2_4)[↓](#6_4_2_6) Perfomance
* Amazon S3 automatically scales to high request rates, latency 100-200 ms
* Your application can achieve at least 3,500 PUT/COPY/POST/DELETE and 5,500 GET/HEAD requests per second per prefix in a bucket.
* There are no limits to the number of prefixes in a bucket.
* Example (object path => prefix):
  * `bucket/folder1/sub1/file` => `/folder1/sub1/`
  * `bucket/folder1/sub2/file` => `/folder1/sub2/`
  * `bucket/1/file` => `/1/`
  * `bucket/2/file` => `/2/`
* If you spread reads across all four prefixes evenly, you can achieve 22,000 requests per second for GET and HEAD
* **Multi-part upload**
  * recommended for files > 100MB, must use for files > 5GB
  * Can help parallelize uploads (speed up transfers)
* **Transfer Acceleration**
  * *Amazon S3 Transfer Acceleration* enables fast, easy, and secure transfers (upload & download) of files over long distances between your client and an S3 bucket. Transfer Acceleration takes advantage of Amazon CloudFront’s globally distributed edge locations. As the data arrives at an edge location, data is routed to Amazon S3 over an optimized network path.
  * File upload/downloads through an Edge location via a dedicated CloudFront endpoint
  * Compatible with multi-part upload
* **S3 Byte-Range Fetches**
  * Parallelize GETs by requesting specific byte ranges
  * Better resilience in case of failures
  * Can be used to speed up downloads
  * Can be used to retrieve only partial data (for example the head of a file)
* **S3 Select & Glacier Select**
  * Retrieve less data using SQL by performing *server side filtering*
  * Works on objects stored in CSV, JSON, or Apache Parquet format
  * Can filter by rows & columns (simple SQL statements)
  * Less network transfer, less CPU cost client-side

<a name="6_4_2_6"></a>
#### [↖](#6_4)[↑](#6_4_2_5)[↓](#6_4_2_7) Cross Region Replication/Same Region Replication
Replication enables automatic, asynchronous copying of objects across Amazon S3 buckets. Buckets that are configured for object replication can be owned by the same AWS account or by different accounts. Object may be replicated to a single destination bucket or multiple destination buckets. Destination buckets can be in different AWS Regions or within the same Region as the source bucket.
* Use cases
  * Reduce latency
  * Disaster recovery
  * Helpful for security
* Only new/changed objects will be replicated
* Cannot chain replications
* Can replicate complete buckets or subfolder ('prefix')
* Can be combined with Lifecycle Policies
* Deleting of individual versions or delete markers is *not* replicated
* Best way to copy existing objects over is using AWS CLI

<a name="6_4_2_7"></a>
#### [↖](#6_4)[↑](#6_4_2_6)[↓](#6_4_2_8) Hosting Static Websites
`<bucket-name>.s3-website-<AWS-Region>.amazonaws.com`
* Bucket name *must* match domain name. Every hosted bucket recieves its own URL
* Use *AWS Route 53* to integrate custom domains (also to automatically fail-over from dynamic website)
* Specify `index` & `error` documents
* In *AWS Route 53*: create hosted zone & record set
* Might need to add CORS configuration to bucket (cross origin resource sharing)

<a name="6_4_2_8"></a>
#### [↖](#6_4)[↑](#6_4_2_7)[↓](#6_4_3) Storage classes
.|Durability|Availability|AZs|Costs per GB|Retrieval Fee|.
-|-|-|-|-|-|-
S3 Standard|**11x9**|**4x9**|**>=3**|$0.023|**No**|.
S3 Intelligent Tiering|**11x9**|3x9|**>=3**|$0.023|**No**|Automatically moves objects between two access tiers based on changing access patterns
S3 IA (infrequent access)|**11x9**|3x9|**>=3**|$0.0125|Yes|For data that is accessed less frequently, but requires rapid access when needed
S3 One Zone IA (infrequent access)|**11x9**|99.5|1|**$0.01**|Yes|For data that is accessed less frequently, but requires rapid access when needed
Glacier|**11x9**|.|**>=3**|.|Yes|For archival only, comes as *expedited* (1-5min), *standard* (3-5h) or *bulk* (5-12h)
Glacier Deep Archive|**11x9**|.|**>=3**|.|Yes|Longer time span to retrieve
~~S3 RRS (reduced redundancy storage)~~|4x9|4x9|>=3|$0.024|.|Deprecated

* Can transition objects between tiers (or delete) using S3 Lifecycle Policies

<a name="6_4_3"></a>
### [↖](#6_4)[↑](#6_4_2_8)[↓](#6_4_3_1) Access Control
* **Effect** – This can be either allow or deny
* **Principal** – Account or user who is allowed access to the actions and resources in the statement
* **Actions** – For each resource, S3 supports a set of operations
* **Resources** – Buckets and objects are the resources
* Authorization works as a *union* of **IAM** & **bucket policies** and **bucket ACLs**
<a name="6_4_3_1"></a>
#### [↖](#6_4)[↑](#6_4_3)[↓](#6_4_3_2) Defaults
* Bucket is *owned* by the AWS account that created it
  * Ownership refers to the identity and email address used to create the account
	* Bucket ownership is not transferable
* Bucket owner gets full permission (ACL)
* The person paying the bills always has full control.
* A person uploading an object into a bucket owns it by default.
<a name="6_4_3_2"></a>
#### [↖](#6_4)[↑](#6_4_3_1)[↓](#6_4_3_3) IAM
* IAM policies (in general) specify what actions are allowed or denied on what AWS resources
* Defined as JSON
* Attached to IAM users, groups, or roles (so they cannot grant access to anonymous users)
* Use if you’re more interested in *“What can this user do in AWS?”*
<a name="6_4_3_3"></a>
#### [↖](#6_4)[↑](#6_4_3_2)[↓](#6_4_3_4) Bucket policies
* Specify what actions are allowed or denied for which principals on the bucket that the policy is
attached to
* Defined as JSON
* Attached *only* to S3 buckets. Can however effect object in buckets.
* Contain *principal* element (unnecessary for IAM)
* Use if you’re more interested in *“Who can access this S3 bucket?”*
* Easiest way to grant *cross-account permissions* for all `s3:*` permission. (Cannot do this with ACLs.)
<a name="6_4_3_4"></a>
#### [↖](#6_4)[↑](#6_4_3_3)[↓](#6_4_3_5) ACLs
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
<a name="6_4_3_5"></a>
#### [↖](#6_4)[↑](#6_4_3_4)[↓](#6_4_4) How to specify resources in a policy:
.|.
-|-
`arn:partition:service:region:namespace:relative-id`|`arn:aws:s3:::mybucket`
`arn:aws:s3:::*`|All buckets and objects in account
`arn:aws:s3:::mybucket`|`mybucket`
`arn:aws:s3:::mybucket/*`|All objects in `mybucket`
`arn:aws:s3:::mybucket/mykey`|`mykey` in `mybucket`
`arn:aws:s3:::mybucket/developers/($aws:username)/`|folder matching the accessing user's name
<a name="6_4_4"></a>
### [↖](#6_4)[↑](#6_4_3_5)[↓](#6_4_5) Pre-signed URLs
All objects are private by default. Only the object owner has permission to access these objects. However, the object owner can optionally share objects with others by creating a **pre-signed URL**, using their own security credentials, to grant time-limited permission to download the objects.

<a name="6_4_5"></a>
### [↖](#6_4)[↑](#6_4_4)[↓](#6_4_5_1) Encryption

<a name="6_4_5_1"></a>
#### [↖](#6_4)[↑](#6_4_5)[↓](#6_4_5_2) Protecting data in transit
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
<a name="6_4_5_2"></a>
#### [↖](#6_4)[↑](#6_4_5_1)[↓](#6_4_6) Protecting data at rest
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

<a name="6_4_6"></a>
### [↖](#6_4)[↑](#6_4_5_2)[↓](#6_4_6_1) Etc

<a name="6_4_6_1"></a>
#### [↖](#6_4)[↑](#6_4_6)[↓](#6_4_6_2) Pricing
Charged by
  * Storage
  * Requests
  * Storage management pricing
    * Tags
  * Data transfer
    * For cross-region transfers only
  * Transfer acceleration (feature)

<a name="6_4_6_2"></a>
#### [↖](#6_4)[↑](#6_4_6_1)[↓](#6_5) Limits
.|.
-|-
Buckets per account|100
Bucket policy max size|20KB
Object size|0B to 5TB
Object size in a single `PUT`|5GB

---

<a name="6_5"></a>
## [↖](#top)[↑](#6_4_6_2)[↓](#6_5_1) S3 Solution Architecture
<!-- toc_start -->
* [Exposing Static Objects](#6_5_1)
* [Indexing objects in DynamoDB](#6_5_2)
<!-- toc_end -->

<a name="6_5_1"></a>
### [↖](#6_5)[↑](#6_5)[↓](#6_5_2) Exposing Static Objects
* -> `EC2 instance storage`
* -> `CloudFront` - `EC2` - `EBS`
* -> `CloudFront` - `ALB` - `ASG` - `EFS`
  * Requires Linux for EFS
* -> `CloudFront` - `S3`

<a name="6_5_2"></a>
### [↖](#6_5)[↑](#6_5_1)[↓](#6_6) Indexing objects in DynamoDB
* -> `S3` - `Lambda` - `DynamoDB`
* Problem: No indexing facility in S3, cannot search
  * API for object metadata in DynamoDB:
    * Search by date
    * Total storage used by a customer
    * List of all objects with certain attributes
    * Find all objects uploaded within a date range

---

<a name="6_6"></a>
## [↖](#top)[↑](#6_5_2)[↓](#7) S3 vs EFS vs EBS Comparison
Amazon S3|Amazon EBS|Amazon EFS
-|-|-
Can be publicly accessible|Accessible only via the given EC2 Machine|Accessible via several EC2 machines and AWS services
Web interface|File system interface|Web and file system interface
Object Storage|Block storage|Object storage
Scalable|Hardly scalable|Scalable
Slowest|Fastest|Faster than S3, slower than EBS
Good for storing backups|Is meant to be EC2 drive|Good for shareable applications and workloads
Elastic, only pay for used storage|Fixed, pay for provisioned storage|Elastic, only pay for used storage

---

<a name="7"></a>
# [↖](#top)[↑](#6_6)[↓](#7_1) Caching
<a name="7_1"></a>
## [↖](#top)[↑](#7)[↓](#7_1_1) CloudFront (Core Topic)
<!-- toc_start -->
* [Overview](#7_1_1)
* [Basic workflow](#7_1_2)
* [Origin](#7_1_3)
* [CloudFront vs S3 Cross Region Replication](#7_1_4)
* [CloudFront Geo Restriction](#7_1_5)
* [Signed URL/Signed Cookies](#7_1_6)
  * [Trusted Signer](#7_1_6_1)
* [Field-Level Encryption](#7_1_7)
* [Caching](#7_1_8)
  * [CloudFront Caching vs API Gateway Caching](#7_1_8_1)
* [Lambda@Edge](#7_1_9)
* [https](#7_1_10)
  * [Scenario 1 (requires 2 certs)](#7_1_10_1)
  * [Scenario 2 (doesn't work)](#7_1_10_2)
  * [Scenario 2 (requires 1 cert)](#7_1_10_3)
<!-- toc_end -->
<a name="7_1_1"></a>
### [↖](#7_1)[↑](#7_1)[↓](#7_1_2) Overview
Amazon CloudFront is a web service that speeds up distribution of your static and dynamic web content, such as .html, .css, .js, and image files, to your users. CloudFront delivers your content through a worldwide network of data centers called edge locations. When a user requests content that you're serving with CloudFront, the request is routed to the edge location that provides the lowest latency (time delay), so that content is delivered with the best possible performance.
* If the content is already in the edge location with the lowest latency, CloudFront delivers it immediately.
* If the content is not in that edge location, CloudFront retrieves it from an origin that you've defined—such as an Amazon S3 bucket, a MediaPackage channel, or an HTTP server (for example, a web server) that you have identified as the source for the definitive version of your content.

CloudFront speeds up the distribution of your content by routing each user request through the AWS backbone network to the edge location that can best serve your content. Typically, this is a CloudFront edge server that provides the fastest delivery to the viewer. Using the AWS network dramatically reduces the number of networks that your users' requests must pass through, which improves performance. Users get lower latency—the time it takes to load the first byte of the file and higher data transfer rates.

You also get increased reliability and availability because copies of your files (also known as objects) are now held (or cached) in multiple edge locations around the world.
* Content Delivery Network (CDN)
* Improves read performance, content is cached at the edge
* 225 Point of Presence globally (edge locations)
* DDoS protection, integration with Shield, AWS Web Application Firewall
	* Only accepts well-formed connections to prevent many common DDoS attacks like SYN floods and UDP reflection attacks from reaching your origin.
* Can expose external HTTPS and can talk to internal HTTPS backends
* On AWS: <a href="https://aws.amazon.com/cloudfront/" target="_blank">Service</a> - <a href="https://aws.amazon.com/cloudfront/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html" target="_blank">User Guide</a>

<a name="7_1_2"></a>
### [↖](#7_1)[↑](#7_1_1)[↓](#7_1_3) Basic workflow
* You specify origin servers, like an Amazon S3 bucket or your own HTTP server, from which CloudFront gets your files which will then be distributed from CloudFront edge locations all over the world.
* An origin server stores the original, definitive version of your objects.
* You upload your files to your origin servers.
* If you're using an Amazon S3 bucket as an origin server, you can make the objects in your bucket publicly readable, so that anyone who knows the CloudFront URLs for your objects can access them. You also have the option of keeping objects private and controlling who accesses them. See "Serving private content with signed URLs and signed cookies".
* You create a CloudFront distribution, which tells CloudFront which origin servers to get your files
* CloudFront assigns a domain name to your new distribution
* CloudFront sends your distribution's configuration (but not your content) to all of its edge locations

<a name="7_1_3"></a>
### [↖](#7_1)[↑](#7_1_2)[↓](#7_1_4) Origin
An origin is the location where content is stored, and from which CloudFront gets content to serve to viewers. To specify an origin:
* An Amazon S3 bucket that is configured with static website hosting
* An Amazon S3 bucket that is not configured with static website hosting
* An Elastic Load Balancing load balancer
* An AWS Elemental MediaPackage endpoint
* An AWS Elemental MediaStore container
* Any other HTTP server, running on an Amazon EC2 instance or any other kind of host

Can have primary and secondary origin (**HA/Failover**)

Origin|How content is accessed
-|-
S3|CloudFront assumes Origin Access Identity<br/>S3 Bucket Policy
EC2|Must have public IPs
ALB (-> EC2)|ALB must have public IP, EC2 can be private

<a name="7_1_4"></a>
### [↖](#7_1)[↑](#7_1_3)[↓](#7_1_5) CloudFront vs S3 Cross Region Replication


**CloudFront**|**S3 Cross Region Replication**
-|-
Global Edge network|Must be setup for each region you want replication to happen
Files are cached for a TTL (maybe a day)|Files are updated in near real-time
Great for static content that must be available everywhere|Read only
.|Great for dynamic content that needs to be available at low-latency in few regions

<a name="7_1_5"></a>
### [↖](#7_1)[↑](#7_1_4)[↓](#7_1_6) CloudFront Geo Restriction
* You can restrict who can access your distribution
  * Whitelist: Allow your users to access your content only if they're in one of the countries on a list of approved countries.
  * Blacklist: Prevent your users from accessing your content if they're in one of the countries on a blacklist of banned countries.
* The “country” is determined using a 3 rd party Geo-IP database
* Use case: Copyright Laws to control access to content

<a name="7_1_6"></a>
### [↖](#7_1)[↑](#7_1_5)[↓](#7_1_6_1) Signed URL/Signed Cookies
* You want to distribute paid shared content to premium users over the world
* We can use CloudFront Signed URL/Cookie. We attach a policy with:
  * Includes URL expiration
  * Includes IP ranges to access the data from
  * Trusted signers (which AWS *accounts* can create signed URLs)
* How long should the URL be valid for?
  * Shared content (movie, music): make it short (a few minutes)
  * Private content (private to the user): you can make it last for years
* Signed URL = access to *individual* files (one signed URL per file)
* Signed Cookies = access to *multiple* files (one signed cookie for many files)
* Need to implement logic to sign URLs ourselves!

Signed URL/Cookie|S3 Pre-Signed URL
-|-
Allow access to a path, no matter the origin|Issue a request as the person who pre-signed the URL
Account wide key-pair, only the root can manage it|Uses the IAM key of the signing IAM principal
Can filter by IP, path, date, expiration|Limited lifetime
Can leverage caching features|.

<a name="7_1_6_1"></a>
#### [↖](#7_1)[↑](#7_1_6)[↓](#7_1_7) Trusted Signer
To create signed URLs or signed cookies, you need a signer. A signer is either a trusted key group that you create in CloudFront, or an AWS account that contains a CloudFront key pair.We recommend that you use trusted key groups, for the following reasons:

* With CloudFront key groups, you don’t need to use the AWS account root user to manage the public keys for CloudFront signed URLs and signed cookies.
* With CloudFront key groups, you can manage public keys, key groups, and trusted signers using the CloudFront API.
* Because you can manage key groups with the CloudFront API, you can also use AWS Identity and Access Management (IAM) permissions policies to limit what different users are allowed to do.
* When you use the AWS account root user to manage CloudFront key pairs, you can’t restrict what the root user can do or the conditions in which it can do them.
* With CloudFront key groups, you can associate a higher number of public keys with your CloudFront distribution.

<a name="7_1_7"></a>
### [↖](#7_1)[↑](#7_1_6_1)[↓](#7_1_8) Field-Level Encryption
* You can enforce secure end-to-end connections to origin servers by using HTTPS. Field-level encryption adds an additional layer of security that lets you protect specific data throughout system processing so that only certain applications can see it.
* When you configure your CloudFront distribution, specify the set of fields in POST requests that you want to be encrypted, and the public key to use to encrypt them. You can encrypt up to 10 data fields in a request.

<a name="7_1_8"></a>
### [↖](#7_1)[↑](#7_1_7)[↓](#7_1_8_1) Caching
* Cache based on
  * Headers
      * Strategy: Whitelist headers that should be cached on, ignore others
  * Session Cookies
  * Query String Parameters
* The cache lives at each CloudFront Edge Location
* You want to maximize the cache hit rate to minimize requests on the origin
* Control the TTL (0 seconds to 1 year), can be set by the origin using the Cache-Control header, Expires header...
* Maximize cache hits by separating static and dynamic distributions
  * Static distribution doesn't need complicated configuration
  * Dynamic distributions caches based on correct headers and cookies

<a name="7_1_8_1"></a>
#### [↖](#7_1)[↑](#7_1_8)[↓](#7_1_9) CloudFront Caching vs API Gateway Caching
API Gateway now has two different kinds of endpoints. The original design is now called *edge optimized*, and the new option is called *regional*. Regional endpoints do not use front-end services from CloudFront, and may offer lower latency when accessed from EC2 within the same AWS region. All existing endpoints were categorized as edge-optimized when the new regional capability was rolled out. With a regional endpoint, the CloudFront-* headers are not present in the request, unless you use your own CloudFront distribution and whitelist those headers for forwarding to the origin.
* Can deploy API Gateway in *regional mode* (comes with its own cache), *and* deploy a CloudFront distribution at the edge, that can have a cache too.
  * Allows for fine-grained control of caching
  * Many different options from here, could e.g. also disable API-Gateway cache

<a name="7_1_9"></a>
### [↖](#7_1)[↑](#7_1_8_1)[↓](#7_1_10) Lambda@Edge
* You have deployed a CDN using CloudFront
* What if you wanted to run a global AWS Lambda alongside?
* Or how to implement request filtering before reaching your application?
* For this, you can use Lambda@Edge: deploy Lambda functions alongside your CloudFront CDN
  * Build more responsive applications
  * You don’t manage servers, Lambda is deployed globally
  * Customize the CDN content
  * Pay only for what you use
**Scenarios**
* You can use Lambda to change CloudFront requests and responses:
  * After CloudFront receives a request from a viewer (viewer request)
  * Before CloudFront forwards the request to the origin (origin request)
  * After CloudFront receives the response from the origin (origin response)
  * Before CloudFront forwards the response to the viewer (viewer response)
* You can also generate responses to viewers without ever sending the request to the origin.
* Lambda@Edge does not have any cache. It’s only to change requests/responses
* Examples
  * Website Security and Privacy
    * Can e.g. use Lambda@Edge to validate authentication & authorization
  * Dynamic Web Application at the Edge
  * Search Engine Optimization (SEO)
  * Intelligently Route Across Origins and Data Centers
  * Bot Mitigation at the Edge
  * Real-time Image Transformation
  * A/B Testing
  * User Authentication and Authorization
  * User Prioritization, User Tracking and Analytics
  * Increasing the cache hit ratio (by modifying headers, normalize user-agent...)

<a name="7_1_10"></a>
### [↖](#7_1)[↑](#7_1_9)[↓](#7_1_10_1) https
* A viewer submits an HTTPS request to CloudFront. There's some SSL/TLS negotiation here between the viewer and CloudFront. In the end, the viewer submits the request in an encrypted format.
* If the object is in the CloudFront edge cache, CloudFront encrypts the response and returns it to the viewer, and the viewer decrypts it.
* If the object is not in the CloudFront cache, CloudFront performs SSL/TLS negotiation with your origin and, when the negotiation is complete, forwards the request to your origin in an encrypted format.
* Your origin decrypts the request, encrypts the requested object, and returns the object to CloudFront.
* CloudFront decrypts the response, re-encrypts it, and forwards the object to the viewer. CloudFront also saves the object in the edge cache so that the object is available the next time it's requested.
* The viewer decrypts the response.

<a name="7_1_10_1"></a>
#### [↖](#7_1)[↑](#7_1_10)[↓](#7_1_10_2) Scenario 1 (requires 2 certs)

.|CloudFront|ALB
-|-|-
hostname|www.example.com|origin.example.com
ssl cert|www.example.com|origin.example.com
origin|origin.example.com|.

If Host header is forwarded:
- www.example.com won’t match origin.example.com
- CloudFront will refuse the request

If Host header is *not* forwarded:
- CloudFront will add a Host header value of the origin: origin.example.com
- Requests & Responses will work

<a name="7_1_10_2"></a>
#### [↖](#7_1)[↑](#7_1_10_1)[↓](#7_1_10_3) Scenario 2 (doesn't work)

.|CloudFront|ALB
-|-|-
hostname|www.example.com|www.example.com
ssl cert|www.example.com|www.example.com
origin|www.example.com|.

Impossible, as CloudFront distribution will loop over itself!

<a name="7_1_10_3"></a>
#### [↖](#7_1)[↑](#7_1_10_2)[↓](#7_2) Scenario 2 (requires 1 cert)

.|CloudFront|ALB
-|-|-
hostname|www.example.com|origin.example.com
ssl cert|www.example.com|www.example.com
origin|origin.example.com|.

If Host header is forwarded:
- Host: www.example.com will match the www.example.com SSL certificate
- CloudFront will accept
- The correct Host value could be set by Lambda@Edge

If Host header is *not* forwarded:
- CloudFront will add a Host header value of the origin: origin.example.com
- origin.example.com will not match the SSL cert www.example.com
- The request will fail

---

<a name="7_2"></a>
## [↖](#top)[↑](#7_1_10_3)[↓](#7_2_1) ElastiCache (Core Topic)
<!-- toc_start -->
* [Overview](#7_2_1)
* [Scenarios](#7_2_2)
* [Memcached](#7_2_3)
* [Redis](#7_2_4)
<!-- toc_end -->

<a name="7_2_1"></a>
### [↖](#7_2)[↑](#7_2)[↓](#7_2_2) Overview
Amazon ElastiCache allows you to seamlessly set up, run, and scale popular open-source compatible in-memory data stores in the cloud. Build data-intensive apps or boost the performance of your existing databases by retrieving data from high throughput and low latency in-memory data stores.
* Amazon ElastiCache is a popular choice for real-time use cases like Caching, Session Stores, Gamin, Geospatial Services, Real-Time Analytics, and Queuing.
* Amazon ElastiCache offers fully managed Redis and Memcached for your most demanding applications that require sub-millisecond response times.
* Caches are in-memory databases with really high performance, low latency
* Helps reduce load off of databases for read intensive workloads
* Helps make your application stateless
* AWS takes care of OS maintenance/patching, optimizations, setup, configuration, monitoring, failure recovery and backups
* Using ElastiCache involves heavy application code changes
* ElastiCache is a good choice if database is read-heavy and not prone to frequent changing.
* On AWS: <a href="https://aws.amazon.com/elasticache/" target="_blank">Service</a> - <a href="https://aws.amazon.com/elasticache/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/elasticache/index.html" target="_blank">User Guide</a>

<a name="7_2_2"></a>
### [↖](#7_2)[↑](#7_2_1)[↓](#7_2_3) Scenarios
* Use as DB cache
  * `->` `application` - `Elasticache` - `RDS`
* User-session store
  * `->` `user` - `application` (x `n`)  - `Elasticache`

<a name="7_2_3"></a>
### [↖](#7_2)[↑](#7_2_2)[↓](#7_2_4) Memcached
* Simple key-value storage
* A widely adopted memory object caching system. ElastiCache is protocol compliant with Memcached, so popular tools that you use today with existing Memchached environments willwork seamlessly with the service.
* Multi-node for partitioning of data (sharding)
* Non persistent
* Single-AZ
* No backup and restore
* Support multi-threaded operations

<a name="7_2_4"></a>
### [↖](#7_2)[↑](#7_2_3)[↓](#7_3) Redis
* Advanced data structures
* A popular open-source in-memory key-value store that supports data structures such as sorted sets and lists. ElastiCache supports master/slave replication and multi-AZ which can be used to achieve cross-AZ-redundancy.
* Also offers Pub/Sub, Sorted Sets and In-Memory Data Store
* Multi-AZ with automated failover
* Read Replicas to scale reads and have high availability
* Can scale up, but cannot scale down
* Persistent, Data Durability:
  * Read Only File Feature (AOF),
  * Backup and restore features
* AOF (Append Only File) log can be enabled for recovery of nodes
	* When a node is rebooted and the cache engine starts, the AOF is "replayed"; the result is a warm Redis cache with all of the data intact.
* Caching Strategies
	* **Lazy loading**
		* As the name implies, lazy loading is a caching strategy that loads data into the cache only when necessary.
		* Only requested data is cached. Because most data is never requested, lazy loading avoids filling up the cache with data that isn't requested.
	* **Write-through**
		* The write-through strategy adds data or updates data in the cache whenever data is written to the database.
		* Data in the cache is never stale. Because the data in the cache is updated every time it's written to the database, the data in the cache is always current.

---

<a name="7_3"></a>
## [↖](#top)[↑](#7_2_4)[↓](#7_3_1) Handling Extreme Rates
<!-- toc_start -->
* [Traffic Management](#7_3_1)
* [Compute](#7_3_2)
* [Storage](#7_3_3)
* [Others](#7_3_4)
<!-- toc_end -->

<a name="7_3_1"></a>
### [↖](#7_3)[↑](#7_3)[↓](#7_3_2) Traffic Management

|Service|Rate|Comment
|-|-|-|
Route53|.|Handles extreme rates without problems
CloudFront|100,000 requests/second|.|
ALB|.|Can scale to extreme rates, needs warmup though


<a name="7_3_2"></a>
### [↖](#7_3)[↑](#7_3_1)[↓](#7_3_3) Compute

|Service|Rate|Comment
|-|-|-|
ASG, ECS|.|Scales well, but slowly, requires bootstrap
Fargate|.|Faster than ECS
Lambda|1,000 concurrent executions|Soft limit per region

<a name="7_3_3"></a>
### [↖](#7_3)[↑](#7_3_2)[↓](#7_3_4) Storage

|Service|Rate|Comment
|-|-|-|
|S3|3,500 PUT, 5,550 GET per prefix/s|.|
|RDS, Aurora, ElasticSearch|.|provisioned
|DynamoDB|.|Autoscaling on demand
|EBS|16k IOPS (gp2), 64k IOPS (io1)|.|
|Instance Store|~M IOPS|.
|EFS|.|Performance modes *General*, *Max IO*|
|Redis|<200 nodes|(replica+sharding)
|Memcached|20 nodes|(sharding)
|DAX|10 nodes|(primary + replicas)

<a name="7_3_4"></a>
### [↖](#7_3)[↑](#7_3_3)[↓](#8) Others

|Service|Rate|Comment
|-|-|-|
|SQS, SNS|.|unlimited
|SQS FIFO|3,000 RPS|(with batching)
|Kinesis|1 MB/s in, 2 MB/s out|per shard

---

<a name="8"></a>
# [↖](#top)[↑](#7_3_4)[↓](#8_1) Databases
<a name="8_1"></a>
## [↖](#top)[↑](#8)[↓](#8_1_1) DynamoDB
<!-- toc_start -->
* [Overview](#8_1_1)
* [Basics](#8_1_2)
* [Important features](#8_1_3)
* [Keys and indexes](#8_1_4)
  * [Partion Key](#8_1_4_1)
  * [Partition Key & Sort Key](#8_1_4_2)
* [Secondary indexes](#8_1_5)
  * [Projected attributes](#8_1_5_1)
  * [Local secondary index](#8_1_5_2)
  * [Global secondary index](#8_1_5_3)
* [DynamoDB DAX](#8_1_6)
  * [DAX vs ElastiCache](#8_1_6_1)
* [Solution Architecture](#8_1_7)
  * [Use DDB to index objext in S3](#8_1_7_1)
<!-- toc_end -->

<a name="8_1_1"></a>
### [↖](#8_1)[↑](#8_1)[↓](#8_1_2) Overview
Amazon DynamoDB is a key-value and document database that delivers single-digit millisecond performance at any scale. It's a fully managed, multi-region, multi-active, durable database with built-in security, backup and restore, and in-memory caching for internet-scale applications. DynamoDB can handle more than 10 trillion requests per day and can support peaks of more than 20 million requests per second.
* NoSQL database, fully managed, massive scale (1,000,000 rps)
* Similar to Apache Cassandra (can migrate to DynamoDB)
* No disk space to provision, max object size is 400 KB
* Capacity: *provisioned* (WCU, RCU, & Auto Scaling) or *on-demand*
* Supports CRUD (Create Read Update Delete)
* Read: *eventually* or *strong consistency*
* Supports transactions across multiple tables (ACID support)
* Backups available, point in time recovery
* Integrated with IAM for security
* On AWS: <a href="https://aws.amazon.com/dynamodb/" target="_blank">Service</a> - <a href="https://aws.amazon.com/dynamodb/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/dynamodb/index.html" target="_blank">User Guide</a>

<a name="8_1_2"></a>
### [↖](#8_1)[↑](#8_1_1)[↓](#8_1_3) Basics
* DynamoDB is made of tables
* Each table has a primary key (must be decided at creation time)
* Each table can have an infinite number of items (= rows)
* Each item has attributes (can be added over time – can be null)
* Maximum size of a item is 400KB
* Data types supported are:
  * Scalar Types: String, Number, Binary, Boolean, Null
  * Document Types: List, Map
  * Set Types: String Set, Number Set, Binary Set
* In DynamoDB, you need to know your queries when you design the database
  * Must have right PK, SK & indexes in place
  * Unlike RDS

<a name="8_1_3"></a>
### [↖](#8_1)[↑](#8_1_2)[↓](#8_1_4) Important features
* **TTL**
  * automatically expire row after a specified epoch date
* **DynamoDB Streams**
  * react to changes to DynamoDB tables in real time
  * Can be read by AWS Lambda, EC2...
  * 24 hours retention of data
  * Common pattern:
    * `CRUD on DDB table` -> `Lambda` -> `Amazon ES ElasticSearch`, or `Kinesis`
* **Global Tables** (cross region replication)
	* Amazon DynamoDB global tables provide a fully managed solution for deploying a multiregion, multi-active database, without having to build and maintain your own replication solution. With global tables you can specify the AWS Regions where you want the table to be available. DynamoDB performs all of the necessary tasks to create identical tables in these Regions and propagate ongoing data changes to all of them.
  * Active Active replication, many regions
  * Must enable DynamoDB Streams
  * Useful for low latency, DR purposes
  * Common pattern:
    * Two tables in two regions
    * Replicate all CRUD changes into each other

<a name="8_1_4"></a>
### [↖](#8_1)[↑](#8_1_3)[↓](#8_1_4_1) Keys and indexes

<a name="8_1_4_1"></a>
#### [↖](#8_1)[↑](#8_1_4)[↓](#8_1_4_2) Partion Key
* **Partition key** (PK) is also called **hash attribute** or **primary key**
* Must be decided at creation time
* Must be unique, used for internal hash function (*unordered*)
* Used to retrieve data
* You should design your application for uniform activity across all logical partition keys in the Table and its secondary indexes.
* Example
  * `user_id` for a users table

<a name="8_1_4_2"></a>
#### [↖](#8_1)[↑](#8_1_4_1)[↓](#8_1_5) Partition Key & Sort Key
* **Composite PK**: *index* composed of hashed PK (*unordered*) and Sort Key (SK, *ordered*)
* **Sort key** is also called **range attribute** or **range key**
* Data is grouped by partition key
* Combination of *PK* and *SK* must be unique
  * Different items can have the same *PK*, must have different *SK*
* Example
  * `users-games` table
    * `user_id` for the partition key
    * `game_id` for the sort key
  * good sort key: `timestamp`

<a name="8_1_5"></a>
### [↖](#8_1)[↑](#8_1_4_2)[↓](#8_1_5_1) Secondary indexes
* Associated with exactly one table, from which it obtains its data
* Allows to query or scan data by an *alternate key* (other than PK/SK)
* Only for `read` operations, `write` is not supported.

<a name="8_1_5_1"></a>
#### [↖](#8_1)[↑](#8_1_5)[↓](#8_1_5_2) Projected attributes
* Attributes copied from the base table into an *index*
* Makes them queryable
* Different projection types
	* *KEYS_ONLY* - Only the index and primary keys are projected into the index
	* *INCLUDE* - Only the specified table attributes are projected into the index
	* *ALL* - All of the table attributes are projected into the index

<a name="8_1_5_2"></a>
#### [↖](#8_1)[↑](#8_1_5_1)[↓](#8_1_5_3) Local secondary index
* Uses the *same PK*, but offers different *SK*
* Must be defined at table creation time
* Every partition of a local secondary index is scoped to a base table partition that has the same partition key value
* Local secondary indexes are extra tables that dynamo keeps in the background
* Can choose *eventual consistency* or *strong consistency* at *creation* time
* *Local* as in "co-located on the same partition"
* Can request *not-projected* attributes for query or scan operation
* Consumes read/write throughput from the original table.

<a name="8_1_5_3"></a>
#### [↖](#8_1)[↑](#8_1_5_2)[↓](#8_1_6) Global secondary index
* Uses *different PK* and offers additional *SK* (or none).
* Can be created after the base table has already been created.
* *PK* does not have to be unique (unlike base table)
* Queries on the global index can span all of the data in the base table, across all partitions
* Only support *eventual consistency*
* Have their own provisioned read/write throughput
* Global secondary keys are distributed transactions across multiple partitions
* Global as in "over many partitions"
* Cannot request not-projected attributes for query or scan operation

<a name="8_1_6"></a>
### [↖](#8_1)[↑](#8_1_5_3)[↓](#8_1_6_1) DynamoDB DAX
* DAX = DynamoDB Accelerator
* *Seamless* cache for DynamoDB, no application re-write
* Writes go through DAX to DynamoDB
* Micro second latency for cached reads & queries
* Solves the Hot Key problem
  * too many reads on a particular row can cause throtteling
* 5 minutes TTL for cache by default
* Up to 10 nodes in the cluster
* Multi-AZ
  * 3 nodes minimum recommended for production
* Secure
  * Encryption at rest with KMS, VPC, IAM, CloudTrail...

<a name="8_1_6_1"></a>
#### [↖](#8_1)[↑](#8_1_6)[↓](#8_1_7) DAX vs ElastiCache
* Use DAX if DynamoDB is what the client already interacts with
* Use ElastiCache if you want to speed up a whole computation process
  * E.g. also store compuational results in a cache

<a name="8_1_7"></a>
### [↖](#8_1)[↑](#8_1_6_1)[↓](#8_1_7_1) Solution Architecture
<a name="8_1_7_1"></a>
#### [↖](#8_1)[↑](#8_1_7)[↓](#8_2) Use DDB to index objext in S3
*  `S3` -> `Lambda` to store metadata in -> `DynamoDB`, provide API for object metada
  * Search by date
  * Total storage used by a customer
  * List of all objects with certain attributes
  * Find all objects uploaded within a date range

---

<a name="8_2"></a>
## [↖](#top)[↑](#8_1_7_1)[↓](#8_2_1) ElasticSearch (Core Topic)
<!-- toc_start -->
* [Overview](#8_2_1)
* [ELK](#8_2_2)
* [ElasticSearch Patterns](#8_2_3)
<!-- toc_end -->

<a name="8_2_1"></a>
### [↖](#8_2)[↑](#8_2)[↓](#8_2_2) Overview
Amazon Elasticsearch Service is a fully managed service that makes it easy for you to deploy, secure, and run Elasticsearch cost effectively at scale. You can build, monitor, and troubleshoot your applications using the tools you love, at the scale you need. The service provides support for open source Elasticsearch APIs, managed **Kibana**, integration with Logstash and other AWS services, and built-in alerting and SQL querying. Amazon Elasticsearch Service lets you pay only for what you use – there are no upfront costs or usage requirements. With Amazon Elasticsearch Service, you get the ELK stack you need, without the operational overhead.
* Managed version of Elasticsearch (open source project)
* Runs on servers (not a serverless offering)
* Built-in support for Kibana
* Use cases:
  * Log Analytics
  * Real-time application monitoring
  * Security analysis
  * Full text search
  * Clickstream analytics
  * Indexing
* *Not* a good choice for record *processing*
* May be called Amazon ES at the exam
* On AWS: <a href="https://aws.amazon.com/elasticsearch-service/" target="_blank">Service</a> - <a href="https://aws.amazon.com/elasticsearch-service/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/elasticsearch-service/index.html" target="_blank">User Guide</a>

<a name="8_2_2"></a>
### [↖](#8_2)[↑](#8_2_1)[↓](#8_2_3) ELK
* Elasticsearch
  * Provides search and indexing capabilities
* Logstash
  * Log ingestion mechanism
  * Agent-based
* Kibana
  * Provides real-time dashboards on top of data in ES

<a name="8_2_3"></a>
### [↖](#8_2)[↑](#8_2_2)[↓](#8_3) ElasticSearch Patterns
* `DynamoDB Table` -> `DynamoDB Stream` -> `Lambda` -> `AWS ES`
* `CloudWatch Logs` -> `Subscription Filter` -> `Lambda` -> `AWS ES` (real time)
* `CloudWatch Logs` -> `Subscription Filter` -> `Kinesis Firehose` -> `AWS ES` (near real time)

---

<a name="8_3"></a>
## [↖](#top)[↑](#8_2_3)[↓](#8_3_1) RDS
<!-- toc_start -->
* [Overview](#8_3_1)
* [Security](#8_3_2)
* [RDS Backup](#8_3_3)
* [Multi-AZ deployments](#8_3_4)
* [Replicating RDS](#8_3_5)
* [Etc](#8_3_6)
<!-- toc_end -->
<a name="8_3_1"></a>
### [↖](#8_3)[↑](#8_3)[↓](#8_3_2) Overview
Amazon Relational Database Service (Amazon RDS) makes it easy to set up, operate, and scale a relational database in the cloud. It provides cost-efficient and resizable capacity while automating time-consuming administration tasks such as hardware provisioning, database setup, patching and backups. It frees you to focus on your applications so you can give them the fast performance, high availability, security and compatibility they need

Amazon RDS is available on several database instance types - optimized for memory, performance or I/O - and provides you with six familiar database engines to choose from, including Amazon Aurora, PostgreSQL, MySQL, MariaDB, Oracle Database, and SQL Server. You can use the AWS Database Migration Service to easily migrate or replicate your existing databases to Amazon RDS.
* Set up, operate, and scale a **relational database** in the cloud
  * Provisioning, backups, patching, monitoring
* Supports
	* Amazon Aurora
	* MySQL
	* MariaDB
	* Oracle
	* PostgreSQL
	* MS SQL Server
* Supports *encryption at rest* for all database engines
  * Can only be applied to a *new* instance
  * This could be created from an existing snapshot
* **RDS Events**: get notified via SNS for events (operations, outages...)
* **DB instance**
	* Database environment in the cloud with specified *compute* and *storage* resources
* **Multi-AZ deployments**
	* Provide enhanced availability and durability for DB Instances, making them a natural fit for production database workloads
* **DB subnet group**
	* Collection of subnets that you are designated for the RDS DB Instances in a VPC
* **Maintenance window**
	* Needs to be specified (or defaults to weekly) for maintenance events like scaling and patching
* **DB Parameter group**
	* Acts as a “container” for engine configuration values that can be applied to one or more DB Instances
* **RDS Events**: get notified via SNS for events (operations, outages...)
* On AWS: <a href="https://aws.amazon.com/rds/" target="_blank">Service</a> - <a href="https://aws.amazon.com/rds/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/rds/index.html" target="_blank">User Guide</a>

<a name="8_3_2"></a>
### [↖](#8_3)[↑](#8_3_1)[↓](#8_3_3) Security
* KMS encryption at rest for underlying EBS volumes/snapshots
* Transparent Data Encryption (TDE) for Oracle and SQL Server
* SSL encryption to RDS is possible for all DB (in-flight)
* IAM authentication for MySQL and PostgreSQL
* Authorization still happens within RDS (not in IAM)
* Can copy an un-encrypted RDS snapshot into an encrypted one
* CloudTrail cannot be used to track queries made within RDS

<a name="8_3_3"></a>
### [↖](#8_3)[↑](#8_3_2)[↓](#8_3_4) RDS Backup
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

<a name="8_3_4"></a>
### [↖](#8_3)[↑](#8_3_3)[↓](#8_3_5) Multi-AZ deployments
Amazon RDS Multi-AZ deployments provide enhanced availability for database instances within a single AWS Region.
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

<a name="8_3_5"></a>
### [↖](#8_3)[↑](#8_3_4)[↓](#8_3_6) Replicating RDS
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
  * E.g. use read replica to implement bigger changes on db level, after these have been finished promote to master instance
  * This will break replication
  * Useful for database sharding, could create replicas for each shard

<a name="8_3_6"></a>
### [↖](#8_3)[↑](#8_3_5)[↓](#8_4) Etc
* *DB security groups* are used with DB instances that are not in a VPC and on the EC2-Classic platform.
  * Don't need to specify a destination port number when you create DB security group rules
* *RDS Reserved instances* are available for multi-AZ deployments.
* Cannot SSH into an RDS instance

---

<a name="8_4"></a>
## [↖](#top)[↑](#8_3_6)[↓](#8_4_1) Aurora
<!-- toc_start -->
* [Overview](#8_4_1)
* [High Availability and Read Scaling](#8_4_2)
* [Replicas](#8_4_3)
* [Aurora Serverless](#8_4_4)
* [Global Aurora](#8_4_5)
* [Multi Master](#8_4_6)
<!-- toc_end -->
<a name="8_4_1"></a>
### [↖](#8_4)[↑](#8_4)[↓](#8_4_2) Overview
Amazon Aurora (Aurora) is a fully managed relational database engine that's compatible with MySQL and PostgreSQL. You already know how MySQL and PostgreSQL combine the speed and reliability of high-end commercial databases with the simplicity and cost-effectiveness of open-source databases. The code, tools, and applications you use today with your existing MySQL and PostgreSQL databases can be used with Aurora. With some workloads, Aurora can deliver up to five times the throughput of MySQL and up to three times the throughput of PostgreSQL without requiring changes to most of your existing applications.

Aurora includes a high-performance storage subsystem. Its MySQL- and PostgreSQL-compatible database engines are customized to take advantage of that fast distributed storage. The underlying storage grows automatically as needed. An Aurora cluster volume can grow to a maximum size of 128 tebibytes (TiB). Aurora also automates and standardizes database clustering and replication, which are typically among the most challenging aspects of database configuration and administration.

Aurora is part of the managed database service Amazon Relational Database Service (Amazon RDS). More cloud-native, usually preferred over RDS
* DB Engines: PostgreSQL-compatible & MySQL-compatible
* Storage: **automatically grows** up to 128 TB, 6 copies of data, multi-AZ
* Read Replicas: up to 15 RR
  * **Single reader endpoint** to access them all
* Cross Region RR: entire database is copied (not select tables)
* Load/Offload data directly from/to S3:
  * Efficient use of resources
  * No need for client application to talk to S3
* Backup, Snapshots & Restore: same as RDS
  * Backups are continuous and incremental so you can quickly restore to any point within the backup retention period.
* On AWS: <a href="https://aws.amazon.com/aurora/" target="_blank">Service</a> - <a href="https://aws.amazon.com/aurora/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/CHAP_AuroraOverview.html" target="_blank">User Guide</a>

<a name="8_4_2"></a>
### [↖](#8_4)[↑](#8_4_1)[↓](#8_4_3) High Availability and Read Scaling
* Starts with 10GB, automatically scales in 10GB increments (storage scaling)
* Compute resources scale up to 32vCPUs and 244GB of memory
* 6 copies of your data across 3 AZ:
  * 4 copies out of 6 needed for writes
  * 3 copies out of 6 need for reads
  * Self healing with peer-to-peer replication
    * Storage is striped across 100s of volumes
    * Designed to transparently handle the loss of up to 2 copies without affecting *write*
    * Up to 3 copies without affecting *read*
    * (this is storage only, it still has the DB engine has a single point of failure)
* Automated failover for master in less than 30 seconds
* Master + up to 15 Aurora Read Replicas serve reads
* Support for Cross Region Replication

<a name="8_4_3"></a>
### [↖](#8_4)[↑](#8_4_2)[↓](#8_4_4) Replicas
* Two types
  * Up to 15 *Aurora replicas*
  * Up to 5 *MySQL read replicas*

<a name="8_4_4"></a>
### [↖](#8_4)[↑](#8_4_3)[↓](#8_4_5) Aurora Serverless
* Automated database instantiation and auto-scaling based on actual usage
* Good for infrequent, intermittent or unpredictable workloads
* No capacity planning needed
* Pay per second, can be more cost-effective

<a name="8_4_5"></a>
### [↖](#8_4)[↑](#8_4_4)[↓](#8_4_6) Global Aurora
An Aurora global database consists of one primary AWS Region where your data is mastered, and up to five read-only secondary AWS Regions. You issue write operations directly to the primary DB cluster in the primary AWS Region. Aurora replicates data to the secondary AWS Regions using dedicated infrastructure, with latency typically under a second.
* Aurora Cross Region Read Replicas:
  * Useful for disaster recovery
  * Simple to put in place
* Aurora Global Database (recommended):
  * One primary Region (read/write)
  * Up to 5 secondary (read-only) regions, replication lag is less than 1 second
  * Up to 16 Read Replicas per secondary region
  * Helps for decreasing latency
  * Promoting another region (for disaster recovery) has an RTO of < 1 minute

<a name="8_4_6"></a>
### [↖](#8_4)[↑](#8_4_5)[↓](#9) Multi Master
* Is a new feature of the Aurora MySQL-compatible edition that adds the ability to scale out write performance across multiple Availability Zones.
* In case you want immediate failover for write node (HA)
* *Every* node does R/W
  * Faster than promoting a RR as new master

---

<a name="9"></a>
# [↖](#top)[↑](#8_4_6)[↓](#9_1) Service Communication
<a name="9_1"></a>
## [↖](#top)[↑](#9)[↓](#9_1_1) Step Functions
<!-- toc_start -->
* [Overview](#9_1_1)
* [Tasks](#9_1_2)
* [Integration](#9_1_3)
<!-- toc_end -->
<a name="9_1_1"></a>
### [↖](#9_1)[↑](#9_1)[↓](#9_1_2) Overview
AWS Step Functions is a serverless function orchestrator that makes it easy to sequence AWS Lambda functions and multiple AWS services into business-critical applications. Through its visual interface, you can create and run a series of checkpointed and event-driven workflows that maintain the application state. The output of one step acts as an input to the next. Each step in your application executes in order, as defined by your business logic.

Orchestrating a series of individual serverless applications, managing retries, and debugging failures can be challenging. As your distributed applications become more complex, the complexity of managing them also grows. With its built-in operational controls, Step Functions manages sequencing, error handling, retry logic, and state, removing a significant operational burden from your team.
* Build serverless visual workflow to orchestrate your Lambda functions
* Represent flow as a JSON state machine/YAML via SAM
* Features: sequence, parallel, conditions, timeouts, error handling...
* Can also integrate with EC2, ECS, On-premises servers, API Gateway
* Maximum execution time of 1 year
* Possibility to implement human approval feature
* If you chain Lambda functions using Step Functions, be mindful of the added latency to pass the calls.
* On AWS: <a href="https://aws.amazon.com/step-functions" target="_blank">Service</a> - <a href="https://aws.amazon.com/step-functions/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/step-functions/" target="_blank">User Guide</a>
* See also: <a href="https://www.awsgeek.com/amazon-kinesis-data-streams/" target="_blank">AWS Geek 2020</a>

<a name="9_1_2"></a>
### [↖](#9_1)[↑](#9_1_1)[↓](#9_1_3) Tasks
* Lambda Tasks
  * Invoke a Lambda function
* Activity Tasks
  * Activity worker (HTTP), EC2 Instances, mobile device, on-premises DC
  * They poll the Step functions service
* Service Tasks
  * Connect to a supported AWS service
  * Lambda function, ECS Task, Fargate, DynamoDB, Batch job, SNS topic, SQS queue
* Wait Task
  * To wait for a duration or until a timestamp
* Step Functions does not integrate natively with AWS Mechanical Turk
  * Use SWF to integrate with Mechanical Turk

<a name="9_1_3"></a>
### [↖](#9_1)[↑](#9_1_2)[↓](#9_2) Integration
* API-Gateway - via service proxy
* CloudWatch Evnets - via trigger
* AWS SDK/CLI - via API call

---

<a name="9_2"></a>
## [↖](#top)[↑](#9_1_3)[↓](#9_2_1) Simple Workflow Service (SWF)
<!-- toc_start -->
* [Overview](#9_2_1)
* [Core components](#9_2_2)
<!-- toc_end -->

<a name="9_2_1"></a>
### [↖](#9_2)[↑](#9_2)[↓](#9_2_2) Overview
The Amazon Simple Workflow Service (Amazon SWF) makes it easy to build applications that coordinate work across distributed components. In Amazon SWF, a task represents a logical unit of work that is performed by a component of your application. Coordinating tasks across the application involves managing intertask dependencies, scheduling, and concurrency in accordance with the logical flow of the application. Amazon SWF gives you full control over implementing tasks and coordinating them without worrying about underlying complexities such as tracking their progress and maintaining their state.

When using Amazon SWF, you implement workers to perform tasks. These workers can run either on cloud infrastructure, such as Amazon Elastic Compute Cloud (Amazon EC2), or on your own premises. You can create tasks that are long-running, or that may fail, time out, or require restarts—or that may complete with varying throughput and latency. Amazon SWF stores tasks and assigns them to workers when they are ready, tracks their progress, and maintains their state, including details on their completion. To coordinate tasks, you write a program that gets the latest state of each task from Amazon SWF and uses it to initiate subsequent tasks. Amazon SWF maintains an application's execution state durably so that the application is resilient to failures in individual components. With Amazon SWF, you can implement, deploy, scale, and modify these application components independently.

Amazon SWF offers capabilities to support a variety of application requirements. It is suitable for a range of use cases that require coordination of tasks, including media processing, web application back-ends, business process workflows, and analytics pipelines.
* **Task coordination** and **state management** service
* Code runs on EC2 (not serverless)
* Distributed, scales up and down depending on task
* Works with *on-premises* and *cloud* apps
* Allows for *synchronous* or *asynchronous* processing
* Can contain human events
* Guaranteed order of execution
* Tasks can live up to one year (`31,536,000 seconds`)
* SWF is an older service, it's recommended to use Step Functions for new applications, except:
  * If you need external signals to intervene in the processes
  * If you need child processes that return values to parent processes
  * If you need to use Amazon Mechanical Turk
* On AWS: <a href="https://aws.amazon.com/swf" target="_blank">Service</a> - <a href="https://aws.amazon.com/swf/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/amazonswf/latest/developerguide/swf-welcome.html" target="_blank">User Guide</a>

<a name="9_2_2"></a>
### [↖](#9_2)[↑](#9_2_1)[↓](#9_3) Core components
* **Workflow**
	* A workflow is a set of *activities* that carry out some objective, together with logic that coordinates the activities.
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
    * Schedules *activity tasks*, provides input data to the *activity workers*, processes events that arrive while the *workflow* is in progress, and ultimately ends (or closes) the *workflow* when the objective has been completed.

---

<a name="9_3"></a>
## [↖](#top)[↑](#9_2_2)[↓](#9_3_1) Simple Queue Service (Core Topic)
<!-- toc_start -->
* [Overview](#9_3_1)
* [Core features](#9_3_2)
* [Scenarios](#9_3_3)
* [Limits](#9_3_4)
<!-- toc_end -->

<a name="9_3_1"></a>
### [↖](#9_3)[↑](#9_3)[↓](#9_3_2) Overview
Amazon Simple Queue Service (SQS) is a fully managed message queuing service that enables you to decouple and scale microservices, distributed systems, and serverless applications. SQS eliminates the complexity and overhead associated with managing and operating message oriented middleware, and empowers developers to focus on differentiating work. Using SQS, you can send, store, and receive messages between software components at any volume, without losing messages or requiring other services to be available. Get started with SQS in minutes using the AWS console, Command Line Interface or SDK of your choice, and three simple commands.

SQS offers two types of message queues. Standard queues offer maximum throughput, best-effort ordering, and at-least-once delivery. SQS FIFO queues are designed to guarantee that messages are processed exactly once, in the exact order that they are sent.
* Oldest AWS service
* Scalable **message queue** service
* Allows *loose coupling* and *asynchronous processing*
* **Pull** from *SQS* (*Push* to *SNS*)
* Can handle extreme scale, no provisioning required
* PCI compliant
* Protection against data loss on application failure
* Message size of max 256 KB
  * Use a pointer to S3 for large messages
  * Up to 2GB with Extended Client Library
* Can be read from EC2 (optional ASG), Lambda (event source mapping)
* On AWS: <a href="https://aws.amazon.com/sqs" target="_blank">Service</a> - <a href="https://aws.amazon.com/sqs/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/welcome.html" target="_blank">User Guide</a>

<a name="9_3_2"></a>
### [↖](#9_3)[↑](#9_3_1)[↓](#9_3_3) Core features
* Redundant infrastructure
* Multiple readers/writers at the same time
* Access control via *SQS policies* (similar to *IAM*)
* **Standard queue**
  * Default queue
	* Guarantees message delivery *at least once*
	* *No guarantee on message order*
	* No guarantee on not receiving duplicates (app has to deal with it -> implement *idempotent* processing)
* **FIFO queue**
	* Guaranteed order
	* Exactly-once processing
	* *Message groups* - multiple ordered message groups within a single queue
	* Name ends in `.fifo`
  * 300 messages/s without batching, 3000/s with batching
* **Delay queues**
	* Controls when a message becomes available
	* Between 0s and 15min, default 0s
* **Visibility timeout**
	* Controls when a polled message becomes visible again
	* Configurable and extendable for individual messages
	* Between 0s and 12h, default 30s
  * Recommendation: 6 times the timeout of the consumer (e.g. Lambda)
* **Message retention period**
	* Amount of time a message will live in the queue if it's not deleted
	* Between 1min and 14d, default 4d
* **In flight message**
	* Sent to a client but have not yet been deleted or have not yet reached the end of their visibility window
* **Deadletter queue**
	* Queue that other queues can send messages to when these were not successfully processed.
  * Configure on SQS-queue level
  * If client is Lambda: Can also use Lambda Destination for failure
* **Receive message wait time**
	* Value >0 enables *long polling*
	* Between 0s and 20s, default 0s (*short polling*)

<a name="9_3_3"></a>
### [↖](#9_3)[↑](#9_3_2)[↓](#9_3_4) Scenarios
* Lambda – Event Source Mapping - SQS & SQS FIFO
  * `Lambda Event Source Mapping` -> (poll batch) -> `SQS` -> (return batch) -> `Lambda Event Source Mapping` -> (invoke with batch) -> `Lambda function`
* Request/Response queue (async)
  * `Client` push -> `SQS Request Queue` -> `Worker` poll -> (process) -> push -> `SQS Response Queue` -> `Worker` poll
    * Decoupling
    * Fault-Tolerance
    * Load Balancing

<a name="9_3_4"></a>
### [↖](#9_3)[↑](#9_3_3)[↓](#9_4) Limits
.|.
-|-
Max message size|256KB (2GB with Extended Client Library)
Max inflight messages|120,000

---

<a name="9_4"></a>
## [↖](#top)[↑](#9_3_4)[↓](#9_4_1) Amazon MQ
<!-- toc_start -->
* [Overview](#9_4_1)
<!-- toc_end -->

<a name="9_4_1"></a>
### [↖](#9_4)[↑](#9_4)[↓](#9_5) Overview
Amazon MQ is a managed message broker service for Apache ActiveMQ and RabbitMQ that makes it easy to set up and operate message brokers on AWS. Amazon MQ reduces your operational responsibilities by managing the provisioning, setup, and maintenance of message brokers for you. Because Amazon MQ connects to your current applications with industry-standard APIs and protocols, you can easily migrate to AWS without having to rewrite code.
* Amazon MQ = managed Apache ActiveMQ
  * Doesn’t “scale” as much as SQS/SNS
  * Runs on a dedicated machine, can run in HA with failover
  * Has both queue feature (~SQS) and topic features (~SNS)
* SQS, SNS are “cloud-native” services, and they’re using proprietary protocols from AWS.
* Traditional applications running from on-premises may use open protocols such as: MQTT, AMQP, STOMP, Openwire, WSS
* When migrating to the cloud, instead of re-engineering the application to use SQS and SNS, we can use Amazon MQ
  * IBM MQ, TIBCO EMS, Rabbit MQ, and Apache ActiveMQ can be migrated to Amazon MQ
* On AWS: <a href="https://aws.amazon.com/amazon-mq" target="_blank">Service</a> - <a href="https://aws.amazon.com/amazon-mq/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/amazon-mq/index.html" target="_blank">User Guide</a>

---

<a name="9_5"></a>
## [↖](#top)[↑](#9_4_1)[↓](#9_5_1) Simple Notification Service (Core Topic)
<!-- toc_start -->
* [Overview](#9_5_1)
* [Scenarios](#9_5_2)
<!-- toc_end -->

<a name="9_5_1"></a>
### [↖](#9_5)[↑](#9_5)[↓](#9_5_2) Overview
Amazon Simple Notification Service (Amazon SNS) is a fully managed messaging service for both application-to-application (A2A) and application-to-person (A2P) communication.

The A2A pub/sub functionality provides topics for high-throughput, push-based, many-to-many messaging between distributed systems, microservices, and event-driven serverless applications. Using Amazon SNS topics, your publisher systems can fanout messages to a large number of subscriber systems including Amazon SQS queues, AWS Lambda functions and HTTPS endpoints, for parallel processing, and Amazon Kinesis Data Firehose. The A2P functionality enables you to send messages to users at scale via SMS, mobile push, and email.
* The *event producer* (publisher) only sends message to one SNS topic
* As many *event receivers* (subscriptions) as we want to listen to the SNS topic notifications
* Each subscriber to the topic will get all the messages (note: new feature to filter messages)
* Up to 10,000,000 subscriptions per topic
* 100,000 topics limit
* Subscribers can be:
  * QS
  * TTP/HTTPS (with delivery retries – how many times)
  * Lambda
  * Emails
  * SMS messages
  * Mobile Notifications (**SNS Mobile Push** - Android, Apple, Fire OS, Windows...)
* On AWS: <a href="https://aws.amazon.com/sns" target="_blank">Service</a> - <a href="https://aws.amazon.com/sns/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/sns" target="_blank">User Guide</a>

<a name="9_5_2"></a>
### [↖](#9_5)[↑](#9_5_1)[↓](#10) Scenarios
* SNS + SQS: Fan Out
  * `Producer` -> `SNS` -> per consumer: `SQS` - `Consumer`
    * Push once in SNS, receive in many SQS queues
    * Fully decoupled, no data loss, ability to add receivers of data later
    * SQS allows for delayed processing, retries of work
    * May have many workers on one queue and one worker on the other queue

---

<a name="10"></a>
# [↖](#top)[↑](#9_5_2)[↓](#10_1) Data Engineering

<a name="10_1"></a>
## [↖](#top)[↑](#10)[↓](#10_1_1) Kinesis (Core Topic)
<!-- toc_start -->
* [Overview](#10_1_1)
* [Kinesis Data Streams](#10_1_2)
  * [Overview](#10_1_2_1)
  * [Kinesis Streams Shards](#10_1_2_2)
  * [Getting Data in and out](#10_1_2_3)
  * [Limits](#10_1_2_4)
* [Kinesis Data Firehose](#10_1_3)
  * [Overview](#10_1_3_1)
  * [Firehose Buffer Sizing](#10_1_3_2)
* [Data Streams vs Firehose](#10_1_4)
* [Kinesis Data Analytics](#10_1_5)
* [Streaming Architectures](#10_1_6)
  * [Full Data Engineering Pipeline](#10_1_6_1)
  * [3000 messages of 1KB/sec](#10_1_6_2)
  * [Comparison](#10_1_6_3)
<!-- toc_end -->
<a name="10_1_1"></a>
### [↖](#10_1)[↑](#10_1)[↓](#10_1_2) Overview
Amazon Kinesis makes it easy to collect, process, and analyze real-time, streaming data so you can get timely insights and react quickly to new information. Amazon Kinesis offers key capabilities to cost-effectively process streaming data at any scale, along with the flexibility to choose the tools that best suit the requirements of your application. With Amazon Kinesis, you can ingest real-time data such as video, audio, application logs, website clickstreams, and IoT telemetry data for machine learning, analytics, and other applications. Amazon Kinesis enables you to process and analyze data as it arrives and respond instantly instead of having to wait until all your data is collected before the processing can begin.
* Kinesis is a managed “data streaming” service
* Great for application logs, metrics, IoT, clickstreams
* Great for “real-time” big data
* Great for streaming processing frameworks (Spark, NiFi, etc...)
* Data is automatically replicated synchronously to 3 AZ
* **Kinesis**
  * **Kinesis Streams**: low latency streaming ingest at scale
  * **Kinesis Analytics**: perform real-time analytics on streams using SQL
  * **Kinesis Firehose**: load streams into S3, Redshift, ElasticSearch & Splunk
* High level picture
  * -> `data producers`(Click streams, IoT, metrics & logs, ...)
  * -> `Kinesis Streams`
  * -> `Kinesis Analytics`
  * -> `Kinesis Firehose`
  * -> `storage` (S3, Redshift, splunk, Elasticsearch, ...)
* On AWS: <a href="https://aws.amazon.com/kinesis" target="_blank">Service</a>

<a name="10_1_2"></a>
### [↖](#10_1)[↑](#10_1_1)[↓](#10_1_2_1) Kinesis Data Streams
<a name="10_1_2_1"></a>
#### [↖](#10_1)[↑](#10_1_2)[↓](#10_1_2_2) Overview
Amazon Kinesis Data Streams (KDS) is a massively scalable and durable real-time data streaming service. KDS can continuously capture gigabytes of data per second from hundreds of thousands of sources such as website clickstreams, database event streams, financial transactions, social media feeds, IT logs, and location-tracking events. The data collected is available in milliseconds to enable real-time analytics use cases such as real-time dashboards, real-time anomaly detection, dynamic pricing, and more.
* Streams are divided in ordered *shards*/partitions
* Data retention is 24 hours by default, can go up to 365 days (previously: 7 days)
* Ability to reprocess/replay data
* Multiple applications can consume the same stream
  * This is not possible with e.g. SQS
* Real-time processing with scale of throughput
  * The more shards, the more scale
* Once data is inserted in Kinesis, it can’t be deleted (immutability)
  * Another difference to SQS
* On AWS: <a href="https://aws.amazon.com/kinesis/data-streams" target="_blank">Service</a> - <a href="https://aws.amazon.com/kinesis/data-streams/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/kinesis/index.html" target="_blank">User Guide</a>
* See also: <a href="https://www.awsgeek.com/amazon-kinesis-data-streams/" target="_blank">AWS Geek 2020</a>

<a name="10_1_2_2"></a>
#### [↖](#10_1)[↑](#10_1_2_1)[↓](#10_1_2_3) Kinesis Streams Shards
* One stream is made of many different shards
* Billing is per shard provisioned, can have as many shards as you want
* Batching available or per message calls.
* The number of shards can evolve over time (reshard/merge)
* Records are ordered per Shard

<a name="10_1_2_3"></a>
#### [↖](#10_1)[↑](#10_1_2_2)[↓](#10_1_2_4) Getting Data in and out
* **Producers**
  * AWS SDK
    * Simple producer
  * Kinesis Producer Library (KPL):
    * Batch, compression, retries
    * C++, Java
    * Best choice when writing own application
  * Kinesis Agent (based on KPL)
    * Monitor log files and sends them to Kinesis directly
    * Can write to Kinesis Data Streams AND Kinesis Data Firehose
    * Best choice when e.g. getting data out of EC2
* **Producers**
  * AWS SDK:
    * Simple consumer
  * Lambda: (through Event source mapping)
  * Kinesis Client Library (KCL):
    * checkpointing, coordinated reads

<a name="10_1_2_4"></a>
#### [↖](#10_1)[↑](#10_1_2_3)[↓](#10_1_3) Limits

.|.
-|-
Producer|1MB/s or 1000 messages/s at write PER SHARD<br/>“ProvisionedThroughputException” otherwise
Consumer Classic|2MB/s at read PER SHARD across all consumers<br/>5 API calls per second PER SHARD across all consumers
Consumer Enhanced Fan-Out|2MB/s at read PER SHARD, PER ENHANCED CONSUMER<br/>No API calls needed (push model)
Data Retention|24 hours data retention by default<br/>Can be extended to 365 (was: 7) days

<a name="10_1_3"></a>
### [↖](#10_1)[↑](#10_1_2_4)[↓](#10_1_3_1) Kinesis Data Firehose

<a name="10_1_3_1"></a>
#### [↖](#10_1)[↑](#10_1_3)[↓](#10_1_3_2) Overview
Amazon Kinesis Data Firehose is the easiest way to reliably load streaming data into data lakes, data stores, and analytics services. It can capture, transform, and deliver streaming data to Amazon S3, Amazon Redshift, Amazon Elasticsearch Service, generic HTTP endpoints, and service providers like Datadog, New Relic, MongoDB, and Splunk. It is a fully managed service that automatically scales to match the throughput of your data and requires no ongoing administration. It can also batch, compress, transform, and encrypt your data streams before loading, minimizing the amount of storage used and increasing security.

You can easily create a Firehose delivery stream from the AWS Management Console, configure it with a few clicks, and start ingesting streaming data from hundreds of thousands of data sources to your specified destinations. You can also configure your data streams to automatically convert the incoming data to open and standards based formats like Apache Parquet and Apache ORC before the data is delivered.

With Amazon Kinesis Data Firehose, there is no minimum fee or setup cost. You pay for the amount of data that you transmit through the service, if applicable, for converting data formats, and for Amazon VPC delivery and data transfer.
* Fully Managed Service, no administration, automatic scaling, serverless
* Near Real Time (60 seconds latency minimum for non full batches)
* Load data into Redshift/Amazon S3/ElasticSearch/Splunk
* Supports many data formats, conversions, transformations, compression
* Pay only for the amount of data going through Firehose
* High level picture
  * -> `data producers`(SDK/KPL, Kinesis Agent, Kinesis Data Streams, CloudWatch Logs and Events, IoT rules actions)
  * -> `Kinesis Firehose`
    * Can optinally transform data with Lambda
      * Several blueprint templates available
      * Can upload transfromation failures into bucket
    * Can optionally upload source records into bucket
    * Can optionally upload delivery failures into bucket
  * -> `storage` (S3, Redshift, splunk, Elasticsearch) <- these are only destinations available for Firehose!
* On AWS: <a href="https://aws.amazon.com/kinesis/data-firehose" target="_blank">Service</a> - <a href="https://aws.amazon.com/kinesis/data-firehose/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/kinesis/index.html" target="_blank">User Guide</a>

<a name="10_1_3_2"></a>
#### [↖](#10_1)[↑](#10_1_3_1)[↓](#10_1_4) Firehose Buffer Sizing
* Firehose accumulates records in a buffer
* The buffer is flushed based on time and size rules
* **Buffer Size** (eg 32MB): if that buffer size is reached, it’s flushed
* **Buffer Time** (eg 1 minute): if that time is reached, it’s flushed
* Firehose can automatically increase the buffer size to increase throughput
* High throughput => Buffer Size will be hit
* Low throughput => Buffer Time will be hit
* Firehose is near real-time, if real-time flush from Kinesis Data Streams to S3 is needed, use Lambda
  * Will costs more

<a name="10_1_4"></a>
### [↖](#10_1)[↑](#10_1_3_2)[↓](#10_1_5) Data Streams vs Firehose
* **Data Streams**
  * Going to write custom code (producer/consumer)
  * Real time (~200 ms latency for *classic*, ~70 ms latency for *enhanced fan-out*)
  * Must manage scaling (shard splitting/merging)
  * Data Storage for 1 to 7 days, replay capability, multiple consumers
  * Use with Lambda to insert data in real-time to ElasticSearch (for example)
* **Firehose**
  * Near real time only (lowest buffer time is 1 minute)
  * Fully managed, send to S3, Splunk, Redshift, ElasticSearch
  * Serverless data transformations with Lambda
  * Automated Scaling
  * No data storage

<a name="10_1_5"></a>
### [↖](#10_1)[↑](#10_1_4)[↓](#10_1_6) Kinesis Data Analytics
Amazon Kinesis Data Analytics is the easiest way to transform and analyze streaming data in real time with Apache Flink. Apache Flink is an open source framework and engine for processing data streams. Amazon Kinesis Data Analytics reduces the complexity of building, managing, and integrating Apache Flink applications with other AWS services.

Amazon Kinesis Data Analytics takes care of everything required to run streaming applications continuously, and scales automatically to match the volume and throughput of your incoming data. With Amazon Kinesis Data Analytics, there are no servers to manage, no minimum fee or setup cost, and you only pay for the resources your streaming applications consume.
* Use cases
  * Streaming ETL: select columns, make simple transformations, on streaming data
  * Continuous metric generation: live leaderboard for a mobile game
  * Responsive analytics: look for certain criteria and build alerting (filtering)
* Features
  * Pay only for resources consumed (but it’s not cheap)
  * Serverless; scales automatically
  * Use IAM permissions to access streaming source and destination(s)
  * SQL or Flink to write the computation
  * Schema discovery
  * Lambda can be used for pre-processing
* On AWS: <a href="https://aws.amazon.com/kinesis/data-analytics" target="_blank">Service</a> - <a href="https://aws.amazon.com/kinesis/data-analytics/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/kinesis/index.html" target="_blank">User Guide</a>

<a name="10_1_6"></a>
### [↖](#10_1)[↑](#10_1_5)[↓](#10_1_6_1) Streaming Architectures

<a name="10_1_6_1"></a>
#### [↖](#10_1)[↑](#10_1_6)[↓](#10_1_6_2) Full Data Engineering Pipeline
* 'Classic Kinesis': (producer) -> Data Streams -> Data Analytics -> Data Firehose -> (storage)
  * Can also produce into Data Firehose
  * Can also use Data Firehose as an input to Data Analytics
  * Can also use Data Streams as an output of Data Analytics

<a name="10_1_6_2"></a>
#### [↖](#10_1)[↑](#10_1_6_1)[↓](#10_1_6_3) 3000 messages of 1KB/sec
* Option 1
  * Kinesis Data Streams -> Lambda
  * Costs
    * 3 shards: 3MB/s in
    * 3 * $0.015/hr = $32.4/mth
    * Must use Data Firehose to output to S3
* Option 2
  * DynamoDB Streams -> Lambda
    * 3000 WCU = 3 MB/s
    * = $1,450.90/month
    * Storage in DynamoDB

<a name="10_1_6_3"></a>
#### [↖](#10_1)[↑](#10_1_6_2)[↓](#10_2) Comparison

.|Kinesis Data Streams|SQS|SQS FIFO|SNS|DynamoDB|S3
-|-|-|-|-|-|-
**Data**|Immutable|Immutable|Immutable|Immutable|Mutable|Mutable
**Retention**|1-7 days,export to S3 using KDF|1-14 days|1-14 days|No retention|Infinite or can implement TTL|Infinite, can setup lifecycle policies
**Ordering**|Per shard|No ordering|Per group-id|No ordering|No ordering|No ordering
**Scalability**|Provision shards|Soft limit|300 msg/s Or 3000 if batch|Soft limit|WCU & RCU On-demand|Infinite, 3500 PUT, 5500 GET/prefix
**Readers**|EC2, Lambda, KDF, KDA, KCL (checkpoint)|EC2, Lambda|EC2, Lambda|HTTP, Lambda, Email, SQS...|DynamoDB Streams|SDK, S3 Events
**Latency**|KDS (200 ms),KDF (1 min)|Low (10-100ms)|Low (10-100ms)|Low (10-100ms)|Low (10-100ms)|Low (10-100ms)

---

<a name="10_2"></a>
## [↖](#top)[↑](#10_1_6_3)[↓](#10_2_1) AWS Batch
<!-- toc_start -->
* [Overview](#10_2_1)
* [Batch vs Lambda](#10_2_2)
* [Compute Environments](#10_2_3)
* [Multi-Node Mode](#10_2_4)
<!-- toc_end -->

<a name="10_2_1"></a>
### [↖](#10_2)[↑](#10_2)[↓](#10_2_2) Overview
AWS Batch enables developers, scientists, and engineers to easily and efficiently run hundreds of thousands of batch computing jobs on AWS. AWS Batch dynamically provisions the optimal quantity and type of compute resources (e.g., CPU or memory optimized instances) based on the volume and specific resource requirements of the batch jobs submitted. With AWS Batch, there is no need to install and manage batch computing software or server clusters that you use to run your jobs, allowing you to focus on analyzing results and solving problems. AWS Batch plans, schedules, and executes your batch computing workloads across the full range of AWS compute services and features, such as AWS Fargate, Amazon EC2 and Spot Instances.

There is no additional charge for AWS Batch. You only pay for the AWS resources (e.g. EC2 instances or Fargate jobs) you create to store and run your batch jobs.
* Run batch jobs as Docker images (ECS)
* Dynamic provisioning of the instances (EC2 & Spot Instances) – in VPC
* Optimal quantity and type based on volume and requirements
* No need to manage clusters (but still runs on instances)
  * You just pay for the underlying EC2 instances
* Example: batch process of images, running thousands of concurrent jobs
* Schedule Batch Jobs using CloudWatch Events
* Orchestrate Batch Jobs using AWS Step Functions
* On AWS
  * <a href="https://aws.amazon.com/batch/" target="_blank">Service</a> - <a href="https://aws.amazon.com/batch/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/batch/" target="_blank">User Guide</a>

<a name="10_2_2"></a>
### [↖](#10_2)[↑](#10_2_1)[↓](#10_2_3) Batch vs Lambda
* Lambda:
  * Time limit
  * Limited runtimes
  * Limited temporary disk space
  * Serverless
* Batch:
  * No time limit
  * Any runtime as long as it’s package as a Docker image
  * Rely on EBS/instance store for disk space
  * Relies on EC2 (can be managed by AWS)

<a name="10_2_3"></a>
### [↖](#10_2)[↑](#10_2_2)[↓](#10_2_4) Compute Environments
* Managed Compute Environment
  * AWS Batch managed the capacity and instance types within the environment
  * You can choose On-Demand or Spot Instances
  * You can set a maximum price for Spot Instances
  * Launched within your own VPC
  * If you launch within your own private subnet, make sure it has access to the ECS service
  * Either using a NAT gateway/instance or using VPC Endpoints for ECS
* Unmanaged Compute Environment
  * You control and manage instance configuration, provisioning and scaling

<a name="10_2_4"></a>
### [↖](#10_2)[↑](#10_2_3)[↓](#10_3) Multi-Node Mode
* Large scale, good for HPC (high performance computing)
* Leverages multiple EC2/ECS instances at the same time
* Good for tightly coupled workloads
* Represents a single job, and specified how many nodes to create for the job
* 1 main node, and many child node.
* Does not work with Spot Instances!
* Works better if your EC2 launch mode is a placement group ”cluster”

---

<a name="10_3"></a>
## [↖](#top)[↑](#10_2_4)[↓](#10_3_1) Amazon EMR
<!-- toc_start -->
* [Overview](#10_3_1)
* [Node types & purchasing](#10_3_2)
* [Instance Configuration](#10_3_3)
<!-- toc_end -->
<a name="10_3_1"></a>
### [↖](#10_3)[↑](#10_3)[↓](#10_3_2) Overview
Amazon EMR is the industry-leading cloud big data platform for processing vast amounts of data using open source tools such as Apache Spark, Apache Hive, Apache HBase, Apache Flink, Apache Hudi, and Presto. Amazon EMR makes it easy to set up, operate, and scale your big data environments by automating time-consuming tasks like provisioning capacity and tuning clusters. With EMR you can run petabyte-scale analysis at less than half of the cost of traditional on-premises solutions and over 3x faster than standard Apache Spark. You can run workloads on Amazon EC2 instances, on Amazon Elastic Kubernetes Service (EKS) clusters, or on-premises using EMR on AWS Outposts.
* EMR stands for “Elastic MapReduce”
* EMR helps creating Hadoop clusters (Big Data) to analyze and process vast amount of data
	* Can **not** analyze real-time data (-> Kinesis)
* The clusters can be made of hundreds of EC2 instances
* Also supports Apache Spark, HBase, Presto, Flink...
* EMR takes care of all the provisioning and configuration of EC2
* Auto-scaling with CloudWatch
* Use cases
  * Data processing, machine learning, web indexing, big data...
* Runs on EC2 in your VPC/single AZ
* Temporary storage on instances, permanent on S3
  * Special file system for S3: EMRFS
* On AWS
  * <a href="https://aws.amazon.com/emr/" target="_blank">Service</a> - <a href="https://aws.amazon.com/emr/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/emr/index.html" target="_blank">User Guide</a>

<a name="10_3_2"></a>
### [↖](#10_3)[↑](#10_3_1)[↓](#10_3_3) Node types & purchasing
* **Master Node**: Manage the cluster, coordinate, manage health
* **Core Node**: Run tasks and store data
* **Task Node** (optional): Just to run tasks.
	* Spot instances can be used here
* Purchasing options:
  * On-demand: reliable, predictable, won’t be terminated
  * Reserved (min 1 year): cost savings (EMR will automatically use if available)
  * Spot Instances: cheaper, can be terminated, less reliable
* Can have long-running cluster, or transient (temporary) cluster
* One big cluster vs many smaller ones? Long running vs transient?

<a name="10_3_3"></a>
### [↖](#10_3)[↑](#10_3_2)[↓](#10_4) Instance Configuration
* **Uniform instance groups**
  * Select a single instance type and purchasing option for each node (has auto-scaling)
* **Instance fleet**
  * Select target capacity, mix instance types and purchasing options (no Auto Scaling)

---

<a name="10_4"></a>
## [↖](#top)[↑](#10_3_3)[↓](#10_5) Running Jobs on AWS

.|.
-|-
EC2 instance|With long-running cronjob
Reactive workflow|CloudWatch Events/S3 Events/API Gateway/SQS/SNS/... -> Lambda
Fargate|CloudWatch Events -> Lambda
CloudWatch Events and Lambda (scheduled)|Cloudwatch Events -> cron schedule -> Lambda
AWS Batch|CloudWatch Events -> Batch
EMR|.

---

<a name="10_5"></a>
## [↖](#top)[↑](#10_4)[↓](#10_5_1) Amazon Redshift
<!-- toc_start -->
* [Overview](#10_5_1)
* [How it works](#10_5_2)
* [Snapshots and DR](#10_5_3)
* [Redshift Spectrum](#10_5_4)
<!-- toc_end -->
<a name="10_5_1"></a>
### [↖](#10_5)[↑](#10_5)[↓](#10_5_2) Overview
No other data warehouse makes it as easy to gain new insights from all your data. With Redshift, you can query and combine exabytes of structured and semi-structured data across your data warehouse, operational database, and data lake using standard SQL. Redshift lets you easily save the results of your queries back to your S3 data lake using open formats, like Apache Parquet, so that you can do additional analytics from other analytics services like Amazon EMR, Amazon Athena, and Amazon SageMaker.
* Redshift is based on PostgreSQL (analytics and data warehousing)
  * User for OLAP (Online Analytical Processing)
  * Not used for OLTP (Online Transaction Processing) -> RDS
* 10x better performance than other data warehouses, scale to PBs of data
* Columnar storage of data (instead of row-based)
  * Very efficient for e.g. sum or average of a column
* Massively Parallel Query Execution (MPP)
* Pay as you go, based on the instances provisioned
  * Not a great choice for sporadic usage -> Athena
* Has a SQL interface for performing queries
* BI tools such as AWS Quicksight or Tableau integrate with it
* On AWS
  * <a href="https://aws.amazon.com/redshift/" target="_blank">Service</a> - <a href="https://aws.amazon.com/redshift/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/redshift/index.html" target="_blank">User Guide</a>

<a name="10_5_2"></a>
### [↖](#10_5)[↑](#10_5_1)[↓](#10_5_3) How it works
* Data is loaded from S3, Kinesis Firehose, DynamoDB, Database Migration Service, ...
* From 1 node to 128 nodes, up to 160 GB of space per node
* Can provision multiple nodes, but it’s not Multi-AZ
* **Leader node**: for query planning, results aggregation
* **Compute node**: for performing the queries, send results to back leader
* Backup & Restore, Security VPC/IAM/KMS, Monitoring
* Redshift Enhanced VPC Routing: COPY/UNLOAD goes through VPC

<a name="10_5_3"></a>
### [↖](#10_5)[↑](#10_5_2)[↓](#10_5_4) Snapshots and DR
* Snapshots are point-in-time backups of a cluster, stored internally in S3
* Snapshots are incremental (only what has changed is saved)
* You can restore a snapshot into a new cluster
* Automated: every 8 hours, every 5 GB, or on a schedule. Set retention
* Manual: snapshot is retained until you delete it
* You can configure Amazon Redshift to automatically copy snapshots (automated or manual) to another AWS Region
  * Great for DR

<a name="10_5_4"></a>
### [↖](#10_5)[↑](#10_5_3)[↓](#10_6) Redshift Spectrum
Using Amazon Redshift Spectrum, you can efficiently query and retrieve structured and semistructured data from files in Amazon S3 without having to load the data into Amazon Redshift tables. Redshift Spectrum queries employ massive parallelism to execute very fast against large datasets. Much of the processing occurs in the Redshift Spectrum layer, and most of the data remains in Amazon S3. Multiple clusters can concurrently query the same dataset in Amazon S3 without the need to make copies of the data for each cluster.
* Query data that is already in S3 without loading it
* Must have a Redshift cluster available to start the query
* The query is then submitted to thousands of Redshift Spectrum nodes
  * Nodes are shared across customers

---

<a name="10_6"></a>
## [↖](#top)[↑](#10_5_4)[↓](#10_6_1) Athena
<!-- toc_start -->
* [Overview](#10_6_1)
<!-- toc_end -->
<a name="10_6_1"></a>
### [↖](#10_6)[↑](#10_6)[↓](#10_7) Overview
Amazon Athena is an interactive query service that makes it easy to analyze data in Amazon S3 using standard SQL. Athena is serverless, so there is no infrastructure to manage, and you pay only for the queries that you run.

Athena is easy to use. Simply point to your data in Amazon S3, define the schema, and start querying using standard SQL. Most results are delivered within seconds. With Athena, there’s no need for complex ETL jobs to prepare your data for analysis. This makes it easy for anyone with SQL skills to quickly analyze large-scale datasets.

Athena is out-of-the-box integrated with AWS Glue Data Catalog, allowing you to create a unified metadata repository across various services, crawl data sources to discover schemas and populate your Catalog with new and modified table and partition definitions, and maintain schema versioning.
* Serverless SQL queries on top of your data in S3, pay per query, output to S3
* Supports CSV, JSON, Parquet, ORC
* Queries are logged in CloudTrail (which can be chained with CloudWatch logs)
* Great for sporadic queries
* Ready-to-use queries for VPC Flow Logs, CloudTrail, ALB Access Logs, Cost and Usage reports (billing), etc...
* On AWS
  * <a href="https://aws.amazon.com/athena/" target="_blank">Service</a> - <a href="https://aws.amazon.com/athena/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/athena/" target="_blank">User Guide</a>

---

<a name="10_7"></a>
## [↖](#top)[↑](#10_6_1)[↓](#10_7_1) QuickSight
<!-- toc_start -->
* [Overview](#10_7_1)
<!-- toc_end -->
<a name="10_7_1"></a>
### [↖](#10_7)[↑](#10_7)[↓](#10_8) Overview
Amazon QuickSight is a fast business analytics service to build visualizations, perform ad hoc analysis, and quickly get business insights from your data. Amazon QuickSight seamlessly discovers AWS data sources, enables organizations to scale to hundreds of thousands of users, and delivers fast and responsive query performance by using a robust in-memory engine (SPICE).
* Business Intelligence tool for data visualization, creating dashboards, ...
* Integrates with Athena, Redshift, EMR, RDS, ...
* On AWS
  * <a href="https://aws.amazon.com/quicksight/" target="_blank">Service</a> - <a href="https://aws.amazon.com/quicksight/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/quicksight/" target="_blank">User Guide</a>

---

<a name="10_8"></a>
## [↖](#top)[↑](#10_7_1)[↓](#10_9) AWS Data Pipeline
AWS Data Pipeline is a web service that helps you reliably process and move data between different AWS compute and storage services, as well as on-premises data sources, at specified intervals. With AWS Data Pipeline, you can regularly access your data where it’s stored, transform and process it at scale, and efficiently transfer the results to AWS services such as Amazon S3, Amazon RDS, Amazon DynamoDB, and Amazon EMR.

AWS Data Pipeline helps you easily create complex data processing workloads that are fault tolerant, repeatable, and highly available. You don’t have to worry about ensuring resource availability, managing inter-task dependencies, retrying transient failures or timeouts in individual tasks, or creating a failure notification system. AWS Data Pipeline also allows you to move and process data that was previously locked up in on-premises data silos.

* On AWS: <a href="https://aws.amazon.com/datapipeline/" target="_blank">Service</a> - <a href="https://aws.amazon.com/datapipeline/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/data-pipeline/index.html" target="_blank">User Guide</a>

---

<a name="10_9"></a>
## [↖](#top)[↑](#10_8)[↓](#10_9_1) Big Data Architecture
<!-- toc_start -->
* [Analytics Layer](#10_9_1)
* [Big Data Ingestion](#10_9_2)
* [Comparison of warehousing technologies](#10_9_3)
<!-- toc_end -->
<a name="10_9_1"></a>
### [↖](#10_9)[↑](#10_9)[↓](#10_9_2) Analytics Layer
* Amazon EMR
* Redshift/Redshift Spectrum
* Athena
* QuickSight (visualization)

<a name="10_9_2"></a>
### [↖](#10_9)[↑](#10_9_1)[↓](#10_9_3) Big Data Ingestion
* Kinesis Data Streams
* Kinesis Firehose (every 1 minute)
* S3
* ...
* Athena
* S3
* QuickSight

<a name="10_9_3"></a>
### [↖](#10_9)[↑](#10_9_2)[↓](#11) Comparison of warehousing technologies
* EMR
  * Need to use Big Data tools such as Apache Hive, Spark
  * One long-running cluster, many jobs, with auto-scaling, or one cluster per job?
  * Purchasing options – Spot, On Demand, Reserved Instances
  * Can access data in DynamoDB and/or S3
  * Scratch data on EBS disks (HDFS) and long term storage in S3 (EMRFS)
* Athena
  * Simple queries and aggregations, data must live in S3
  * Serverless, simple SQL queries, out-of-the-box queries for many services (cost & billing..)
  * Audit queries through CloudTrail
* Redshift
  * Advanced SQL queries, must provision servers
  * Can leverage Redshift Spectrum for serverless queries on S3

---

<a name="11"></a>
# [↖](#top)[↑](#10_9_3)[↓](#11_1) Monitoring

<a name="11_1"></a>
## [↖](#top)[↑](#11)[↓](#11_1_1) CloudWatch (Core Topic)
<!-- toc_start -->
* [Overview](#11_1_1)
* [CloudWatch Metrics](#11_1_2)
* [CloudWatch Alarms](#11_1_3)
* [CloudWatch Dashboards](#11_1_4)
* [CloudWatch Events](#11_1_5)
  * [EventBridge](#11_1_5_1)
  * [S3 Events](#11_1_5_2)
* [CloudWatch Logs](#11_1_6)
  * [Log sources](#11_1_6_1)
  * [Log targets](#11_1_6_2)
  * [S3 Export](#11_1_6_3)
  * [Log Subscriptions](#11_1_6_4)
  * [Logs Agent & Unified Agent](#11_1_6_5)
<!-- toc_end -->

<a name="11_1_1"></a>
### [↖](#11_1)[↑](#11_1)[↓](#11_1_2) Overview
Amazon CloudWatch is a monitoring and observability service built for DevOps engineers, developers, site reliability engineers (SREs), and IT managers. CloudWatch provides you with data and actionable insights to monitor your applications, respond to system-wide performance changes, optimize resource utilization, and get a unified view of operational health. CloudWatch collects monitoring and operational data in the form of logs, metrics, and events, providing you with a unified view of AWS resources, applications, and services that run on AWS and on-premises servers. You can use CloudWatch to detect anomalous behavior in your environments, set alarms, visualize logs and metrics side by side, take automated actions, troubleshoot issues, and discover insights to keep your applications running smoothly.
* Access all your data from a single platform
* Easiest way to collect custom and granular metrics for AWS resources
* Visibility across your applications, infrastructure, and services
* Improve total cost of ownership
* Optimize applications and operational resources
* Derive actionable insights from logs
* On AWS
  * <a href="https://aws.amazon.com/cloudwatch/" target="_blank">Service</a> - <a href="https://aws.amazon.com/cloudwatch/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/cloudwatch/index.html" target="_blank">User Guide</a>
* See also: <a href="https://www.awsgeek.com/Amazon-EventBridge/Amazon-EventBridge.jpg" target="_blank">AWS Geek 2019</a>

<a name="11_1_2"></a>
### [↖](#11_1)[↑](#11_1_1)[↓](#11_1_3) CloudWatch Metrics
* Provided by many AWS services
* EC2 standard: 5 minutes, detailed monitoring: 1 minute
* EC2 RAM is not a built-in metric
* Can create custom metrics: standard resolution 1 minute, high resolution 1 sec

<a name="11_1_3"></a>
### [↖](#11_1)[↑](#11_1_2)[↓](#11_1_4) CloudWatch Alarms
* Based on thresholds defined on metrics, including custom metrics
  * Can only be based on a *single* metric
* Can trigger *SNS*, *Auto Scaling* or *EC2* action (`stop`/`terminate`/...
  * Alarms do *not* raise CloudWatch Events themselves, but can be forwarded to CloudWatch EventBridge
    * This allows to trigger a lot more actions
    * Notable targets:
      * Compute: Lambda, Batch, ECS task
      * Orchestration: Step Functions, CodePipeline, CodeBuild
      * Integration: SQS, SNS, Kinesis Data Streams, Kinesis Data Firehose
      * Maintenance: SSM, EC2 Actions
* *High resolution alarms* down to 10 seconds
* Takes place once, at a specific point in time
  * Disable with `mon-disable-alarm-actions` via CLI
* Can be added to dashboard
* Using *alarm actions*, you can create alarms that automatically stop, terminate, reboot, or recover your EC2 instances.

<a name="11_1_4"></a>
### [↖](#11_1)[↑](#11_1_3)[↓](#11_1_5) CloudWatch Dashboards
* Customizable home pages in the CloudWatch console that you can use to monitor your resources in a single correlated view
* Even those resources that are spread across different Regions.
* You can use CloudWatch dashboards to create customized views of the metrics and alarms for your AWS resources.

<a name="11_1_5"></a>
### [↖](#11_1)[↑](#11_1_4)[↓](#11_1_5_1) CloudWatch Events
* Define actions on things that happened
* Or schedule `cron`-based events
* Events are recorded constantly over time
  * *Targets* process events
  * *Rules* match incoming events and route them to targets
  * E.g. CodeCommit automatically triggers CodePipeline on new commits
* Can deliver cross-account
  * Must be in the same region
<a name="11_1_5_1"></a>
#### [↖](#11_1)[↑](#11_1_5)[↓](#11_1_5_2) EventBridge
* CloudWatch Events in its core
* Adding other (3rd party service partners) event sources into the mix
<a name="11_1_5_2"></a>
#### [↖](#11_1)[↑](#11_1_5_1)[↓](#11_1_6) S3 Events
* On bucket events send to SNS, SQS or Lambda
  * Not everything is covered by S3 notifications
  * Only object-level operations, not bucket-level
* Can also integrate with CloudTrail, but need a trail configured for that bucket

<a name="11_1_6"></a>
### [↖](#11_1)[↑](#11_1_5_2)[↓](#11_1_6_1) CloudWatch Logs
* *Log events* are records of some activity recorded by the application or resource being monitored
* *Log streams* are sequences of log events from the same source
* *Log groups* are groups of log streams that share the same retention, monitoring, and access control settings
* *Metric filters* allow to extract metric observations from ingested events and transform them to data points in a CloudWatch metric
  * Search for and match terms, phrases, or values in log events
  * Can increment the value of a CloudWatch metric
  * For example, find a specific IP inside of a log or count occurrences of “ERROR” in your logs
  * Metric filters can be used to trigger alarms
* *Retention settings* can be used to specify how long log events are kept in CloudWatch Logs
  * Default: Indefinetely
* Logs can be exported to S3 for durable storage.
  * This can be automated with `EventsFilter` -> `Lambda`

<a name="11_1_6_1"></a>
#### [↖](#11_1)[↑](#11_1_6)[↓](#11_1_6_2) Log sources
* SDK, CloudWatch Logs Agent, CloudWatch Unified Agent
* Elastic Beanstalk: collection of logs from application
* ECS: collection from containers
* AWS Lambda: collection from function logs
* VPC Flow Logs: VPC specific logs
* API Gateway
* CloudTrail based on filter
* CloudWatch log agents: for example on EC2 machines
* Route53: Log DNS queries

<a name="11_1_6_2"></a>
#### [↖](#11_1)[↑](#11_1_6_1)[↓](#11_1_6_3) Log targets
* CloudWatch Logs can send logs to
  * Amazon S3 (exports)
  * Kinesis Data Streams
  * Kinesis Data Firehose
  * AWS Lambda
  * ElasticSearch

<a name="11_1_6_3"></a>
#### [↖](#11_1)[↑](#11_1_6_2)[↓](#11_1_6_4) S3 Export
* S3 buckets must be encrypted with AES-256 (SSE-S3), not SSE-KMS
* Log data can take up to 12 hours to become available for export
* The API call is CreateExportTask
* Not near-real time or real-time... use Logs Subscriptions instead

<a name="11_1_6_4"></a>
#### [↖](#11_1)[↑](#11_1_6_3)[↓](#11_1_6_5) Log Subscriptions
* Allow real-time delivery of log events
* Can create subscription filter for *Lambda*, *Elasticsearch*, *Kinesis Data/Firehose* (not supported from console)
  * Only Kinesis Stream supports cross-account
    * Need to establish *log data sender* and *log data recipient*.
    * The log group and the destination must be in the same AWS region. However, the AWS resource that the destination points to can be located in a different region.

<a name="11_1_6_5"></a>
#### [↖](#11_1)[↑](#11_1_6_4)[↓](#11_2) Logs Agent & Unified Agent
* For virtual servers (EC2 instances, on-premises servers...)
* CloudWatch Logs Agent
  * Old version of the agent
  * Can only send to CloudWatch Logs
* CloudWatch Unified Agent
  * Collect additional system-level metrics such as RAM, processes, etc...
  * Collect logs to send to CloudWatch Logs
  * Centralized configuration using SSM Parameter Store
* Batch Sends
  * `batch_count`: number of log events to send (default 10000, min 1)
  * `batch_duration`: duration of batching for log events (default & min is 5000ms)
  * `batch_size`: max size of log events in a batch (default & max is 1 MB)
* Both agents cannot send logs to Kinesis

<a name="11_2"></a>
## [↖](#top)[↑](#11_1_6_5)[↓](#11_2_1) X-Ray
<!-- toc_start -->
* [Overview](#11_2_1)
<!-- toc_end -->

<a name="11_2_1"></a>
### [↖](#11_2)[↑](#11_2)[↓](#12) Overview
*AWS X-Ray* helps developers analyze and debug production, *distributed applications*, such as those built using a microservices architecture. With X-Ray, you can understand how your application and its underlying services are performing to identify and troubleshoot the root cause of performance issues and errors. X-Ray provides an end-to-end view of requests as they travel through your application, and shows a map of your application’s underlying components. You can use X-Ray to analyze both applications in development and in production, from simple three-tier applications to complex microservices applications consisting of thousands of services.
* X-Ray demon runs on EC2-instances/Elastic Beanstalk instances/ECS
* Integrations with:
  * EC2 – install the X-Ray agent
  * ECS – install the X-Ray agent or Docker container
  * Lambda
  * Beanstalk - agent is automatically installed
  * API Gateway – helpful to debug errors (such as 504)
* X-Ray SDK to send signals
* X-Ray API collects information
  * Automation could base on regular polling of `GetServiceGraph`
* X-Ray Console displays information in *service map*
* On AWS:
  * <a href="https://aws.amazon.com/xray/" target="_blank">Service</a> - <a href="https://aws.amazon.com/xray/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/xray/latest/userguide/" target="_blank">User Guide</a

<a name="12"></a>
# [↖](#top)[↑](#11_2_1)[↓](#12_1) Deployment and Instance Management

<a name="12_1"></a>
## [↖](#top)[↑](#12)[↓](#12_1_1) Elastic Beanstalk (Core Topic)
<!-- toc_start -->
* [Overview](#12_1_1)
* [Architecture models](#12_1_2)
* [Deployment Types](#12_1_3)
* [Blue/Green Deployment](#12_1_4)
<!-- toc_end -->

<a name="12_1_1"></a>
### [↖](#12_1)[↑](#12_1)[↓](#12_1_2) Overview
AWS Elastic Beanstalk is an easy-to-use service for deploying and scaling web applications and services developed with `Java`, `.NET`, `PHP`, `Node.js`, `Python`, `Ruby`, `Go`, and `Docker` on familiar servers such as Apache, Nginx, Passenger, and IIS.

You can simply upload your code and Elastic Beanstalk automatically handles the deployment, from capacity provisioning, load balancing, auto-scaling to application health monitoring. At the same time, you retain full control over the AWS resources powering your application and can access the underlying resources at any time.
* Elastic Beanstalk is a developer centric view of deploying an application on AWS
* Allows to *deploy*, *monitor* and *scale* applications quickly
* It uses all the component’s we’ve seen before: EC2, Auto Scaling Group, Elastic Load Balancers, RDS, etc...
  * But it’s all in one view that’s easy to make sense of!
* We still have full control over the configuration of each component
* Beanstalk is free but you pay for the underlying instances
* Focuses on components and performance, not configuration and specification
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
  * Packer Builder
  * Docker Single-/Multicontainer - runs on ECS
  * Docker Preconfigured Glassfish/Python/Go
* Elastic Beanstalk is great to “Replatform” your application from on-premises to the cloud
* Managed service
  * Instance configuration/OS is handled by Elastic Beanstalk
  * Deployment strategy is configurable but performed by Elastic Beanstalk
* Just the application code is the responsibility of the developer
* On AWS: <a href="https://aws.amazon.com/elasticbeanstalk/" target="_blank">Service</a> - <a href="https://aws.amazon.com/elasticbeanstalk/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/elastic-beanstalk/" target="_blank">User Guide</a>
* See also: <a href="https://www.awsgeek.com/AWS-Elastic-Beanstalk/AWS-Elastic-Beanstalk.jpg" target="_blank">AWS Geek 2019</a>

<a name="12_1_2"></a>
### [↖](#12_1)[↑](#12_1_1)[↓](#12_1_3) Architecture models
* Three architecture models:
  * **Single Instance deployment**: good for dev
    * Elastic IP, EC2, (RDS)
  * **LB + ASG**: great for production or pre-production web applications
    * ALB, ASG, EC2 (x AZs), (RDS multi-AZ)
  * **ASG only**: great for non-web apps in production (workers, etc..)
    * SQS, ASG, EC2
* If your application performs tasks that are long to complete, offload these tasks to a dedicated worker environment
* Decoupling your application into two tiers is common
  * Web Tier (LB + ASG + EC2)
  * Worker Tier (SQS + EC2)
* Example: processing a video, generating a zip file, etc
* You can define periodic tasks in a file `cron.yaml**`

<a name="12_1_3"></a>
### [↖](#12_1)[↑](#12_1_2)[↓](#12_1_4) Deployment Types
An **in-place upgrade** involves performing application updates on live Amazon EC2 instances. A **disposable upgrade**, on the other hand, involves rolling out a new set of EC2 instances by terminating older instances.
* Single instance deploys
* HA with Load Balancer
  * *All at once*
  * *Rolling update*
  * *Rolling with additional batches*
  * *Immutable*
    * Adds new Auto Scaling Group to existing environment
  * *Blue/Green* - not really supported, however
		* Not a “direct feature” of Elastic Beanstalk, but can achieve Zero downtime and release facility
		* Create a new “stage” environment and deploy v2 there
		* The new environment (green) can be validated independently and roll back if issues
		* Route 53 can be setup using weighted policies to redirect a little bit of traffic to the stage environment
		* Use Elastic Beanstalk's “swap URLs” feature (DNS swap) when done with the environment test
  * *Traffic Splitting* via Application Load Balancer
* Can configure Elastic Beanstalk to *ignore health checks* during deployments

<a name="12_1_4"></a>
### [↖](#12_1)[↑](#12_1_3)[↓](#12_2) Blue/Green Deployment
* Not a “direct feature” of Elastic Beanstalk, but can achieve Zero downtime and release facility
* Create a new “stage” environment and deploy v2 there
* The new environment (green) can be validated independently and roll back if issues
* Route 53 can be setup using weighted policies to redirect a little bit of traffic to the stage environment
* Use Elastic Beanstalk's “swap URLs” feature (DNS swap) when done with the environment test

---

<a name="12_2"></a>
## [↖](#top)[↑](#12_1_4)[↓](#12_2_1) OpsWorks Stacks (Core Topic)
<!-- toc_start -->
* [Overview](#12_2_1)
* [Components](#12_2_2)
<!-- toc_end -->
<a name="12_2_1"></a>
### [↖](#12_2)[↑](#12_2)[↓](#12_2_2) Overview
*AWS OpsWorks* is a configuration management service that provides managed instances of Chef and Puppet. Chef and Puppet are automation platforms that allow you to use code to automate the configurations of your servers. OpsWorks lets you use Chef and Puppet to automate how servers are configured, deployed, and managed across your Amazon EC2 instances or on-premises compute environments.
* Chef & Puppet help you perform server configuration automatically, or repetitive actions
* They work great with EC2 & On-premises VM
* AWS OpsWorks = Managed Chef & Puppet
* It’s an alternative to AWS SSM
* If you’re already using cookbooks (chef) on-Premises, OpsWorks is good
* Migrating from other tech to OpsWorks or vice–versa is not easy
* Declarative desired state engine
  * Automate, monitor and maintain deployments
* AWS' implementation of *Chef*
	* Original Chef
	* AWS-bespoke orchestration components
  * **Cookbooks** define **recipes**
* OpsWorks has three offerings:
  * *AWS OpsWorks Stacks* (**<- exam relevant**)
  * *AWS Opsworks for Chef Automate*
  * *AWS OpsWorks for Puppet Enterprise*
* For Chef 11, *BerkShelf* is often used
	* Allows to use external cookbooks
* On AWS: <a href="https://aws.amazon.com/opsworks/stacks/" target="_blank">Service</a> - <a href="https://aws.amazon.com/opsworks/stacks/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/opsworks/latest/userguide/" target="_blank">User Guide</a>
<a name="12_2_2"></a>
### [↖](#12_2)[↑](#12_2_1)[↓](#12_3) Components
* **Stack**
  * Set of resources that are managed as a group
* **Layer**
  * Represent and configure components of a stack
  * Share common configuration elements
* **Instance**
  * Units of compute within the platform
  * Must be associated with at least one layer
* **App**
  * Applications that are deployed on one or more instances
* **Deployments**
  * Deploy application code and related files to application server instances

---

<a name="12_3"></a>
## [↖](#top)[↑](#12_2_2)[↓](#12_3_1) CodeDeploy (Core Topic)
<!-- toc_start -->
* [Overview](#12_3_1)
* [Deploys](#12_3_2)
  * [To EC2/On-premises](#12_3_2_1)
  * [To Lambdas](#12_3_2_2)
  * [To ECS](#12_3_2_3)
<!-- toc_end -->
<a name="12_3_1"></a>
### [↖](#12_3)[↑](#12_3)[↓](#12_3_2) Overview
*AWS CodeDeploy* is a fully managed deployment service that automates software deployments to a variety of compute services such as Amazon EC2, AWS Fargate, AWS Lambda, and your on-premises servers. AWS CodeDeploy makes it easier for you to rapidly release new features, helps you avoid downtime during application deployment, and handles the complexity of updating your applications. You can use AWS CodeDeploy to automate software deployments, eliminating the need for error-prone manual operations. The service scales to match your deployment needs.
* CodeDeploy can be chained into CodePipeline and can use artifacts from there
* CodeDeploy does not provision resources
* Automated deployments
  * EC2, on-premises, (ASG), ECS (Fargate), Lambda
* Minimize downtime
* Centralized control
* Easy to adopt
* Integrates with AWS SAM
* On AWS: <a href="https://aws.amazon.com/codedeploy/" target="_blank">Service</a> - <a href="https://aws.amazon.com/codedeploy/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/codedeploy/latest/userguide/" target="_blank">User Guide</a>
<a name="12_3_2"></a>
### [↖](#12_3)[↑](#12_3_1)[↓](#12_3_2_1) Deploys
<a name="12_3_2_1"></a>
#### [↖](#12_3)[↑](#12_3_2)[↓](#12_3_2_1_1) To EC2/On-premises
* Define how to deploy the application using appspec.yml + deployment strategy
* Can use hooks to verify the deployment after each deployment phase
* **In-place**
  * The application on each instance in the deployment group is stopped
  * The latest application revision is installed
  * The new version of the application is started and validated.
  * You can use a load balancer so that each instance is deregistered during its deployment and then restored to service after the deployment is complete.
  * Only deployments that use the EC2/On-Premises compute platform can use in-place deployments.0
* **Blue/green**
  * Instances are provisioned for the replacement environment.
  * The latest application revision is installed on the replacement instances.
  * An optional wait time occurs for activities such as application testing and system verification.
  * Instances in the *replacement* environment are registered with an Elastic Load Balancing load balancer, causing traffic to be rerouted to them.
  * Instances in the *original* environment are deregistered and can be terminated or kept running for other uses.
  * If you use an EC2/On-Premises compute platform, be aware that blue/green deployments work with Amazon EC2 instances only.

##### Integration with Elastic Load Balancing
* During deployments, a load balancer prevents internet traffic from being routed to instances when they are not ready, are currently being deployed to, or are no longer needed as part of an environment.
* **Blue/Green Deployments**
  * Allows traffic to be routed to the new instances in a deployment group that the latest application revision has been deployed to (the replacement environment), according to the rules you specify
  * Blocks traffic from the old instances where the previous application revision was running (the original environment).
  * After instances in a replacement environment are registered with a load balancer, instances from the original environment are deregistered and, if you choose, terminated.
  * Specify a Classic Load Balancer, Application Load Balancer, or Network Load Balancer in your deployment group.
* **In-Place Deployments**
  * Prevents internet traffic from being routed to an instance while it is being deployed to
  * Makes the instance available for traffic again after the deployment to that instance is complete.
  * If a load balancer isn't used during an in-place deployment, internet traffic may still be directed to an instance during the deployment process.
  * When you use a load balancer with an in-place deployment, instances in a deployment group are deregistered from a load balancer, updated with the latest application revision, and then reregistered with the load balancer as part of the same deployment group after the deployment is successful.
  * Specify a Classic Load Balancer, Application Load Balancer, or Network Load Balancer. You can specify the load balancer as part of the deployment group's configuration, or use a script provided by CodeDeploy to implement the load balancer.

##### Integration with Auto Scaling Groups
* When new Amazon EC2 instances are launched as part of an Amazon EC2 Auto Scaling group, CodeDeploy can deploy your revisions to the new instances automatically.
* During blue/green deployments on an EC2/On-Premises compute platform, you have two options for adding instances to your replacement (green) environment:
  * Use instances that already exist or that you create manually.
  * Use settings from an Amazon EC2 Auto Scaling group that you specify to define and create instances in a new Amazon EC2 Auto Scaling group.
* If an Amazon EC2 Auto Scaling scale-up event occurs while a deployment is underway, the new instances will be updated with the application revision that was most recently deployed, not the application revision that is currently being deployed.
  * Suspend scaling during rolling deploys
  * Or redeploy

##### Register on-premises instances
* Configure each on-premises instance, register it with CodeDeploy, and then tag it.
* Need to install CodeDeploy agent, obviously
* On-premises instances cannot blue/green, as CodeDeploy cannot create new infrastructure

<a name="12_3_2_2"></a>
#### [↖](#12_3)[↑](#12_3_2_1_3)[↓](#12_3_2_2_1) To Lambdas
* Lambda deploys a new *version* under an *alias*, and traffic is shifted between old and new version
	* (Versions and Aliases are native Lambda features)
* Pre- and post-traffic hooks feature to validate deployment before and after the traffic shift
* Easy & automated rollback using CloudWatch Alarms

##### Integration with AWS Serverless
* Deploys new versions of your Lambda function, and automatically creates aliases that point to the new version.
* Gradually shifts customer traffic to the new version until you're satisfied that it's working as expected, or you roll back the update.
* Defines pre-traffic and post-traffic test functions to verify that the newly deployed code is configured correctly and your application operates as expected.
* Rolls back the deployment if CloudWatch alarms are triggered.

<a name="12_3_2_3"></a>
#### [↖](#12_3)[↑](#12_3_2_2_1)[↓](#12_4) To ECS
* Support for Blue/Green deployments for Amazon ECS and AWS Fargate
* Setup is done within the ECS service definition
* CodeDeploy reroutes traffic from the original version of a task set to a new, replacement task set
* Target groups specified in the deployment group are used to serve traffic to the original and replacement task sets
* After the deployment is complete, the original task set is terminated.
* Can specify an optional test listener to serve test traffic to your replacement version before traffic is rerouted to it

---

<a name="12_4"></a>
## [↖](#top)[↑](#12_3_2_3)[↓](#12_4_1) CloudFormation (Core Topic)
<!-- toc_start -->
* [Overview](#12_4_1)
* [CloudFormation and ASG](#12_4_2)
* [Retaining Data on Deletes](#12_4_3)
* [CloudFormation and IAM](#12_4_4)
* [Custom Resources](#12_4_5)
* [Cross vs Nested Stacks](#12_4_6)
* [Other Concepts](#12_4_7)
<!-- toc_end -->
<a name="12_4_1"></a>
### [↖](#12_4)[↑](#12_4)[↓](#12_4_2) Overview
*AWS CloudFormation* provides a common language for you to describe and provision all the infrastructure resources in your cloud environment. CloudFormation allows you to use a simple text file to model and provision, in an automated and secure manner, all the resources needed for your applications across all regions and accounts. This file serves as the single source of truth for your cloud environment.

AWS CloudFormation is available at no additional charge, and you pay only for the AWS resources needed to run your applications.
* Allows to create and provision **resources** in a reusable **template** fashion
* Declarative - no need for ordering and orchestration
* Separation of concerns - different stacks for different purposes
* Backbone of
  * Elastic Beanstalk
  * Service Catalog
  * SAM (Serverless Application Model)
* On AWS: <a href="https://aws.amazon.com/cloudformation/" target="_blank">Service</a> - <a href="https://aws.amazon.com/cloudformation/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html" target="_blank">User Guide</a>

<a name="12_4_2"></a>
### [↖](#12_4)[↑](#12_4_1)[↓](#12_4_3) CloudFormation and ASG
* CloudFormation manages the ASG, not the underlying EC2
* You can define “success conditions” for the launch of your EC2 instances using a `CreationPolicy`
* You can define “update strategies” for the update of your EC2 instances using an `UpdatePolicy`
* To update the underlying EC2 in an ASG, you have to create a new launch configuration/launch template & use an `UpdatePolicy`

<a name="12_4_3"></a>
### [↖](#12_4)[↑](#12_4_2)[↓](#12_4_4) Retaining Data on Deletes
* You can put a DeletionPolicy on any resource to control what happens when the CloudFormation template is deleted
* DeletionPolicy **Retain**
  * Specify on resources to preserve/backup in case of CloudFormation deletes
  * To keep a resource, specify Retain (works for any resource/nested stack)
* DeletionPolicy **Snapshot**
  * EBS Volume, ElastiCache Cluster, ElastiCache ReplicationGroup
  * RDS DBInstance, RDS DBCluster, Redshift Cluster
* DeletePolicy **Delete** (default behavior):
  * Note: for AWS::RDS::DBCluster resources, the default policy is Snapshot
  * Note: to delete an S3 bucket, you need to first empty the bucket of its content

<a name="12_4_4"></a>
### [↖](#12_4)[↑](#12_4_3)[↓](#12_4_5) CloudFormation and IAM
* When deploying a CloudFormation stack
  * It uses the permissions of our own IAM principal
  * OR assign an IAM role to the stack that can perform the actions
* If you create IAM resources, you need to explicitly provide a “capability” to CloudFormation CAPABILITY_IAM and CAPABILITY_NAMED_IAM

<a name="12_4_5"></a>
### [↖](#12_4)[↑](#12_4_4)[↓](#12_4_6) Custom Resources
* You can define a Custom Resource in CloudFormation to address any of these use cases:
* An AWS resource is not yet supported (new service for example)
* Example use cases
  * An on-premises resource
  * Emptying an S3 bucket before being deleted
  * Fetch an AMI id
  * Anything you want...!

<a name="12_4_6"></a>
### [↖](#12_4)[↑](#12_4_5)[↓](#12_4_7) Cross vs Nested Stacks
* Cross Stacks
  * Helpful when stacks have different lifecycles
  * Use Outputs Export and `Fn::ImportValue`
  * When you need to pass export values to many stacks (VPC Id, etc...)
* Nested Stacks
  * Helpful when components must be re-used
  * Ex: re-use Application Load Balancer configuration
  * The nested stack only is important to the higher level stack (it’s not shared)

<a name="12_4_7"></a>
### [↖](#12_4)[↑](#12_4_6)[↓](#12_5) Other Concepts
* CloudFormer
  * Create an AWS CloudFormation template from existing AWS resources
* ChangeSets
  * Generate & Preview the CloudFormation changes before they get applied
* StackSets
  * Deploy a CloudFormation stack across multiple accounts and regions
* Stack Policies
  * Prevent accidental updates/deletes to stack resources

  ---

<a name="12_5"></a>
## [↖](#top)[↑](#12_4_7)[↓](#12_5_1) Service Catalog
<!-- toc_start -->
* [Overview](#12_5_1)
* [Components](#12_5_2)
<!-- toc_end -->

<a name="12_5_1"></a>
### [↖](#12_5)[↑](#12_5)[↓](#12_5_2) Overview
AWS Service Catalog allows organizations to create and manage catalogs of IT services that are approved for use on AWS. These IT services can include everything from virtual machine images, servers, software, and databases to complete multi-tier application architectures. AWS Service Catalog allows you to centrally manage commonly deployed IT services, and helps you achieve consistent governance and meet your compliance requirements, while enabling users to quickly deploy only the approved IT services they need.
* Ensure compliance with corporate standards
* Help employees quickly find and deploy approved IT services
* Centrally manage IT service lifecycle
* Connect with ITSM/ITOM software
* Self-service for user
  * Integrates with self-service portals like ServiceNow
* Users of Service Catalog *only* required IAM permissions for the product, but *not* the underlying services
* On AWS: <a href="https://aws.amazon.com/servicecatalog/" target="_blank">Service</a> - <a href="https://aws.amazon.com/servicecatalog/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/servicecatalog/latest/userguide/" target="_blank">User Guide</a>

<a name="12_5_2"></a>
### [↖](#12_5)[↑](#12_5_1)[↓](#12_6) Components
* **Admins** define
  * **Product**
    * Defined in CloudFormation
    * Can be versioned
  *	**Portfolio**
    * Collection of products
    * IAM permissions to govern access
    * Products available per team/per client/...
* **Users** choose
  * from product list
  * launches automatically

---

<a name="12_6"></a>
## [↖](#top)[↑](#12_5_2)[↓](#12_6_1) AWS Serverless Application Model
<!-- toc_start -->
* [Overview](#12_6_1)
<!-- toc_end -->

<a name="12_6_1"></a>
### [↖](#12_6)[↑](#12_6)[↓](#12_7) Overview
The AWS Serverless Application Model (SAM) is an open-source framework for building serverless applications. It provides shorthand syntax to express functions, APIs, databases, and event source mappings. With just a few lines per resource, you can define the application you want and model it using YAML. During deployment, SAM transforms and expands the SAM syntax into AWS CloudFormation syntax, enabling you to build serverless applications faster.

To get started with building SAM-based applications, use the AWS SAM CLI. SAM CLI provides a Lambda-like execution environment that lets you locally build, test, and debug applications defined by SAM templates. You can also use the SAM CLI to deploy your applications to AWS.
* Framework for developing and deploying serverless applications
* All configuration is YAML code
  * Lambda Functions (`AWS::Serverless::Function`)
  * DynamoDB tables (`AWS::Serverless::SimpleTable`)
  * API Gateway (`AWS::Serverless::API`)
  * Cognito User Pools
* SAM can help you to run Lambda, API Gateway, DynamoDB locally
* SAM can use CodeDeploy to deploy Lambda functions (traffic shifting)
* Leverages CloudFormation in the backend
* On AWS: <a href="https://aws.amazon.com/serverless/sam" target="_blank">Service</a> - <a href="https://aws.amazon.com/serverless/sam/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/serverless-application-model/" target="_blank">User Guide</a>

---

<a name="12_7"></a>
## [↖](#top)[↑](#12_6_1)[↓](#12_7_1) Deployments (Core Topic)
<!-- toc_start -->
* [Options](#12_7_1)
* [Mechanisms](#12_7_2)
* [Per AWS Service](#12_7_3)
<!-- toc_end -->
<a name="12_7_1"></a>
### [↖](#12_7)[↑](#12_7)[↓](#12_7_2) Options
.|.
-|-
Vanilla EC2|With User Data (just for the first launch)
AMI Baking|For things that are slow to install (runtimes, updates, tools), and use EC2 user data for quick runtime setup
Auto Scaling Group|With launch template (AMI)
CodeDeploy|In-place on EC2<br/>In-place on ASG<br/>New instances on ASG<br/>Traffic shifting for AWS Lambda<br/>New task set for ECS + traffic shifting
Elastic Beanstalk|In-place all at once upgrades<br/>Rolling upgrades (with or without additional instances)<br/>Immutable upgrades (new instances)<br/>Blue/Green (entirely new stack)
OpsWorks|For chef/puppet stacks only<br/>Can manage ELB and EC2 instances<br/>Cannot manage an ASG
SAM Framework|Leverages CloudFormation & CodeDeploy

<a name="12_7_2"></a>
### [↖](#12_7)[↑](#12_7_1)[↓](#12_7_3) Mechanisms
.|.
-|-
Runtime/container|`EC2` - `ECS` - `Lambda` - `Elastic Beanstalk`
Application deployment|`CodeDeploy` - `OpsWorks` -  `Elastic Beanstalk`
Code/deployment management|`CodeCommit` - `CodePipeline` -  `Elastic Beanstalk`
Infrastructure deployment|`OpsWorks` - `CloudFormation` - `Elastic Beanstalk`

<a name="12_7_3"></a>
### [↖](#12_7)[↑](#12_7_2)[↓](#12_8) Per AWS Service

Strategy|Auto Scaling<br/>Group|CodeDeploy<br/>EC2/On-Premises|CodeDeploy ECS|CodeDeploy Lambda|Elastic<br/>Beanstalk|OpsWorks
-|-|-|-|-|-|-
**Single Target Deployment**|.|.|.|.|redeploy|.
**All At Once**|`AutoScalingReplacingUpdate`|*All-at-once*|.|.|*all at once*|.
**Minimum In Service**|.|.|.|.|*rolling*|.
**Rolling**|`AutoScalingRollingUpdate`|*One-at-at-time*|.|.|*rolling*|.
**Rolling With Extra Batches**|.|.|.|.|*rolling with<br/>extra batches*|.
**Blue/Green**|.|Traffic is shifted to a replacement set of instances<br/>* *All-at-once*<br/>* *Half-at-a-time*<br/>* *One-at-a-time*|Traffic is shifted to a replacement task set<br/>* *Canary*<br/>* *Linear*<br/>* *All-at-once*|Traffic is shifted to a new Lambda version<br/>* *Canary*<br/>* *Linear*<br/>* *All-at-once*|*immutable* comes close<br/>or: create new environment and use DNS|create new environment and use DNS
**Canary**|.|.|See above<br/>* *Canary*|See above<br/>* *Canary*|*Traffic Splitting*|.

---

<a name="12_8"></a>
## [↖](#top)[↑](#12_7_3)[↓](#12_8_1) Systems Manager (Core Topic)
<!-- toc_start -->
* [Overview](#12_8_1)
* [Components](#12_8_2)
  * [Resources groups](#12_8_2_1)
  * [Insights](#12_8_2_2)
  * [Parameter store](#12_8_2_3)
  * [Action & Change](#12_8_2_4)
  * [Instances & Nodes](#12_8_2_5)
<!-- toc_end -->

<a name="12_8_1"></a>
### [↖](#12_8)[↑](#12_8)[↓](#12_8_2) Overview
AWS Systems Manager gives you visibility and control of your infrastructure on AWS. Systems Manager provides a unified user interface so you can view operational data from multiple AWS services and allows you to automate operational tasks across your AWS resources. With Systems Manager, you can group resources, like Amazon EC2 instances, Amazon S3 buckets, or Amazon RDS instances, by application, view operational data for monitoring and troubleshooting, and take action on your groups of resources. Systems Manager simplifies resource and application management, shortens the time to detect and resolve operational problems, and makes it easy to operate and manage your infrastructure securely at scale.
*Group resources* -> *Visualize data* -> *Take action*
* Manage EC2 and on-premises instances at scale
  * On-premises requires generation of secret *activation code*/*activation id*
* Get operational insights of infrastructure
* Easily detect problems
* Patching automation for enhanced compliance
* Both Linux and Windows
* Tightly integrated with CloudWatch, AWS Config
* Free service
* SSM Agent
  * Installed on instances
  * Need correct IAM permissions, then shows up on SSM dashboard
* On AWS: <a href="https://aws.amazon.com/systems-manager/" target="_blank">Service</a> - <a href="https://aws.amazon.com/systems-manager/faq/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/systems-manager/latest/userguide/" target="_blank">User Guide</a>

<a name="12_8_2"></a>
### [↖](#12_8)[↑](#12_8_1)[↓](#12_8_2_1) Components
<a name="12_8_2_1"></a>
#### [↖](#12_8)[↑](#12_8_2)[↓](#12_8_2_2) Resources groups
* Organize your AWS resources.
* Make it easier to manage, monitor, and automate tasks on large numbers of resources at one time.
  * Define groups based on tags or on CloudFormation stacks
	* Same region only

<a name="12_8_2_2"></a>
#### [↖](#12_8)[↑](#12_8_2_1)[↓](#12_8_2_3) Insights
* **Insights dashboards**
  * Automatically aggregates and displays operational data for each resource group
* **Inventory**
  * Discover and audit the software installed
* **Configuration Compliance**
  * Scan your fleet of managed instances for patch compliance and configuration inconsistencies

<a name="12_8_2_3"></a>
#### [↖](#12_8)[↑](#12_8_2_2)[↓](#12_8_2_4) Parameter store
* Secure storage for configuration and secrets
* Optional seamless encryption using KMS
* Serverless, scalable, durable, easy SDK, free
* Version tracking of configurations/secrets
* Configuration management using path & IAM
* Notifications with CloudWatch Events
* Integration with CloudFormation
* Can retrieve secrets from Secrets Manager using the SSM Parameter Store API

<a name="12_8_2_4"></a>
#### [↖](#12_8)[↑](#12_8_2_3)[↓](#12_8_2_5) Action & Change
* **Automation**
  * Simplifies common maintenance and deployment tasks of EC2 instances and other AWS resources.
  * Build Automation workflows to configure and manage instances and AWS resources.
  * Create custom workflows or use pre-defined workflows maintained by AWS.
  * Receive notifications about Automation tasks and workflows by using Amazon CloudWatch Events.
  * Monitor Automation progress and execution details by using the Amazon EC2 or the AWS Systems Manager console.
  * Can integrate manual approval step
  * Complete *list* of tasks, unlike run command which is a one-off
  * E.g. create *Golden AMi*
* **Maintenance windows**
  * Define a schedule for when to perform potentially disruptive actions on your instances
* **Change Calendar**
  * Set up date and time ranges when actions you specify may or may not be performed in your AWS account

<a name="12_8_2_5"></a>
#### [↖](#12_8)[↑](#12_8_2_4)[↓](#13) Instances & Nodes
* **Run command**
  * Lets you remotely and securely manage the configuration of your managed instances
  * Commands are in *document* format
  * Can run on resource group, individually or tag-based
* **Session manager**
  * Fully managed AWS Systems Manager capability that lets you manage your EC2 instances, on-premises instances, and virtual machines (VMs) through an interactive one-click browser-based shell or through the AWS CLI.
  * Session Manager provides secure and auditable instance management without the need to open inbound ports, maintain bastion hosts, or manage SSH keys
* **Patch manager**
  * Automates the process of patching managed instances with both security related and other types of updates
  * AWS predefined *patch baselines* per operating system
    * Linux
      * `AWS-AmazonLinux2DefaultPatchBaseline`
      * `AWS-CentOSDefaultPatchBaseline`
      * `AWS-RedHatDefaultPatchBaseline`
      * `AWS-SuseDefaultPatchBaseline`
      * `AWS-UbuntuDefaultPatchBaseline`
    * Windows
      * `AWS-DefaultPatchBaseline`: install OS patch CriticalUpdates & SecurityUpdates
      * `AWS-WindowsPredefinedPatchBaseline-OS`: same as “AWS-DefaultPatchBaseline”
      * `AWS-WindowsPredefinedPatchBaseline-OS-Applications`: also updates Microsoft applications
    * Can also define own patch baselines
      * Patch items in approved or rejected list, e.g. 'CVE-2020-1234567'
      * Can define own patch source
  * Define *Patch Group* (based on tags)
  * Define *Maintenance Window* when patches are possibly executed
  * Use `AWS-RunPatchBaseline` *run command*
  * Define *Rate Control* (concurrency & error threshold) for the task
  * Monitor *Patch Compliance* using SSM Inventory
    * Can also evaluate compliance without applying patches
* **State manager**
  * Secure and scalable configuration management service that automates the process of keeping your Amazon EC2 and hybrid infrastructure in a state that you define
* **SSM Documents**
  * JSON format
  * Different types:
    * *Command*
    * *Automation*
    * *Policy*
    * *Session*

---

<a name="13"></a>
# [↖](#top)[↑](#12_8_2_5)[↓](#13_1) Cost Control

<a name="13_1"></a>
## [↖](#top)[↑](#13)[↓](#13_2) Best practices of cost management
* Only allow specific groups or teams to deploy chosen AWS resources.
* Create policies for each environment.
* Require tags in order to instantiate resources.
* Monitor and send alerts or shut down instances that are improperly tagged.
* Use CloudWatch to send alerts when billing thresholds are met.
* Analyze spend using AWS or partner tools.

<a name="13_2"></a>
## [↖](#top)[↑](#13_1)[↓](#13_3) AWS Cost Allocation Tags
* With Tags we can track resources that relate to each other
* With Cost Allocation Tags we can enable detailed costing reports
* Just like Tags, but they show up as columns in Reports
* **AWS Generated Cost Allocation Tags**
  * Automatically applied to the resource you create
  * Starts with Prefix aws: (e.g. `aws:createdBy`)
  * They’re not applied to resources created before the activation
* **User tags**
  * Defined by the user
  * Starts with Prefix user:
* Cost Allocation Tags just appear in the Billing Console
* Takes up to 24 hours for the tags to show up in the report
* <a href="https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/cost-alloc-tags.html" target="_blank">On AWS</a>

---

<a name="13_3"></a>
## [↖](#top)[↑](#13_2)[↓](#13_3_1) Trusted Advisor (Core Topic)
<!-- toc_start -->
* [Overview](#13_3_1)
* [Support Plans](#13_3_2)
<!-- toc_end -->

<a name="13_3_1"></a>
### [↖](#13_3)[↑](#13_3)[↓](#13_3_2) Overview
AWS Trusted Advisor is an online tool that provides you real time guidance to help you provision your resources following AWS best practices. Whether establishing new workflows, developing applications, or as part of ongoing improvement, take advantage of the recommendations provided by Trusted Advisor on a regular basis to help keep your solutions provisioned optimally.
* Global service
* Creates recommendations for
  * Cost optimization
  * Performance
  * Security
  * Fault tolerance
  * Service limits
* Trusted Advisor *check results* are raised as CloudWatch Events
  * Automate by triggering Lambdas
  * Events are only available in `us-east-1`
* Checks are refreshed on visits to the dashboard (max every 5 minutes)
	* Otherwise weekly
  * Can trigger refresh via API
* Full Trusted Advisor – Available for Business & Enterprise support plans only
  * Ability to set CloudWatch alarms when reaching limits
  * Programmatic Access using AWS Support API
* On AWS: <a href="https://aws.amazon.com/trustedadvisor/" target="_blank">Service</a> - <a href="https://aws.amazon.com/premiumsupport/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/awssupport/latest/user/getting-started.html" target="_blank">User Guide</a>

<a name="13_3_2"></a>
### [↖](#13_3)[↑](#13_3_1)[↓](#13_4) Support Plans

.|.
-|-
Basic Support|included for all AWS customers and free
Developer|Recommended when you are experimenting with AWS
Business|If you have production workloads
Enterprise|If you have mission-critical workloads

---

<a name="13_4"></a>
## [↖](#top)[↑](#13_3_2)[↓](#13_4_1) EC2 Purchasing Options & Saving Plans (Core Topic)
<!-- toc_start -->
* [EC2 Purchasing Options](#13_4_1)
  * [Spot Instances](#13_4_1_1)
  * [Spot Fleets](#13_4_1_2)
  * [Pricing by](#13_4_1_3)
* [Savings Plan](#13_4_2)
<!-- toc_end -->

<a name="13_4_1"></a>
### [↖](#13_4)[↑](#13_4)[↓](#13_4_1_1) EC2 Purchasing Options

.|.|.
-|-|-
**On-demand instances**|Short workloads, predictable pricing, reliable|Pay for compute capacity by the hour, instance can be terminated by Amazon
**Reserved instances**|.|Provide a significant discount compared to On-Demand pricing and provide a capacity reservation when used in a specific Availability Zone<br/>Up to 50% cheaper than a *fully utilized* on-demand instance (because we commit upfront to a certain usage)<br/>Minimum 1 year<br/>Guarantees to *not* run into '*insufficent instance capacity*' issues if AWS is unable to provision instances in that AZ<br/>Can resell reserved capacity on *Reserved Instance Marketplace*<br/>Can transfer between AZs
Standard reserved instances|Long workloads|Fixed instance type|
Convertible reserved instances|Long workloads with flexible instances|Can be exchanged against another convertible instance type|
~~Scheduled reserved instances~~|.|deprecated
**Spot instances**|Short workloads, for cheap, can lose instances (not reliable)|Bid on spare Amazon EC2 computing capacity, not available for all instance types
**Dedicated instance**|No other customers will share your hardware|Run on dedicated hardware, but no need to purchase the whole host<br/>Great for software licenses that operate at the core, or socket level<br/>Can define host affinity so that instance reboots are kept on the same host
**Dedicated hosts**|Book an entire physical server, control instance placement|A physical server with EC2 instance capacity fully dedicated to your use
* <a href="https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-purchasing-options.html" target="_blank">On AWS</a>

<a name="13_4_1_1"></a>
#### [↖](#13_4)[↑](#13_4_1)[↓](#13_4_1_2) Spot Instances
* Can get a discount of up to 90% compared to On-demand
* Define max spot price and get the instance while current `spot price < max`
  * The hourly spot price varies based on offer and capacity
  * If the current spot price > your max price you can choose to stop or terminate your instance with a 2 minutes grace period.
* Other strategy: Spot Block
  * “block” spot instance during a specified time frame (1 to 6 hours) without interruptions
* In rare situations, the instance may be reclaimed

<a name="13_4_1_2"></a>
#### [↖](#13_4)[↑](#13_4_1_1)[↓](#13_4_1_3) Spot Fleets
* Collection (Fleet) of Spot Instances and optionally on-demand instances
  * Set a maximum price you’re willing to pay per Spot Instances or all
  * Can have a mix of instance types (M5.large, M5.xlarge, C5.2xlarge, etc..)
* Supports: EC2 standalone, Auto Scaling Groups (launch template), ECS (underlying ASG), AWS Batch (Managed Compute Environment)
* Soft limits
  * Target capacity per Spot Fleet or EC2 fleet: 10,000
  * Target capacity across all Spot Fleet and EC2 Fleet in a region: 100,000
* Allocation strategies
	* `lowestPrice`
		* The Spot Instances come from the pool with the lowest price. This is the default strategy.
	* `diversified`
		* The Spot Instances are distributed across all pools.
	* `capacityOptimized`
		* The Spot Instances come from the pools with optimal capacity for the number of instances that are launching. You can optionally set a priority for each instance type in your fleet using capacityOptimizedPrioritized. EC2 implements the priorities on a best-effort basis, but optimizes for capacity first.
	* `InstancePoolsToUseCount`
		* The Spot Instances are distributed across the number of Spot pools that you specify. This parameter is valid only when used in combination with lowestPrice.

<a name="13_4_1_3"></a>
#### [↖](#13_4)[↑](#13_4_1_2)[↓](#13_4_2) Pricing by
* Instance Type
* Compute time
* Data transfer
* Storage
* Elastic IP address
* Monitoring
* Elastic load balancer

<a name="13_4_2"></a>
### [↖](#13_4)[↑](#13_4_1_3)[↓](#13_5) Savings Plan
Savings Plans is a flexible pricing model that provides savings of up to 72% on your AWS compute usage. This pricing model offers lower prices on Amazon EC2 instances usage, regardless of instance family, size, OS, tenancy or AWS Region, and also applies to AWS Fargate and AWS Lambda usage.

Savings Plans offer significant savings over On Demand, just like EC2 Reserved Instances, in exchange for a commitment to use a specific amount of compute power (measured in $/hour) for a one or three year period. You can sign up for Savings Plans for a 1- or 3-year term and easily manage your plans by taking advantage of recommendations, performance reporting and budget alerts in the AWS Cost Explorer.
* Complements or replaces reserved instances
* New pricing model to get a discount based on long-term usage
* Commit to a certain type of usage: ex $10 per hour for 1 to 3 years
* Any usage beyond the savings plan is billed at the on-demand price
* **EC2 Instance Savings plan** (up to 72% - same discount as Standard RIs)
  * Select instance family (e.g. M5, C5...), and locked to a specific region
  * Flexible across size (m5.large to m5.4xlarge), OS (Windows to Linux), tenancy (dedicated or default)
* **Compute Savings plan** (up to 66% - same discount as Convertible RIs)
  * Ability to move between instance family (move from C5 to M5), region (Ireland to US), compute type (EC2, Fargate, Lambda), OS & tenancy
* On AWS: <a href="https://aws.amazon.com/savingsplans/" target="_blank">Service</a> - <a href="https://aws.amazon.com/savingsplans/faq/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/savingsplans/" target="_blank">User Guide</a>

<a name="13_5"></a>
## [↖](#top)[↑](#13_4_2)[↓](#13_5_1) S3 Cost Savings
<!-- toc_start -->
* [S3 Storage Classes](#13_5_1)
* [S3 Other Cost savings](#13_5_2)
<!-- toc_end -->

<a name="13_5_1"></a>
### [↖](#13_5)[↑](#13_5)[↓](#13_5_2) S3 Storage Classes

.|Durability|Availability|AZs|Costs per GB|Retrieval Fee|.
-|-|-|-|-|-|-
S3 Standard|**11x9**|**4x9**|**>=3**|$0.023|**No**|.
S3 Intelligent Tiering|**11x9**|3x9|**>=3**|$0.023|**No**|Automatically moves objects between two access tiers based on changing access patterns
S3 IA (infrequent access)|**11x9**|3x9|**>=3**|$0.0125|Yes|For data that is accessed less frequently, but requires rapid access when needed
S3 One Zone IA (infrequent access)|**11x9**|99.5|1|**$0.01**|Yes|For data that is accessed less frequently, but requires rapid access when needed
Glacier|**11x9**|.|**>=3**|$0.004<br/>min 90 days|Yes|For archival only, comes as *expedited* (1-5min), *standard* (3-5h) or *bulk* (5-12h)
Glacier Deep Archive|**11x9**|.|**>=3**|$0.00099<br/>min 180 days|Yes|Longer time span to retrieve
~~S3 RRS (reduced redundancy storage)~~|4x9|4x9|>=3|$0.024|.|Deprecated

<a name="13_5_2"></a>
### [↖](#13_5)[↑](#13_5_1)[↓](#14) S3 Other Cost savings
* *S3 Select* & *Glacier Select*: save in network and CPU cost
* S3 Lifecycle Rules: transition objects between tiers
* Compress objects to save space
* **S3 Requester Pays**:
  * In general, bucket owners pay for all Amazon S3 storage and data transfer costs associated with their bucket
  * With Requester Pays buckets, the requester instead of the bucket owner pays the cost of the request and the data download from the bucket
  * The bucket owner always pays the cost of storing data
  * Helpful when you want to share large datasets with other accounts
  * If an IAM role is assumed, the owner account of that role pays for the request

---

<a name="14"></a>
# [↖](#top)[↑](#13_5_2)[↓](#14_1) Migration

<a name="14_1"></a>
## [↖](#top)[↑](#14)[↓](#14_1_1) The 6R Strategies
<!-- toc_start -->
* [Rehosting — Otherwise known as “lift-and-shift.”](#14_1_1)
* [Replatforming — I sometimes call this “lift-tinker-and-shift.”](#14_1_2)
* [Repurchasing — Moving to a different product.](#14_1_3)
* [Refactoring/Re-architecting — Re-imagining how the application is architected and developed, typically using cloud-native features.](#14_1_4)
* [Retire — Get rid of.](#14_1_5)
* [Retain — Usually this means “revisit” or do nothing (for now).](#14_1_6)
<!-- toc_end -->
* <a href="https://aws.amazon.com/blogs/enterprise-strategy/6-strategies-for-migrating-applications-to-the-cloud/" target="_blank">On AWS Blog</a>

<a name="14_1_1"></a>
### [↖](#14_1)[↑](#14_1)[↓](#14_1_2) Rehosting — Otherwise known as “lift-and-shift.”
* Simple migrations by re-hosting on AWS (applications, databases, data...)
* No cloud optimizations being done, application is migrated as is
* Could save as much as 30% on cost
* Example: Migrate using AWS VM Import/Export, AWS Server Migration Service

<a name="14_1_2"></a>
### [↖](#14_1)[↑](#14_1_1)[↓](#14_1_3) Replatforming — I sometimes call this “lift-tinker-and-shift.”
* Not changing the core architecture, but leverage some cloud optimizations
* Example
	* Migrate database to RDS
	* Migrate application to Elastic Beanstalk (Java with Tomcat)

<a name="14_1_3"></a>
### [↖](#14_1)[↑](#14_1_2)[↓](#14_1_4) Repurchasing — Moving to a different product.
* Moving to a different product while moving to the cloud
* Often you move to a SaaS platform
* Expensive in the short term, but quick to deploy
* Example
	* CRM to Salesforce.com, HR to Workday, CMS to Drupal

<a name="14_1_4"></a>
### [↖](#14_1)[↑](#14_1_3)[↓](#14_1_5) Refactoring/Re-architecting — Re-imagining how the application is architected and developed, typically using cloud-native features.
* Reimagining how the application is architected using Cloud Native features
* Driven by the need of the business to add features, scale, performance
* Example
	* Move an application to Serverless architectures, use AWS S3

<a name="14_1_5"></a>
### [↖](#14_1)[↑](#14_1_4)[↓](#14_1_6) Retire — Get rid of.
* Turn off things you don’t need (maybe as a result of Re-architecting)
* Helps with reducing the surface areas for attacks (more security)
* Save cost, maybe up to 10% to 20%
* Focus your attention on resources that must be maintained

<a name="14_1_6"></a>
### [↖](#14_1)[↑](#14_1_5)[↓](#14_2) Retain — Usually this means “revisit” or do nothing (for now).
* Do nothing for now (for simplicity, cost reason, importance...)
* It’s still a decision to make in a Cloud Migration

---

<a name="14_2"></a>
## [↖](#top)[↑](#14_1_6)[↓](#14_3) On-Premises strategies with AWS

.|.
-|-
Download Amazon Linux 2 AMI as a VM (.iso format)|VMWare, KVM, VirtualBox (Oracle VM), Microsoft Hyper-V
AWS Application Discovery Service|Gather information about your on-premises servers to plan a migration<br/>Server utilization and dependency mappings<br/>Track with AWS Migration Hub
AWS VM Import/Export|Migrate existing applications into EC2<br/>Create a DR repository strategy for your on-premises VMs<br/>Can export back the VMs from EC2 to on-premise
AWS Server Migration Service (SMS)|Incremental replication of on-premises live servers to AWS<br/>Migrates the entire VM into AWS
AWS Database Migration Service (DMS)|Replicate On-premises => AWS , AWS => AWS, AWS => On-premises<br/>Works with various database technologies (Oracle, MySQL, DynamoDB, etc..)

---

<a name="14_3"></a>
## [↖](#top)[↑](#14_2)[↓](#14_3_1) Storage Gateway (Core Topic)
<!-- toc_start -->
* [Overview](#14_3_1)
* [Gateway types](#14_3_2)
  * [File gateway (NFS, SMB)](#14_3_2_1)
  * [Volume gateway (iSCSI)](#14_3_2_2)
  * [Tape gateway (VTL)](#14_3_2_3)
<!-- toc_end -->

<a name="14_3_1"></a>
### [↖](#14_3)[↑](#14_3)[↓](#14_3_2) Overview
AWS Storage Gateway connects an on-premises software appliance with cloud-based storage to provide seamless integration with data security features between your on-premises IT environment and the AWS storage infrastructure. You can use the service to store data in the AWS Cloud for scalable and cost-effective storage that helps maintain data security.

The gateway connects to AWS storage services, such as Amazon S3, Amazon Glacier, Amazon EBS, and AWS Backup, providing storage for files, volumes, snapshots, and virtual tapes in AWS.
* Bridge between on-premises data and cloud data in S3
* Use cases: disaster recovery, backup & restore, tiered storage
* Download as VM image, install on host in datacenter
* Gateway types
	* File gateway
	* Tape gateway
	* Stored-volume gateway
	* Cached-volume gateway
* On AWS
	* <a href="https://aws.amazon.com/storagegateway/" target="_blank">Service</a> - <a href="https://aws.amazon.com/storagegateway/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/storagegateway/latest/userguide/WhatIsStorageGateway.html" target="_blank">User Guide</a>

<a name="14_3_2"></a>
### [↖](#14_3)[↑](#14_3_1)[↓](#14_3_2_1) Gateway types

<a name="14_3_2_1"></a>
#### [↖](#14_3)[↑](#14_3_2)[↓](#14_3_2_1_1) File gateway (NFS, SMB)
The *File Gateway* presents a file interface that enables you to store files as objects in Amazon S3 using the industry-standard NFS and SMB file protocols, and access those files via NFS and SMB from your datacenter or Amazon EC2, or access those files as objects with the S3 API.
* File Gateway appliance is a virtual machine to bridge between your NFS and S3
* File gateway offers SMB or NFS-based access to data in Amazon S3 with local caching.
* Can be managed as S3 native objects (bucket policies, cross-region replication etc)
* Each File Gateway should have an IAM role to access S3
* Metadata and directory structure are preserved
* Most recently used data is cached in the file gateway
* Can be mounted on many servers
* <a href="https://d0.awsstatic.com/whitepapers/aws-storage-gateway-file-gateway-for-hybrid-architectures.pdf" target="_blank">AWS whitepaper</a>

##### File gateway scenarios
* **Migration setup**
	* Install File Gateway Appliance in DC *and* in a VPC
	* EC2s would see the same data than on-premises
* **Read Only Replicas**
	* Data Center 1 uses File Gateway Appliance to mirror data into S3
	* Data Center 2 uses File Gateway Appliance to create a read replica from S3
* **Backup and Lifecycle Policies**
	* Use S3 lifecycle policies to migrate data into deeper S3 layers (IA, Glacier)
* **Amazon S3 Object Versioning**
	* Ability to store multiple object versions as they are modified
	* Helpful to restore a file to a previous version
	* Could restore an entire file system to a previous version
	* Must use the “RefreshCache” API on the Gateway to be notified of restore
* **Amazon S3 Object Lock**
	* Enables to have the File Gateway for *Write Once Read Many* (WORM) data
	* If there are file modifications or renames in the file share clients, the file gateway creates a new version of the object without affecting priori versions, and the original locked version will remain unchanged

<a name="14_3_2_2"></a>
#### [↖](#14_3)[↑](#14_3_2_1_1)[↓](#14_3_2_3) Volume gateway (iSCSI)
The *Volume Gateway* presents your applications storage volumes using the `iSCSI` block protocol. Data written to these volumes can be asynchronously backed up as point-in-time snapshots of your volumes, and stored in the cloud as Amazon EBS snapshots. You can set the schedule for when snapshots occur or create them via the AWS Management Console or service API. Snapshots are incremental backups that capture only changed blocks. All snapshot storage is also compressed to minimize your storage charges. * *Stored* volumes (all data on-prem, EBS snapshots in cloud, stored on S3) * *Cached* volumes (only recently used data on-prem, EBS volumes in cloud, stored on S3)
* Block storage using iSCSI protocol backed by S3
* **Cached volumes**: low latency access to most recent data, full data on S3
* **Stored volumes**: entire dataset is on-premises, scheduled backups to EBS/S3
* Can create EBS snapshots from the volumes and restore as EBS!
* Up to 32 volumes per gateway
	* Each volume up to 32TB in cached mode (1PB per Gateway)
	* Each volume up to 16 TB in stored mode (512TB per Gateway)
* Uses Challenge-Handshake Authentication Protocol (CHAP) to authenticate iSCSI and initiator connections. CHAP provides protection against playback attacks by requiring authentication to access storage volume targets.

<a name="14_3_2_3"></a>
#### [↖](#14_3)[↑](#14_3_2_2)[↓](#14_4) Tape gateway (VTL)
The *Tape Gateway* presents itself to your existing backup application as an industry-standard iSCSI-based virtual tape library (VTL), consisting of a virtual media changer and virtual tape drives. You can continue to use your existing backup applications and workflows while writing to a nearly limitless collection of virtual tapes. Each virtual tape is stored in Amazon S3. When you no longer require immediate or frequent access to data contained on a virtual tape, you can have your backup application move it from the Storage Gateway Virtual Tape Library into an archive tier that sits on top of Amazon Glacier cloud storage, further reducing storage costs.
* Some companies still have backup processes using physical tapes
* With Tape Gateway, companies use the same processes but in the cloud
* Virtual Tape Library (VTL) backed by Amazon S3 and Glacier
* Back up data using existing tape-based processes (and iSCSI interface)
* Works with leading backup software vendors
* You can’t access single file within tapes. You need to restore the tape entirely

---

<a name="14_4"></a>
## [↖](#top)[↑](#14_3_2_3)[↓](#14_4_1) Snowball
<!-- toc_start -->
* [Snowball Process](#14_4_1)
<!-- toc_end -->

Snowball is a petabyte-scale data transport solution that uses devices designed to be secure to transfer large amounts of data into and out of the AWS Cloud. Using Snowball addresses common challenges with large-scale data transfers including high network costs, long transfer times, and security concerns. Customers today use Snowball to migrate analytics data, genomics data, video libraries, image repositories, backups, and to archive part of data center shutdowns, tape replacement or application migration projects. Transferring data with Snowball is simple, fast, more secure, and can be as little as one-fifth the cost of transferring data via high-speed Internet.

This replaces *Import Export* which was a manual service to ship drives to AWS.
* Physical data transport solution that helps moving TBs or PBs of data in or out of AWS
* Alternative to moving data over the network (and paying network fees)
* Secure, tamper resistant, uses KMS 256 bit encryption
* Tracking using SNS and text messages. E-ink shipping label
* Snowball size: 50TB and 80TB
* Use cases: large data cloud migrations, DC decommission, disaster recovery
* If it takes more than a week to transfer over the network, use Snowball devices!
* **Snowball** (deprecated)
  * Import/export to S3
* **Snowball Edge**
  * With onboard compute
		* Supports a custom EC2 AMI so you can perform processing on the go
		* Supports custom Lambda functions
* **Snowmobile**
  * The thing on the truck
* On AWS
	* <a href="https://aws.amazon.com/snowball/" target="_blank">Service</a> - <a href="https://aws.amazon.com/snowball/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/snowball/index.html" target="_blank">User Guide</a>

<a name="14_4_1"></a>
### [↖](#14_4)[↑](#14_4)[↓](#14_5) Snowball Process
* Request snowball devices from the AWS console for delivery
* Install the snowball client on your servers
* Connect the snowball to your servers and copy files using the client
* Ship back the device when you’re done (goes to the right AWS facility)
* Data will be loaded into an S3 bucket
* Snowball is completely wiped
* Tracking is done using SNS, text messages and the AWS console

---

<a name="14_5"></a>
## [↖](#top)[↑](#14_4_1)[↓](#14_5_1) Database Migration Service (Core Topic)
<!-- toc_start -->
* [Overview](#14_5_1)
* [Schema Conversion Tool (SCT)](#14_5_2)
* [Good to know](#14_5_3)
* [Combine Snowball & DMS](#14_5_4)
<!-- toc_end -->

<a name="14_5_1"></a>
### [↖](#14_5)[↑](#14_5)[↓](#14_5_2) Overview
AWS Database Migration Service helps you migrate databases to AWS quickly and securely. The source database remains fully operational during the migration, minimizing downtime to applications that rely on the database. The AWS Database Migration Service can migrate your data to and from most widely used commercial and open-source databases.

AWS Database Migration Service supports homogeneous migrations such as Oracle to Oracle, as well as heterogeneous migrations between different database platforms, such as Oracle or Microsoft SQL Server to Amazon Aurora. With AWS Database Migration Service, you can continuously replicate your data with high availability and consolidate databases into a petabyte-scale data warehouse by streaming data to Amazon Redshift and Amazon S3. Learn more about the supported source and target databases.
* Quickly and securely migrate databases to AWS
	* Resilient, self healing
	* Source database remains available during the migration
* Supports
	* Homogeneous migrations: ex Oracle to Oracle
	* Heterogeneous migrations: ex Microsoft SQL Server to Aurora
* Continuous Data Replication using Change Data Capture (CDC)
* You must create an EC2 instance to perform the replication tasks
* Sources
	* On-Premises and EC2 instances databases: Oracle, MS SQL Server, MySQL, MariaDB, PostgreSQL, MongoDB, SAP, DB2
	* Azure: Azure SQL Database
	* Amazon RDS: all including Aurora
	* Amazon S3
	* *not*: RedShift, DynamoDb, ElasticSearch Service, Kinesis Data Streams
* Targets
	* On-premises and EC2 instances databases: Oracle, MS SQL Server, MySQL, MariaDB, PostgreSQL, SAP
	* Amazon RDS, Amazon Redshift, Amazon DynamoDB, Amazon S3, ElasticSearch Service, Kinesis Data Streams, DocumentDB
* On AWS
	* <a href="https://aws.amazon.com/dms/" target="_blank">Service</a> - <a href="https://aws.amazon.com/dms/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/dms/" target="_blank">User Guide</a>

<a name="14_5_2"></a>
### [↖](#14_5)[↑](#14_5_1)[↓](#14_5_3) Schema Conversion Tool (SCT)
* Convert your Database’s Schema from one engine to another
* Example OLTP: (SQL Server or Oracle) to MySQL, PostgreSQL, Aurora
* Example OLAP: (Teradata or Oracle) to Amazon Redshift
* You do *not* need to use SCT if you are migrating the *same* DB engine
	* Ex: On-premises PostgreSQL => RDS PostgreSQL
	* The DB engine is still PostgreSQL (RDS is the platform)

<a name="14_5_3"></a>
### [↖](#14_5)[↑](#14_5_2)[↓](#14_5_4) Good to know
* Works over VPC Peering, VPN (site to site, software), Direct Connect
* Supports Full Load, Full Load + CDC, or CDC only
* Oracle:
	* Source: Supports Transparent Data Encryption (TDE) for the source using “BinaryReader”
	* Target: Supports BLOBs in tables that have a primary key, and TDE
* ElasticSearch:
	* Source: does not exist
	* Target: possible to migrate to DMS from a relational database
	* Therefore DMS cannot be used to replicate ElasticSearch data

<a name="14_5_4"></a>
### [↖](#14_5)[↑](#14_5_3)[↓](#14_6) Combine Snowball & DMS
* Larger data migrations can include many terabytes of information.
* Can be limited due to network bandwidth or size of data
* AWS DMS can use Snowball Edge & Amazon S3 to speed up migration
* Following stages:
	* You use the AWS Schema Conversion Tool (AWS SCT) to extract the data locally and move it to an Edge device.
	* You ship the Edge device or devices back to AWS.
	* After AWS receives your shipment, the Edge device automatically loads its data into an Amazon S3 bucket.
	* AWS DMS takes the files and migrates the data to the target data store. If you are using change data capture (CDC), those updates are written to the Amazon S3 bucket and then applied to the target data store.

---

<a name="14_6"></a>
## [↖](#top)[↑](#14_5_4)[↓](#14_7) Application Discovery Service (Core Topic)
AWS Application Discovery Service helps enterprise customers plan migration projects by gathering information about their on-premises data centers.

Planning data center migrations can involve thousands of workloads that are often deeply interdependent. Server utilization data and dependency mapping are important early first steps in the migration process. AWS Application Discovery Service collects and presents configuration, usage, and behavior data from your servers to help you better understand your workloads.

The collected data is retained in encrypted format in an AWS Application Discovery Service data store. You can export this data as a CSV file and use it to estimate the Total Cost of Ownership (TCO) of running on AWS and to plan your migration to AWS. In addition, this data is also available in AWS Migration Hub, where you can migrate the discovered servers and track their progress as they get migrated to AWS.
* Plan migration projects by gathering information about on-premises data centers
* Server utilization data and dependency mapping are important for migrations
* Agentless discovery (Application Discovery Agentless Connector):
	* Open Virtual Appliance (OVA) package that can be deployed to a VMware host
	* VM inventory, configuration, and performance history such as CPU, memory, and disk usage
	* OS agnostic
* Agent-based discovery:
	* System configuration, system performance, running processes, and details of the network connections between systems
	* Supports Microsoft Server, Amazon Linux, Ubuntu, RedHat, CentOS, SUSE...
	* Resulting data can be exported as CSV or viewed within AWS Migration Hub
* Data can be explorer using pre-defined queries in Amazon Athena
* On AWS
	* <a href="https://aws.amazon.com/application-discovery/" target="_blank">Service</a> - <a href="https://aws.amazon.com/application-discovery/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/application-discovery/index.html" target="_blank">User Guide</a>

---

<a name="14_7"></a>
## [↖](#top)[↑](#14_6)[↓](#14_8) Server Migration Service
AWS Server Migration Service (SMS) is an agentless service which makes it easier and faster for you to migrate thousands of on-premises workloads to AWS. AWS SMS allows you to automate, schedule, and track incremental replications of live server volumes, making it easier for you to coordinate large-scale server migrations.
* **Simplify the cloud migration process**. You can begin migrating a group of servers with just a few clicks in the AWS Management Console. After the migration has initiated, AWS SMS manages all the complexities of the migration process, including automatically replicating volumes of live servers to AWS and creating new AMIs periodically. You can quickly launch EC2 instances from AMIs in the console.
* **Orchestrate multi-server migrations**. AWS SMS orchestrates server migrations by allowing you to schedule replications and track progress of a group of servers that constitutes an application. You can schedule initial replications, configure replication intervals, and track progress for each server using the console. When you launch a migrated application, you can apply customized configuration scripts that run during startup.
* **Test server migrations incrementally**: With support for incremental replication, AWS SMS allows fast, scalable testing of migrated servers. Because AWS SMS replicates incremental changes to your on-premises servers and transfers only the delta to the cloud, you can test small changes iteratively and save on network bandwidth.
* **Support the most widely used operating systems**. AWS SMS supports the replication of operating system images containing Windows, as well as several major Linux distributions.
* **Minimize downtime**. Incremental AWS SMS replication minimizes the business impact associated with application downtime during the final cutover.

Summary:
* Migrate entire VMs to AWS, improvement over EC2 VM Import/Export service (deprecated)
	* That means the OS, the data, everything is kept intact
	* After loading the VM onto EC2 you can update the OS, the data, make an AMI
	* Therefore SMS is used to re-host
* Only works with VMware vSphere, Windows Hyper-V, and Azure VM
* Every replication creates an EBS snapshot/AMI ready for deployment on EC2
* Every replication is incremental
* “*One time migrations*”, or “*replication every interval*” option
* On AWS
	* <a href="https://aws.amazon.com/server-migration-service/" target="_blank">Service</a> - <a href="https://aws.amazon.com/server-migration-service/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/server-migration-service/index.html" target="_blank">User Guide</a>

---

<a name="14_8"></a>
## [↖](#top)[↑](#14_7)[↓](#14_9) AWS Cloud Adoption Readiness Tool (CART)
Helps organizations of all sizes develop efficient and effective plans for cloud adoption and enterprise cloud migrations. This 16-question online survey and assessment report details your cloud migration readiness across six perspectives including business, people, process, platform, operations, and security. Once you complete a CART survey, you can provide your contact details to download a customized cloud migration assessment that charts your readiness and what you can do to improve it. This tool is designed to help organizations assess their progress with cloud adoption and identify gaps in organizational skills and processes.
* On AWS
	* <a href="https://cloudreadiness.amazonaws.com/#/cart" target="_blank">Tool</a>

---

<a name="14_9"></a>
## [↖](#top)[↑](#14_8)[↓](#15) Disaster Recovery
* DR is about preparing for and recovering from a disaster
* *Recovery Point Objective* - RPO
  * How often do you run backups? How much data will be lost (since last backup)
* *Recovery Time Objective* - RTO
  * How much downtime is acceptable?

From|To|.
-|-|-
On-prem|On-prem|Traditional DR, very expensive
On-prem|Cloud|Hybrid recovery
Cloud Region A|Cloud Region B|.

.|RPO|RTO|Costs|Comment|What to do for DR
-|-|-|-|-|-
Backup & Restore|High|High|$|Regular backups|Restore
Pilot Light|Medium|Medium|$$|Core system is always running, but cannot process requests with additional action being taken|Add non-critical systems
Warm Standby|Low|Low|$$$|Full system at minimum size always running, can handle traffic immediately (at reduced capacity)|Add resources
Multi Site/Hot Site|Lowest|Lowest|$$$$|Full system at production size always running|Only switch traffic

* <a href="https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/plan-for-disaster-recovery-dr.html" target="_blank">On AWS</a>

---

<a name="15"></a>
# [↖](#top)[↑](#14_9)[↓](#15_1) VPC

<a name="15_1"></a>
## [↖](#top)[↑](#15)[↓](#15_1_1) Virtual Private Cloud (VPC)
<!-- toc_start -->
* [Overview](#15_1_1)
  * [Default VPC (Amazon specific)](#15_1_1_1)
  * [Non-default VPC (regular VPC)](#15_1_1_2)
  * [VPC Scenarios](#15_1_1_3)
* [Components](#15_1_2)
* [Structure & Package Flow](#15_1_3)
  * [Package flow through VPC components](#15_1_3_1)
  * [VPC Flow Logs](#15_1_3_2)
* [Limits](#15_1_4)
<!-- toc_end -->

<a name="15_1_1"></a>
### [↖](#15_1)[↑](#15_1)[↓](#15_1_1_1) Overview
Amazon Virtual Private Cloud (Amazon VPC) is a service that lets you launch AWS resources in a logically isolated virtual network that you define. You have complete control over your virtual networking environment, including selection of your own IP address range, creation of subnets, and configuration of route tables and network gateways. You can use both IPv4 and IPv6 for most resources in your virtual private cloud, helping to ensure secure and easy access to resources and applications.

As one of AWS's foundational services, Amazon VPC makes it easy to customize your VPC's network configuration. You can create a public-facing subnet for your web servers that have access to the internet. It also lets you place your backend systems, such as databases or application servers, in a private-facing subnet with no internet access. Amazon VPC lets you to use multiple layers of security, including security groups and network access control lists, to help control access to Amazon EC2 instances in each subnet.
* Provisions a logically isolated section of the AWS cloud
* Spans over all AZs in a region
* Allows to create layered architecture
* Shared or dedicated tenancy (exclusive hardware or not)
  * Cannot be changed after VPC creation
* *Security groups* and subnet-level *network ACLs*
* Ability to extend on-premises network to cloud
* On AWS
	* <a href="https://aws.amazon.com/vpc/" target="_blank">Service</a> - <a href="https://aws.amazon.com/vpc/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/toolkit-for-visual-studio/latest/user-guide/vpc-tkv.html" target="_blank">User Guide</a>

<a name="15_1_1_1"></a>
#### [↖](#15_1)[↑](#15_1_1)[↓](#15_1_1_2) Default VPC (Amazon specific)
* Gives easy access to a VPC without having to configure it from scratch
* Has different subnets in different AZs and an internet gateway (HA, spread out to all AZs)
* Each instance launched automatically receives a *public IP* (and a private IP), this is usually not the case for non-default VPCs)
* Cannot be restored if deleted
* Comes with default NACL that allows all inbound/outbound traffic
<a name="15_1_1_2"></a>
#### [↖](#15_1)[↑](#15_1_1_1)[↓](#15_1_1_3) Non-default VPC (regular VPC)
* Only has private IP addresses
* Resources *only* accessible through *Elastic IP*, *VPN* or *internet gateways*

<a name="15_1_1_3"></a>
#### [↖](#15_1)[↑](#15_1_1_2)[↓](#15_1_2) VPC Scenarios
* VPC with private subnet only -> single tier apps
* VPC with public and private subnets -> layered apps
* VPC with public, private subnets and hardware connected VPN -> extending apps to on-premise
* VPC with private subnets and hardware connected VPN -> extended VPN

<a name="15_1_2"></a>
### [↖](#15_1)[↑](#15_1_1_3)[↓](#15_1_3) Components
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
	* Each subnet in a VPC must be associated with a route table; the table controls the routing for the subnet. A subnet can only be associated with one route table at a time, but multiple subnets can be associated with the same route table
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
		* Horizontally scaled, redundant, and highly available VPC component that allows communication between instances in a VPC and the internet
		* Provides a target in VPC route tables for internet-routable traffic
		* Performs network address translation (NAT) for instances that have been assigned public IPv4 addresses
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
  * One subnet can (and must) only ever be associated to one NACL, however, one NACL can be associated to many subnets
  * Rules for inbound and outbound traffic
  * Rules have numbers and are evaluated from low to high
  * Default is to deny everything in and out
  * *Stateless*
  * Support *allow* and *deny* rules
  * Can block IP addresses (Security groups can't)
	* **Cannot** block URLs (forward proxies can)
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

<a name="15_1_3"></a>
### [↖](#15_1)[↑](#15_1_2)[↓](#15_1_3_1) Structure & Package Flow
<a name="15_1_3_1"></a>
#### [↖](#15_1)[↑](#15_1_3)[↓](#15_1_3_2) Package flow through VPC components
* VPC (has *CIDR*)
	* Gateway (Internet or VPN)
  * Router
	* Route table (one per subnet, can be shared)
	* Network ACL (one per subnet, can be shared)
	* Subnets (CIDRs match VPC's CIDR)
	* Security Group (on VPC level)
	* Instance (needs public IP for internet communication, either ELB or Elastic IP)

<a name="15_1_3_2"></a>
#### [↖](#15_1)[↑](#15_1_3_1)[↓](#15_1_4) VPC Flow Logs
VPC Flow Logs is a feature that enables you to capture information about the IP traffic going to and from network interfaces in your VPC. Flow log data can be published to Amazon CloudWatch Logs and Amazon S3. After you've created a flow log, you can retrieve and view its data in the chosen destination.

Can be created at 3 levels:
* VPC
* Subnet
* Network interface

<a name="15_1_4"></a>
### [↖](#15_1)[↑](#15_1_3_2)[↓](#15_2) Limits
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

---

<a name="15_2"></a>
## [↖](#top)[↑](#15_1_4)[↓](#15_2_1) VPC Peering
<!-- toc_start -->
* [Longest prefix match](#15_2_1)
<!-- toc_end -->
* Connect VPCs through direct network routing
	* Cross-region, cross-account
* Should not have matching or overlapping CIDR blocks
	* If you have a VPC peered with multiple VPCs that have overlapping or matching CIDR blocks, ensure that your route tables are configured to avoid sending response traffic from your VPC to the incorrect VPC.
* Allows instances to communicate with each other as if they were in the same network
* Peering is in star configuration with 1 central VPC. No transitive peering.
	* Must be established for each VPC that need to communicate with one another
* Only routes traffic between source and destination VPC
  * Does not support edge to edge routing
		* Even if VPC A can route into VPC B, it cannot use VPC A's edge infrastructure
		* VPN, Direct Connect, IGW, NAT, Gateway VPC Endpoint (S3 & DynamoDB)
  * Does not share VPN connection into datacenter
* Must update route tables in each VPC’s subnets to ensure instances can communicate
* Can reference a security group of a peered VPC (even cross-account)

<a name="15_2_1"></a>
### [↖](#15_2)[↑](#15_2)[↓](#15_3) Longest prefix match
* VPC uses the longest prefix match to select the most specific route
* Other way of saying it is “most specific route”

---

<a name="15_3"></a>
## [↖](#top)[↑](#15_2_1)[↓](#15_3_1) Transit Gateway
<!-- toc_start -->
* [Overview](#15_3_1)
* [Previously: Transit VPC (=Software VPN)](#15_3_2)
<!-- toc_end -->

<a name="15_3_1"></a>
### [↖](#15_3)[↑](#15_3)[↓](#15_3_2) Overview
AWS Transit Gateway connects VPCs and on-premises networks through a central hub. This simplifies your network and puts an end to complex peering relationships. It acts as a cloud router – each new connection is only made once.

As you expand globally, inter-Region peering connects AWS Transit Gateways together using the AWS global network. Your data is automatically encrypted, and never travels over the public internet. And, because of its central position, AWS Transit Gateway Network Manager has a unique view over your entire network, even connecting to Software-Defined Wide Area Network (SD-WAN) devices.
* For having transitive peering between thousands of VPC and on-premises, hub-and-spoke (star) connection
* Regional resource, can work cross-region
* Share cross-account using Resource Access Manager
	* AWS Resource Access Manager (AWS RAM) lets you share your resources with any AWS account or through AWS Organizations. If you have multiple AWS accounts, you can create resources centrally and use AWS RAM to share those resources with other accounts.
* You can peer Transit Gateways across regions
* Route Tables: limit which VPC can talk with other VPC
* Works with Direct Connect Gateway, VPN connections
* Supports *IP Multicast* (not supported by any other AWS service)
* Instances in a VPC can access a NAT Gateway, NLB, PrivateLink, and EFS in others VPCs attached to the AWS Transit Gateway.
* On AWS:
	* <a href="https://aws.amazon.com/transit-gateway/" target="_blank">Service</a> - <a href="https://aws.amazon.com/transit-gateway/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/vpc/latest/tgw/what-is-transit-gateway.html" target="_blank">User Guide</a>

<a name="15_3_2"></a>
### [↖](#15_3)[↑](#15_3_1)[↓](#15_4) Previously: Transit VPC (=Software VPN)
* Not an AWS offering, newer managed solution is Transit Gateway
* Uses the public internet with a software VPN solution
* Allows for transitive connectivity between VPC & locations
* More complex routing rules, overlapping CIDR ranges, network-level packet filtering

---

<a name="15_4"></a>
## [↖](#top)[↑](#15_3_2)[↓](#15_4_1) VPC Endpoints (Core Topic)
<!-- toc_start -->
* [VPC Endpoint Gateway](#15_4_1)
* [VPC Endpoint Interface](#15_4_2)
* [VPC Endpoint Gateway Load Balancer](#15_4_3)
* [VPC Endpoint Policies](#15_4_4)
<!-- toc_end -->
A VPC endpoint enables private connections between your VPC and supported AWS services and VPC endpoint services powered by AWS PrivateLink. AWS PrivateLink is a technology that enables you to privately access services by using private IP addresses. Traffic between your VPC and the other service does not leave the Amazon network. A VPC endpoint does not require an internet gateway, virtual private gateway, NAT device, VPN connection, or AWS Direct Connect connection. Instances in your VPC do not require public IP addresses to communicate with resources in the service.
* Endpoints allow you to connect to AWS Services using a private network instead of the public internet
* They scale horizontally and are redundant
* No more IGW, NAT, etc... to access AWS Services
* **VPC Endpoint Gateway** (S3 & DynamoDB)
* **VPC Endpoint Interface** (the rest)
* In case of problems:
	* Check DNS Setting Resolution in your VPC
	* Check Route Tables
* On AWS:
	* <a href="https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints.html" target="_blank">User Guide</a>

<a name="15_4_1"></a>
### [↖](#15_4)[↑](#15_4)[↓](#15_4_2) VPC Endpoint Gateway
A gateway endpoint is a gateway that is a target for a specified route in your route table. This type of endpoint is used for traffic destined to a supported AWS service, such as Amazon S3 or Amazon DynamoDB.
* Only works for S3 and DynamoDB, must create one gateway per VPC
* Must update route tables entries
* Gateway is defined at the VPC level
* DNS resolution must be enabled in the VPC
* The same public hostname for S3 can be used
* Gateway endpoint cannot be extended out of a VPC (VPN, DX, TGW, peering)

<a name="15_4_2"></a>
### [↖](#15_4)[↑](#15_4_1)[↓](#15_4_3) VPC Endpoint Interface
An interface endpoint is an elastic network interface with a private IP address from the IP address range of your subnet. It serves as an entry point for traffic destined to a supported AWS service or a VPC endpoint service. Interface endpoints are powered by AWS PrivateLink.
* Provision an ENI that will have a private endpoint interface hostname
* Leverage Security Groups for security
* Private DNS (setting when you create the endpoint)
* The public hostname of a service will resolve to the private Endpoint Interface hostname
* VPC Setting: “Enable DNS hostnames” and “Enable DNS Support” must be 'true’
* Example for Athena:
	* vpce-0b7d2995e9dfe5418-mwrths3x.athena.us-east-1.vpce.amazonaws.com
	* vpce-0b7d2995e9dfe5418-mwrths3x-us-east-1a.athena.us-east-1.vpce.amazonaws.co
	* vpce-0b7d2995e9dfe5418-mwrths3x-us-east-1b.athena.us-east-1.vpce.amazonaws.com
	* athena.us-east-1.amazonaws.com (private DNS name)
* Interface are sharable
	* Can be accessed from Direct Connect and Site-to-Site VPN

<a name="15_4_3"></a>
### [↖](#15_4)[↑](#15_4_2)[↓](#15_4_4) VPC Endpoint Gateway Load Balancer
A Gateway Load Balancer endpoint is an elastic network interface with a private IP address from the IP address range of your subnet. Gateway Load Balancer endpoints are powered by AWS PrivateLink

<a name="15_4_4"></a>
### [↖](#15_4)[↑](#15_4_3)[↓](#15_5) VPC Endpoint Policies
A VPC endpoint policy is an IAM resource policy that you attach to an endpoint when you create or modify the endpoint. If you do not attach a policy when you create an endpoint, we attach a default policy for you that allows full access to the service. If a service does not support endpoint policies, the endpoint allows full access to the service. An endpoint policy does not override or replace IAM user policies or service-specific policies (such as S3 bucket policies). It is a separate policy for controlling access from the endpoint to the specified service.
* Endpoint Policies are JSON documents to control access to services
* Does not override or replace IAM user policies or service-specific policies (such as S3 bucket policies)
* On AWS:
	* <a href="https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints-access.html" target="_blank">User Guide</a>

---

<a name="15_5"></a>
## [↖](#top)[↑](#15_4_4)[↓](#15_5_1) PrivateLink
<!-- toc_start -->
* [Overview](#15_5_1)
<!-- toc_end -->
<a name="15_5_1"></a>
### [↖](#15_5)[↑](#15_5)[↓](#15_6) Overview
AWS PrivateLink enables you to connect to some AWS services, services hosted by other AWS accounts (referred to as endpoint services), and supported AWS Marketplace partner services, via private IP addresses in your VPC. The interface endpoints are created directly inside of your VPC, using elastic network interfaces and IP addresses in your VPC’s subnets. That means that VPC Security Groups can be used to manage access to the endpoints.

We recommend this approach if you want to use services offered by another VPC securely within AWS network, with all network traffic staying on the global AWS backbone and never traverses the public internet.
* Most secure & scalable way to expose a service to 1000s of VPC (own or other accounts)
* Does not require VPC peering, internet gateway, NAT, route tables...
* Requires a NLB (Service VPC) and PrivateLink Endpoint/ENI (Customer VPC)
* If the NLB is in multiple AZ, and the ENI in multiple AZ, the solution is fault tolerant!
* Scenario:
	* Secure and Scale Web Filtering using Explicit Proxy
* On AWS:
	* <a href="https://aws.amazon.com/privatelink/" target="_blank">Service</a> - <a href="https://aws.amazon.com/privatelink/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/aws-privatelink.html" target="_blank">User Guide</a>

---

<a name="15_6"></a>
## [↖](#top)[↑](#15_5_1)[↓](#15_6_1) VPN (Core Topic)
<!-- toc_start -->
* [Site-To-Site VPN](#15_6_1)
  * [Route Propagation](#15_6_1_1)
* [AWS VPN CloudHub](#15_6_2)
* [Client VPN](#15_6_3)
* [Software VPN (not AWS managed)](#15_6_4)
* [VPN to multiple VPCs](#15_6_5)
<!-- toc_end -->
AWS Virtual Private Network solutions establish secure connections between your on-premises networks, remote offices, client devices, and the AWS global network. AWS VPN is comprised of two services: **AWS Site-to-Site VPN** and **AWS Client VPN**. Together, they deliver a highly-available, managed, and elastic cloud VPN solution to protect your network traffic.

AWS Site-to-Site VPN creates encrypted tunnels between your network and your Amazon VPCs or AWS Transit Gateways. For managing remote access, AWS Client VPN connects your users to AWS or on-premises resources using a VPN software client.

VPN connectivity option|Description
-|-
AWS Site-to-Site VPN|You can create an IPsec VPN connection between your VPC and your remote network. On the AWS side of the Site-to-Site VPN connection, a virtual private gateway or transit gateway provides two VPN endpoints (tunnels) for automatic failover. You configure your customer gateway device on the remote side of the Site-to-Site VPN connection.
AWS Client VPN|AWS Client VPN is a managed client-based VPN service that enables you to securely access your AWS resources or your on-premises network. With AWS Client VPN, you configure an endpoint to which your users can connect to establish a secure TLS VPN session. This enables clients to access resources in AWS or an on-premises from any location using an OpenVPN-based VPN client.
AWS VPN CloudHub|If you have more than one remote network (for example, multiple branch offices), you can create multiple AWS Site-to-Site VPN connections via your virtual private gateway to enable communication between these networks.
Third party software VPN appliance|You can create a VPN connection to your remote network by using an Amazon EC2 instance in your VPC that's running a third party software VPN appliance. AWS does not provide or maintain third party software VPN appliances; however, you can choose from a range of products provided by partners and open source communities.

* On AWS:
	* <a href="https://aws.amazon.com/vpn/" target="_blank">Service</a> - <a href="https://aws.amazon.com/vpn/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/vpn/index.html" target="_blank">User Guide</a>

<a name="15_6_1"></a>
### [↖](#15_6)[↑](#15_6)[↓](#15_6_1_1) Site-To-Site VPN
> A customer gateway device is a physical or software appliance that you own or manage in your on-premises network (on your side of a Site-to-Site VPN connection). You or your network administrator must configure the device to work with the Site-to-Site VPN connection.
* On-premises
	* Setup a software or hardware VPN appliance to your on-premises network.
	* The on-premises VPN should be accessible using a public IP
* AWS-side
	* Setup a Virtual Private Gateway (VGW) and attach to your VPC
	* Setup a Customer Gateway (CGW) to point the on-premises VPN appliance
	* Two VPN connections (tunnels) are created for redundancy, encrypted using IPSec
	* Can optionally accelerate traffic with Global Accelerator (for worldwide networks)

<a name="15_6_1_1"></a>
#### [↖](#15_6)[↑](#15_6_1)[↓](#15_6_2) Route Propagation
* Static Routing:
	* Create static route in corporate data center for 10.0.0.1/24 (AWS) through the CGW
	* Create static route in AWS for 10.3.0.0/20 (DC) through the VGW
* Dynamic Routing (BGP):
	* Uses BGP (Border Gateway Protocol) to share routes automatically (eBGP for internet)
	* Routing tables are automatically updated
	* Just need to specify the ASN (Autonomous System Number) of the CGW and VGW

<a name="15_6_2"></a>
### [↖](#15_6)[↑](#15_6_1_1)[↓](#15_6_3) AWS VPN CloudHub
Building on the AWS managed VPN options described previously, you can securely communicate from one site to another using the AWS VPN CloudHub. The AWS VPN CloudHub operates on a simple hub-and-spoke model that you can use with or without a VPC. Use this approach if you have multiple branch offices and existing internet connections and would like to implement a convenient, potentially low-cost hub-and-spoke model for primary or backup connectivity between these remote offices.
* Can connect up to 10 Customer Gateways for each Virtual Private Gateway
* Typically goes into a single VPC
* The sites must not have overlapping IP ranges.
* Low cost hub-and-spoke model for primary or secondary network connectivity between locations
* Provide secure communication between sites, if you have multiple VPN connections
* It’s a VPN connection so it goes over the public internet
* Can be a failover connection between your on-premises locations
* On AWS:
	* <a href="https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/aws-vpn-cloudhub.html" target="_blank">User Guide</a>

<a name="15_6_3"></a>
### [↖](#15_6)[↑](#15_6_2)[↓](#15_6_4) Client VPN
AWS Client VPN is a fully-managed, elastic VPN service that automatically scales up or down based on user demand. Because it is a cloud VPN solution, you don’t need to install and manage hardware or software-based solutions, or try to estimate how many remote users to support at one time.
* Connect from your personal computer using OpenVPN to your private network in AWS and on-premises

<a name="15_6_4"></a>
### [↖](#15_6)[↑](#15_6_3)[↓](#15_6_5) Software VPN (not AWS managed)
* You can setup your own software VPN, but you have to manage everything including bandwidth, redundancy, etc.
* You would have more control over the setup and routing options

<a name="15_6_5"></a>
### [↖](#15_6)[↑](#15_6_4)[↓](#15_7) VPN to multiple VPCs
* For VPN-based customers, AWS recommends creating a separate VPN connection for each customer VPC.
* Direct Connect is recommended because it has a Direct Connect Gateway
* Other Option: Share Services VPC
	* Create a VPN connection between on-premises and shared service VPC
	* Replicate services, applications, databases between on-premises and the Shared Services VPC or deploy proxies in the shared service VPC
	* Do VPC peering between the VPC and the shared service VPC
	* VPCs can directly access the Shared Service VPC services and do not need VPN connections to on-premise
* Other Option: Transit VPC (complicated)
	* Software VPN in transit VPC
	* Good for resources that are hard to replicate on the cloud
	* Must use VPN as VPC peering does not support transitive routing
* Other Option: Transit Gateway

---

<a name="15_7"></a>
## [↖](#top)[↑](#15_6_5)[↓](#15_7_1) Direct Connect (Core Topic)
<!-- toc_start -->
* [Overview](#15_7_1)
* [Direct Connect Virtual Interfaces (VIF)](#15_7_2)
* [Connection Types](#15_7_3)
* [Encryption](#15_7_4)
* [Direct Connect Link Aggregation Groups (LAG)](#15_7_5)
* [Direct Connect Gateway](#15_7_6)
<!-- toc_end -->
<a name="15_7_1"></a>
### [↖](#15_7)[↑](#15_7)[↓](#15_7_2) Overview
AWS Direct Connect is a cloud service solution that makes it easy to establish a dedicated network connection from your premises to AWS. Using AWS Direct Connect, you can establish private connectivity between AWS and your datacenter, office, or colocation environment, which in many cases can reduce your network costs, increase bandwidth throughput, and provide a more consistent network experience than Internet-based connections.

AWS Direct Connect lets you establish a dedicated network connection between your network and one of the AWS Direct Connect locations. Using industry standard 802.1q VLANs, this dedicated connection can be partitioned into multiple virtual interfaces. This allows you to use the same connection to access public resources such as objects stored in Amazon S3 using public IP address space, and private resources such as Amazon EC2 instances running within an Amazon Virtual Private Cloud (VPC) using private IP space, while maintaining network separation between the public and private environments. Virtual interfaces can be reconfigured at any time to meet your changing needs.
* Provides a dedicated private connection from a remote network to your VPC
* Dedicated connection must be setup between your DC and AWS Direct Connect locations
* More expensive than running a VPN solution
* Private access to AWS services through virtual interfaces (VIF)
* Bypass ISP, reduce network cost, increase bandwidth and stability
* Private connection, but not encrypted
* Not redundant by default (must setup a failover DX or VPN)
* Consistent network performance
* Compatible with all AWS services
* Elastic
* On AWS:
	* <a href="https://aws.amazon.com/directconnect/" target="_blank">Service</a> - <a href="https://aws.amazon.com/directconnect/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/directconnect/index.html" target="_blank">User Guide</a>

<a name="15_7_2"></a>
### [↖](#15_7)[↑](#15_7_1)[↓](#15_7_3) Direct Connect Virtual Interfaces (VIF)
* **Public VIF**: Connect to Public AWS Endpoints (S3 buckets, EC2 service, anything AWS...)
	* Connect to all AWS public IP addresses globally.
	* Create public virtual interfaces in any DX location to receive Amazon’s global IP routes.
	* Access publicly routable Amazon services in any AWS Region
* **Private VIF**: To connect to resources in your VPC (EC2 instances, ALB, etc..)
	* Connect VPC resources (such as EC2 instances or load balancers) on your private IP address or endpoint.
	* Connect a private virtual interface to a DX gateway. Then, associate the DX gateway with one or more virtual private gateways in any AWS Region
	* Connect to multiple VPCs in any AWS Region, because a virtual private gateway is associated with a single VPC.
	* VPC endpoints cannot be accessed through Private VIF (Use Public VIF)
* **Transit VIF**: To connect to resources in a VPC using a Transit Gateway
* Watch out:
	* If you want to establish a VPN connection from your company network to a VPC over an AWS Direct Connect connection, you **must** use a **public** virtual interface for your DX connection.

<a name="15_7_3"></a>
### [↖](#15_7)[↑](#15_7_2)[↓](#15_7_4) Connection Types
* Dedicated Connections: 1 Gbps and 10 Gbps capacity
	* Physical ethernet port dedicated to a customer
	* Request made to AWS first, then completed by AWS Direct Connect Partners
* Hosted Connections: 50 Mbps, 500 Mbps, to 10 Gbps
	* Connection requests are made via AWS Direct Connect Partners
	* Capacity can be added or removed on demand (-> elasticity)
	* 1, 2, 5, 10 Gbps available at select AWS Direct Connect Partners
* Lead times are often longer than 1 month to establish a new connection

<a name="15_7_4"></a>
### [↖](#15_7)[↑](#15_7_3)[↓](#15_7_5) Encryption
* Data in transit is not encrypted (but is private)
* AWS Direct Connect + VPN provides an IPsec-encrypted private connection
	* Good for an extra level of security, but slightly more complex to put in place

<a name="15_7_5"></a>
### [↖](#15_7)[↑](#15_7_4)[↓](#15_7_6) Direct Connect Link Aggregation Groups (LAG)
* Get increased speed and failover by summing up existing Direct Connect connections into a logical one
* Can aggregate up to 4 (active active mode)
* Can add connections over time to the LAG
* All connections in the LAG must have the same bandwidth
* All connections in the LAG must terminate at the same AWS Direct Connect Endpoint
* Can set a minimum number of connections for the LAG to function

<a name="15_7_6"></a>
### [↖](#15_7)[↑](#15_7_5)[↓](#15_8) Direct Connect Gateway
* Connecting from a single Direct Connect location to multiple AWS VPCs wasn’t so straight forward.
* Direct Connect gateway is aimed at making it easier to connect from a single Direct Connect location to multiple AWS regions or VPCs
* If you want to setup a Direct Connect to **one or more VPCs** in many **different regions** (same account or cross account), you must use a Direct Connect Gateway
	* Connect to a virtual private gateway if you have one VPC in the target region
	* Connect to transit gateway when you have multiple VPCs in the same Region

---

<a name="15_8"></a>
## [↖](#top)[↑](#15_7_6)[↓](#16) Redundant connections beweteen on-premises and AWS
* Site-to-Site Active Active Connection
	* Two datacenters both with VPN connection
		* If one connection goes down, the affected datacenter can connect via the other datacenter
* Direct Connect – High Availability
	* Multiple connections at multiple AWS Direct Connect locations
		* If one connection goes down, the affected datacenter can connect via the other datacenter
	* Backup VPN
		* If one connection goes down, the affected datacenter can connect via the other datacenter

---

<a name="16"></a>
# [↖](#top)[↑](#15_8)[↓](#16_1) Other Services

<a name="16_1"></a>
## [↖](#top)[↑](#16)[↓](#16_2) Alex for Business
Alexa for Business is a service that enables organizations and employees to use Alexa to get more work done. With Alexa for Business, employees can use Alexa as their intelligent assistant to be more productive in meeting rooms, at their desks, and even with the Alexa devices they already use at home or on the go. IT and facilities managers can also use Alexa for Business to measure and increase the utilization of the existing meeting rooms in their workplace.
* Use Alexa to help employees be more productive in meeting rooms and their desk
* Measure and increase the utilization of meeting rooms in their workplace
* On AWS:
	* <a href="https://aws.amazon.com/alexaforbusiness/" target="_blank">Service</a> - <a href="https://aws.amazon.com/alexaforbusiness/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/a4b/index.html" target="_blank">User Guide</a>

---

<a name="16_2"></a>
## [↖](#top)[↑](#16_1)[↓](#16_2_1) Amazon AppStream & Amazon Workspaces
<!-- toc_start -->
* [Amazon AppStream 2.0](#16_2_1)
* [Amazon Workspaces](#16_2_2)
* [Amazon AppStream 2.0 vs WorkSpaces](#16_2_3)
<!-- toc_end -->
<a name="16_2_1"></a>
### [↖](#16_2)[↑](#16_2)[↓](#16_2_2) Amazon AppStream 2.0
Amazon AppStream 2.0 is a fully managed non-persistent application and desktop streaming service. You centrally manage your desktop applications on AppStream 2.0 and securely deliver them to any computer. You can easily scale to any number of users across the globe without acquiring, provisioning, and operating hardware or infrastructure. AppStream 2.0 is built on AWS, so you benefit from a data center and network architecture designed for the most security-sensitive organizations. Each end user has a fluid and responsive experience because your applications run on virtual machines optimized for specific use cases and each streaming sessions automatically adjust to network conditions.
* Desktop Application Streaming Service
* Deliver to any computer, without acquiring, provisioning infrastructure
* The application is delivered from within a web browser
* On AWS:
	* <a href="https://aws.amazon.com/appstream2/" target="_blank">Service</a> - <a href="https://aws.amazon.com/appstream2/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/appstream2/index.html" target="_blank">User Guide</a>

<a name="16_2_2"></a>
### [↖](#16_2)[↑](#16_2_1)[↓](#16_2_3) Amazon Workspaces
Amazon WorkSpaces is a managed, secure Desktop-as-a-Service (DaaS) solution. You can use Amazon WorkSpaces to provision either Windows or Linux desktops in just a few minutes and quickly scale to provide thousands of desktops to workers across the globe. You can pay either monthly or hourly, just for the WorkSpaces you launch, which helps you save money when compared to traditional desktops and on-premises VDI solutions. Amazon WorkSpaces helps you eliminate the complexity in managing hardware inventory, OS versions and patches, and Virtual Desktop Infrastructure (VDI), which helps simplify your desktop delivery strategy. With Amazon WorkSpaces, your users get a fast, responsive desktop of their choice that they can access anywhere, anytime, from any supported device.
* Managed, Secure Cloud Desktop
* Great to eliminate management of on-premise VDI (Virtual Desktop Infrastructure)
* On Demand, pay per by usage
* Secure, Encrypted, Network Isolation
* Integrated with Microsoft Active Directory
* **WorkSpaces Application Manager** (WAM)
	* Deploy and Manage applications as virtualized application containers
	* Provision at scale, and keep the applications updated using WAM
* **Windows Updates**
	* By default, Amazon Workspaces are configured to install software updates
	* Amazon WorkSpaces with Windows will have Windows Update turned on
	* You have full control over the Windows Update frequency
* **Maintenance Windows**
	* Updates are installed during maintenance windows (you define them)
	* Always On WorkSpaces: default is from 00h00 to 04h00 on Sunday morning
	* AutoStop WorkSpaces: automatically starts once a month to install updates
* Manual maintenance: you define your windows and perform maintenance
* On AWS:
	* <a href="https://aws.amazon.com/workspaces/" target="_blank">Service</a> - <a href="https://aws.amazon.com/workspaces/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/workspaces/index.html" target="_blank">User Guide</a>

<a name="16_2_3"></a>
### [↖](#16_2)[↑](#16_2_2)[↓](#16_3) Amazon AppStream 2.0 vs WorkSpaces
* Workspaces
	* Fully managed VDI and desktop available
	* The users connect to the VDI and open native or WAM applications
	* Workspaces are on-demand or always on
* AppStream 2.0
	* Stream a desktop application to web browsers (no need to connect to a VDI)
	* Works with any device (that has a web browser)
	* Allow to configure an instance type per application type (CPU, RAM, GPU)

---

<a name="16_3"></a>
## [↖](#top)[↑](#16_2_3)[↓](#16_3_1) Amazon DocumentDB
<!-- toc_start -->
* [Overview](#16_3_1)
<!-- toc_end -->

<a name="16_3_1"></a>
### [↖](#16_3)[↑](#16_3)[↓](#16_4) Overview
Amazon DocumentDB (with MongoDB compatibility) is a fast, scalable, highly available, and fully managed document database service that supports MongoDB workloads. As a document database, Amazon DocumentDB makes it easy to store, query, and index JSON data.

Amazon DocumentDB is a non-relational database service designed from the ground-up to give you the performance, scalability, and availability you need when operating mission-critical MongoDB workloads at scale. In Amazon DocumentDB, the storage and compute are decoupled, allowing each to scale independently, and you can increase the read capacity to millions of requests per second by adding up to 15 low latency read replicas in minutes, regardless of the size of your data.

Amazon DocumentDB is designed for 99.99% availability and replicates six copies of your data across three AWS Availability Zones (AZs). You can use AWS Database Migration Service (DMS) for free (for six months) to easily migrate your on-premises or Amazon Elastic Compute Cloud (EC2) MongoDB databases to Amazon DocumentDB with virtually no downtime.

* On AWS:
	* <a href="https://aws.amazon.com/documentdb/" target="_blank">Service</a> - <a href="https://aws.amazon.com/documentdb/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/documentdb/latest/developerguide/what-is.html" target="_blank">User Guide</a>

<a name="16_4"></a>
## [↖](#top)[↑](#16_3_1)[↓](#16_5) Amazon Lex
Amazon Lex is a service for building conversational interfaces into any application using voice and text. Amazon Lex provides the advanced deep learning functionalities of automatic speech recognition (ASR) for converting speech to text, and natural language understanding (NLU) to recognize the intent of the text, to enable you to build applications with highly engaging user experiences and lifelike conversational interactions. With Amazon Lex, the same deep learning technologies that power Amazon Alexa are now available to any developer, enabling you to quickly and easily build sophisticated, natural language, conversational bots (“chatbots”).

With Amazon Lex, you can build bots to increase contact center productivity, automate simple tasks, and drive operational efficiencies across the enterprise. As a fully managed service, Amazon Lex scales automatically, so you don’t need to worry about managing infrastructure.
* Automatic Speech Recognition (ASR) to convert speech to text
* Natural Language Understanding to recognize the intent of text, callers
* Helps build chatbots, call center bots
* On AWS:
	* <a href="https://aws.amazon.com/lex/" target="_blank">Service</a> - <a href="https://aws.amazon.com/lex/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/lex/" target="_blank">User Guide</a>

---

<a name="16_5"></a>
## [↖](#top)[↑](#16_4)[↓](#16_6) Amazon Rekognition
Amazon Rekognition makes it easy to add image and video analysis to your applications using proven, highly scalable, deep learning technology that requires no machine learning expertise to use. With Amazon Rekognition, you can identify objects, people, text, scenes, and activities in images and videos, as well as detect any inappropriate content. Amazon Rekognition also provides highly accurate facial analysis and facial search capabilities that you can use to detect, analyze, and compare faces for a wide variety of user verification, people counting, and public safety use cases.

With Amazon Rekognition Custom Labels, you can identify the objects and scenes in images that are specific to your business needs. For example, you can build a model to classify specific machine parts on your assembly line or to detect unhealthy plants. Amazon Rekognition Custom Labels takes care of the heavy lifting of model development for you, so no machine learning experience is required. You simply need to supply images of objects or scenes you want to identify, and the service handles the rest.
* Find objects, people, text, scenes in images and videos using ML
* Facial analysis and facial search to do user verification, people counting
* Create a database of “familiar faces” or compare against celebrities
* Use cases:
	* Labeling
	* Content Moderation
	* Text Detection
	* Face Detection and Analysis (gender, age range, emotions...)
	* Face Search and Verification
	* Celebrity Recognition
	* Pathing (ex: for sports game analysis)
* On AWS:
	* <a href="https://aws.amazon.com/rekognition/" target="_blank">Service</a> - <a href="https://aws.amazon.com/rekognition/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/rekognition/index.html" target="_blank">User Guide</a>

---

<a name="16_6"></a>
## [↖](#top)[↑](#16_5)[↓](#16_7) CloudSearch
Amazon CloudSearch is a managed service in the AWS Cloud that makes it simple and cost-effective to set up, manage, and scale a search solution for your website or application.
* Managed service to setup, manage and scale a search solution
* Managed alternative to ElasticSearch
* Free text, Boolean, autocomplete suggestions, geospatial search...
* On AWS:
	* <a href="https://aws.amazon.com/cloudsearch/" target="_blank">Service</a> - <a href="https://aws.amazon.com/cloudsearch/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/cloudsearch/index.html" target="_blank">User Guide</a>

---

<a name="16_7"></a>
## [↖](#top)[↑](#16_6)[↓](#16_8) Kinesis Video Streams
Amazon Kinesis Video Streams makes it easy to securely stream video from connected devices to AWS for analytics, machine learning (ML), playback, and other processing. Kinesis Video Streams automatically provisions and elastically scales all the infrastructure needed to ingest streaming video data from millions of devices. It durably stores, encrypts, and indexes video data in your streams, and allows you to access your data through easy-to-use APIs. Kinesis Video Streams enables you to playback video for live and on-demand viewing, and quickly build applications that take advantage of computer vision and video analytics through integration with Amazon Rekognition Video, and libraries for ML frameworks such as Apache MxNet, TensorFlow, and OpenCV. Kinesis Video Streams also supports WebRTC, an open-source project that enables real-time media streaming and interaction between web browsers, mobile applications, and connected devices via simple APIs. Typical uses include video chat and peer-to-peer media streaming.
* One video stream per streaming device (producers)
	* Security cameras, body worn camera, smartphone
	* Can use a Kinesis Video Streams Producer library
* Underlying data is stored in S3 (but we don’t have access to it)
* Cannot output the stream data to S3 (must build custom solution)
* Consumers:
	* Consumed by EC2 instances for real time analysis, or in batch
	* Can leverage the Kinesis Video Stream Parser Library
	* Integration with AWS Rekognition for facial detection
* On AWS:
	* <a href="https://aws.amazon.com/kinesis/video-streams/" target="_blank">Service</a> - <a href="https://aws.amazon.com/kinesis/video-streams/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/kinesis/index.html" target="_blank">User Guide</a>

---

<a name="16_8"></a>
## [↖](#top)[↑](#16_7)[↓](#16_9) Amazon Mechanical Turk
* Crowdsourcing marketplace to perform simple human tasks
* Distributed virtual workforce.
* Integrates with SWF natively, does not integrate with Step Functions

---

<a name="16_9"></a>
## [↖](#top)[↑](#16_8)[↓](#16_10) Device Farm
* Application testing service for your mobile and web applications
* Test across real browsers and real mobiles devices
* Fully automated using framework
* Improve the quality of web and mobile apps
* Generates videos and logs to document the issues encountered
* Can remotely log-in to devices for debugging

---

<a name="16_10"></a>
## [↖](#top)[↑](#16_9)[↓](#16_10_1) Macie
<!-- toc_start -->
* [Overview](#16_10_1)
<!-- toc_end -->

<a name="16_10_1"></a>
### [↖](#16_10)[↑](#16_10)[↓](#16_11) Overview
Amazon Macie is a security service that uses machine learning to automatically discover, classify,
and protect sensitive data in AWS. Amazon Macie recognizes sensitive data such as personally
identifiable information (PII) or intellectual property, and provides you with dashboards and
alerts that give visibility into how this data is being accessed or moved. The fully managed
service continuously monitors data access activity for anomalies, and generates detailed alerts
when it detects risk of unauthorized access or inadvertent data leaks. Amazon Macie is available
to protect data stored in Amazon S3.

* Data Sources
  * AWS CloudTrail event logs, including Amazon S3 object-level API activity
  * S3
* On AWS: <a href="https://aws.amazon.com/macie/" target="_blank">Service</a> - <a href="https://aws.amazon.com/macie/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/macie/latest/userguide/" target="_blank">User Guide</a>
* See also: <a href="https://www.awsgeek.com/Amazon-Macie/Amazon-Macie.jpg" target="_blank">AWS Geek 2019</a>

---

<a name="16_11"></a>
## [↖](#top)[↑](#16_10_1)[↓](#16_12) Amazon Pinpoint
Amazon Pinpoint is a flexible and scalable outbound and inbound marketing communications service. You can connect with customers over channels like email, SMS, push, or voice. Amazon Pinpoint is easy to set up, easy to use, and is flexible for all marketing communication scenarios. Segment your campaign audience for the right customer and personalize your messages with the right content. Delivery and campaign metrics in Amazon Pinpoint measure the success of your communications. Amazon Pinpoint can grow with you and scales globally to billions of messages per day across channels.

* On AWS: <a href="https://aws.amazon.com/pinpoint/" target="_blank">Service</a> - <a href="https://aws.amazon.com/pinpoint/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/pinpoint/" target="_blank">User Guide</a>

---

<a name="16_12"></a>
## [↖](#top)[↑](#16_11) Private Marketplace

A private marketplace controls which products users in your AWS account, such as business users and engineering teams, can procure from AWS Marketplace. It is built on top of AWS Marketplace, and enables your administrators to create and customize curated digital catalogs of approved independent software vendors (ISVs) and products that conform to their in-house policies. Users in your AWS account can find, buy, and deploy approved products from your private marketplace, and ensure that all available products comply with your organization’s policies and standards.

* On AWS: <a href="https://aws.amazon.com/marketplace/features/privatemarketplace" target="_blank">Service</a> - <a href="https://aws.amazon.com/marketplace/features/privatemarketplace/resources" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/marketplace/latest/buyerguide/private-marketplace.html" target="_blank">User Guide</a>

---

