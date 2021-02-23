<!-- toc_start -->
<a name="top"></a>
---
* [Solutions Architect Professional](#1)
* [Exam Objectives](#2)
  * [Content](#2_1)
* [Identity and Federation](#3)
  * [Overview - possible ways to manage Identity and Federation in AWS](#3_1)
  * [Identity and Access Management (IAM)](#3_2)
  * [STS (Security Token Service)](#3_3)
  * [Identity Federation](#3_4)
  * [AWS Active Directory Services](#3_5)
  * [AWS Organization](#3_6)
  * [AWS Resource Access Manager](#3_7)
  * [AWS Single Sign-On](#3_8)
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
  * [AWS Managed Logs](#4_14)
  * [GuardDuty](#4_15)
* [Compute & Load Balancing](#5)
  * [AWS Solution Architectures](#5_1)
  * [EC2](#5_2)
  * [Auto Scaling](#5_3)
  * [ECS](#5_4)
  * [Fargate](#5_5)
  * [Lambda](#5_6)
  * [Load Balancers](#5_7)
  * [API Gateway](#5_8)
  * [Route 53](#5_9)
  * [Solution Architeture Comparision](#5_10)
* [Storage](#6)
  * [EBS](#6_1)
  * [Local Instance Store](#6_2)
  * [EFS](#6_3)
  * [Amazon S3](#6_4)
  * [S3 Solution Architecture](#6_5)
  * [S3 vs EFS vs EBS Comparison](#6_6)
* [Caching](#7)
  * [CloudFront](#7_1)
  * [ElastiCache](#7_2)
  * [Handling Extreme Rates](#7_3)
* [Databases](#8)
  * [DynamoDB](#8_1)
  * [ElasticSearch](#8_2)
  * [RDS](#8_3)
  * [Aurora](#8_4)
* [Service Communication](#9)
  * [Step Functions](#9_1)
  * [Simple Workflow Service (SWF)](#9_2)
  * [Simple Queue Service (SQS)](#9_3)
  * [Amazon MQ](#9_4)
  * [Simple Notification Service (SNS)](#9_5)
* [Data Engineering](#10)
  * [Kinesis](#10_1)
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

.|.|.
-|-|-
**Identity only in AWS**|Users and Accounts all in AWS|Simplest setup
.|AWS Organizations|In case we have multiple accounts<br/>Adds consolidated billing and compliance
**Federation**|With SAML|.
.|Without SAML|With a custom IdP (`GetFederationToken`)
.|With SSO|For multiple accounts within AWS Organizations
.|Web Identity Federation|Not recommended, use Cognito
.|Cognito|For most web and mobile applications<br/>Has anonymous mode & MFA
**Active Directory on AWS**|Microsoft AD|Standalone or setup trust AD with on-premises<br/>Has MFA<br/>Seamless join<br/>RDS integration
.|AD Connector|Proxy requests to on-premises
.|Simple AD|Standalone & cheap AD-compatible with no MFA, no advanced capabilities

* AWS Single Sign-On to connect to multiple AWS Accounts (Organization) and SAML apps

---

<a name="3_2"></a>
## [↖](#top)[↑](#3_1)[↓](#3_2_1) Identity and Access Management (IAM)
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
* Get started using permissions with AWS managed policies
* Use customer managed policies instead of inline policies
* Use access levels to review IAM permissions
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
* An IAM user is an entity that you create in AWS to represent the person or application that uses it to interact with AWS. A user in AWS consists of a name and credentials.
* Holds long-term credentials

<a name="3_2_3"></a>
### [↖](#3_2)[↑](#3_2_2)[↓](#3_2_4) Groups
* An IAM group is a collection of IAM users. Groups let you specify permissions for multiple users, which can make it easier to manage the permissions for those users.
* Typically only provides permission to assume a role

<a name="3_2_4"></a>
### [↖](#3_2)[↑](#3_2_3)[↓](#3_2_5) Roles
* **Role** - An IAM identity that you can create in your account that has specific permissions. An IAM role has some similarities to an IAM user. Roles and users are both AWS identities with permissions policies that determine what the identity can and cannot do in AWS. However, instead of being uniquely associated with one person, a role is intended to be assumable by anyone who needs it. Also, a role does not have standard long-term credentials such as a password or access keys associated with it. Instead, when you assume a role, it provides you with temporary security credentials for your role session, provided by STS.
* **AWS service role** - A role that a service assumes to perform actions in your account on your behalf. When you set up some AWS service environments, you must define a role for the service to assume. This service role must include all the permissions required for the service to access the AWS resources that it needs. Service roles vary from service to service, but many allow you to choose your permissions, as long as you meet the documented requirements for that service. Service roles provide access only within your account and cannot be used to grant access to services in other accounts. You can create, modify, and delete a service role from within IAM.
* **AWS service role for an EC2 instance** - A special type of service role that an application running on an Amazon EC2 instance can assume to perform actions in your account. This role is assigned to the EC2 instance when it is launched. Applications running on that instance can retrieve temporary security credentials and perform actions that the role allows.
* **AWS service-linked role** - A unique type of service role that is linked directly to an AWS service. Service-linked roles are predefined by the service and include all the permissions that the service requires to call other AWS services on your behalf. The linked service also defines how you create, modify, and delete a service-linked role. A service might automatically create or delete the role. It might allow you to create, modify, or delete the role as part of a wizard or process in the service. Or it might require that you use IAM to create or delete the role. Regardless of the method, service-linked roles make setting up a service easier because you don't have to manually add the necessary permissions.
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
* You manage access in AWS by creating policies and attaching them to IAM identities (users, groups of users, or roles) or AWS resources. A policy is an object in AWS that, when associated with an identity or resource, defines their permissions. AWS evaluates these policies when an IAM principal (user or role) makes a request. Permissions in the policies determine whether the request is allowed or denied. Most policies are stored in AWS as JSON documents. AWS supports six types of policies:
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
Example: `${aws:username}`
• "Resource": ["arn:aws:s3:::mybucket/${aws:username}/*"]
AWS Specific:
• `aws:CurrentTime`, `aws:TokenIssueTime`, `aws:principaltype`, `aws:SecureTransport`, `aws:SourceIp`, `aws:userid`, `ec2:SourceInstanceARN`
Service Specific:
• `s3:prefix`, `s3:max-keys`, `s3:x-amz-acl`, `sns:Endpoint`, `sns:Protocol`...
Tag Based:
• `iam:ResourceTag/key-name`, `aws:PrincipalTag/key-name`...

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
## [↖](#top)[↑](#3_2_6_2)[↓](#3_3_1) STS (Security Token Service)
<!-- toc_start -->
* [Overview](#3_3_1)
* [Providing access to an IAM user in another AWS account that you own](#3_3_2)
* [Providing access to an IAM user from a third party AWS account](#3_3_3)
<!-- toc_end -->

<a name="3_3_1"></a>
### [↖](#3_3)[↑](#3_3)[↓](#3_3_2) Overview
AWS Security Token Service (AWS STS) is a web service that enables you to request temporary,
limited-privilege credentials for AWS Identity and Access Management (IAM) users or for users that

* Provide access for an IAM user in one AWS account that you own to access resources in another account that you own
* Provide access to IAM users in AWS accounts owned by third parties
* Provide access for services offered by AWS to AWS resources
* Provide access for externally authenticated users (identity federation)
* Ability to revoke active sessions and credentials for a role (by adding a policy using a time statement – AWSRevokeOlderSessions)

Whenever an IAM assumes another role, it's *giving up* its original permissions.

STS on AWS:
* <a href="https://docs.aws.amazon.com/STS/latest/APIReference/welcome.html" target="_blank">API Reference</a>

<a name="3_3_2"></a>
### [↖](#3_3)[↑](#3_3_1)[↓](#3_3_3) Providing access to an IAM user in another AWS account that you own
• *Zone of trust* are accounts or organizations that you own
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
• *Outside Zone of Trust* are third parties
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
* *Confused Deputy* refers to the fact that *without* `externalId`, it wouldn't be possible for
service providers to make sure that they are accessing the right account (as role ARNs are guessable)

---

<a name="3_4"></a>
## [↖](#top)[↑](#3_3_3)[↓](#3_4_1) Identity Federation
<!-- toc_start -->
* [Overview](#3_4_1)
* [SAML 2.0](#3_4_2)
* [Custom Identity Broker](#3_4_3)
* [Federating users of a mobile or web-based app with WebIdentity](#3_4_4)
* [Federating users of a mobile or web-based app with Amazon Cognito](#3_4_5)
<!-- toc_end -->

<a name="3_4_1"></a>
### [↖](#3_4)[↑](#3_4)[↓](#3_4_2) Overview
If you already manage user identities outside of AWS, you can use IAM identity providers instead of creating
IAM users in your AWS account. With an identity provider (IdP), you can manage your user identities outside of
AWS and give these external user identities permissions to use AWS resources in your account. These users assume
identity provided access *role*.

Federations can have many flavors:
* SAML 2.0
* Custom Identity Broker
* Web Identity Federation with Amazon Cognito
* Web Identity Federation without Amazon Cognito
* Single Sign On
* Non-SAML with AWS Microsoft AD

<a name="3_4_2"></a>
### [↖](#3_4)[↑](#3_4_1)[↓](#3_4_3) SAML 2.0
* Overview
  * To integrate Active Directory/ADFS with AWS (or any SAML 2.0)
  * Access through console or CI
  * Client app authenticates against IdP, receives *SAML assertion* back
  * SAML assertion is exchanged with STS to reveive temporary credentials
* To configure your organization's IdP and AWS to trust each other
  * You begin by registering AWS with your IdP. In your organization's IdP you register AWS as a service provider (SP)
  * AD/ADFS
    * For *AD*, using your organization's IdP, you generate an equivalent metadata XML file that can describe your IdP as an IAM identity provider in AWS.
    * For *ADFS*, invoke ADFS instead of IdP
  * In the IAM console, you create a SAML identity provider entity.
  * In IAM, you create one or more IAM roles. In the role's trust policy, you set the SAML provider as the principal, which establishes a trust relationship between your organization and AWS.
  * In your organization's IdP, you define assertions that map users or groups in your organization to the IAM roles.
  * API/Console
    * For *API access*, in the application that you're creating, you call the AWS STS `AssumeRoleWithSAML` API, passing it the ARN of the SAML provider you created in Step 3, the ARN of the role to assume that you created in Step 4, and the SAML assertion about the current user that you get from your IdP.
    * For *Console access*, this goes against an AWS SSO endpoint instead, SSO then invokes STS
  * If the request is successful, the API returns a set of temporary security credentials,
* Note - federation through SAML is the 'old' way of doing things. Better to use AWS SSO

> Security Assertion Markup Language (**SAML**) is an open standard for exchanging
> authentication and authorization data between parties, in particular, between an identity provider
> and a service provider.

> An identity provider (**IdP**) is a system entity that creates, maintains, and manages identity information
> for principals and also provides authentication services to relying applications within a
> federation or distributed network.

<a name="3_4_3"></a>
### [↖](#3_4)[↑](#3_4_2)[↓](#3_4_4) Custom Identity Broker
* If identity provider is not compatible with SAML 2.0
* The identity broker must determine the appropriate IAM policy (talks directly to STS, unlike SAML scenarios)
* Use STS `AssumeRole` or `GetFederationToken`
* <a href="https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_common-scenarios_federated-users.html" target="_blank">Documentation On AWS</a>

<a name="3_4_4"></a>
### [↖](#3_4)[↑](#3_4_3)[↓](#3_4_5) Federating users of a mobile or web-based app with WebIdentity
* Login with WebIdentity provider (Amazon, Google or Facebook)
* Get temporary credentials from STS
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

<a name="3_4_5"></a>
### [↖](#3_4)[↑](#3_4_4)[↓](#3_5) Federating users of a mobile or web-based app with Amazon Cognito
If you create a mobile or web-based app that accesses AWS resources, the app needs security credentials in order to make programmatic
requests to AWS. For most mobile application scenarios, we recommend that you use Amazon Cognito.
* App user authenticates with OpenID Connect IdP (Amazon, Google, ...)
  * Retrieves OpenID Connect token
* App calls Amazon Cognito and retrieves STS token in exchange for OpenID Connect token
* After being authenticated with Web Identity Federation, you can identify the user with an IAM policy variable:
  * `cognito-identity.amazonaws.com:sub`
* Requires trust relationship between Amazon Cognito and OpenID Connect IdP
* Amazon Cognito prefered over WebIdentiy federation
  * Supports anonymous users
  * Supports MFA
  * Supports data syncronization
* Amazon Connect replaces old service called Token Vending Machine
* <a href="https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_providers_oidc_cognito.html" target="_blank">Documentation On AWS</a>

---

<a name="3_5"></a>
## [↖](#top)[↑](#3_4_5)[↓](#3_5_1) AWS Active Directory Services
<!-- toc_start -->
* [Overview](#3_5_1)
* [AWS Managed Microsoft AD](#3_5_2)
  * [Overview](#3_5_2_1)
  * [Integrations](#3_5_2_2)
  * [Connecting to on-premises AD](#3_5_2_3)
  * [Syncronizing with on-premises AD](#3_5_2_4)
* [AD Connector](#3_5_3)
* [Simple AD](#3_5_4)
<!-- toc_end -->

<a name="3_5_1"></a>
### [↖](#3_5)[↑](#3_5)[↓](#3_5_2) Overview

> Active Directory (**AD**) is a directory service developed by Microsoft for Windows domain networks. It is
> included in most Windows Server operating systems as a set of processes and services.

> Active Directory Federation Services (**ADFS**), a software component developed by Microsoft, can run on
> Windows Server operating systems to provide users with single sign-on access to systems and
> applications located across organizational boundaries.

> The Lightweight Directory Access Protocol (**LDAP**) is an open, vendor-neutral, industry standard application
> protocol for accessing and maintaining distributed directory information services over an Internet Protocol network.

* **AWS Managed Microsoft AD**
  * Create your own AD in AWS, manage users locally, supports MFA
  * Establish “trust" connections with on-premises AD
* **Active Directory Connector**
  * Directory Gateway (proxy) to redirect to on-premises AD
  * Users are managed on the on-premise AD
* **Simple Active Directory**
  * AD-compatible managed directory on AWS
  * Cannot be joined with on-premise AD
* <a href="https://docs.aws.amazon.com/directoryservice/latest/admin-guide/what_is.html" target="_blank">Documentation On AWS</a>

<a name="3_5_2"></a>
### [↖](#3_5)[↑](#3_5_1)[↓](#3_5_2_1) AWS Managed Microsoft AD
<a name="3_5_2_1"></a>
#### [↖](#3_5)[↑](#3_5_2)[↓](#3_5_2_2) Overview

AWS Directory Service for Microsoft Active Directory, also known as AWS Managed Microsoft Active
Directory (AD), enables your directory-aware workloads and AWS resources to use managed Active
Directory (AD) in AWS. AWS Managed Microsoft AD is built on actual Microsoft AD and does not
require you to synchronize or replicate data from your existing Active Directory to the cloud. You
can use the standard AD administration tools and take advantage of the built-in AD features, such
as Group Policy and single sign-on. With AWS Managed Microsoft AD, you can easily join Amazon EC2
and Amazon RDS for SQL Server instances to your domain, and use AWS End User Computing (EUC)
services, such as Amazon WorkSpaces, with AD users and groups.

* Managed Service
* Deploy *Domain Controllers*, different AZs for HA, multiple DCs per AZ for scaling
  * Standalone in cloud, or joined to on-premises AD
* *Seamless Domain Join* allows to join AD from different accounts or VPCs
* Automated backups are supported
* Can join on-premises AD
  * *AD two-way forest trust*
* On AWS: <a href="https://aws.amazon.com/directoryservice/" target="_blank">Service</a> - <a href="https://aws.amazon.com/directoryservice/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/directoryservice/latest/admin-guide/what_is.html" target="_blank">User Guide</a>

<a name="3_5_2_2"></a>
#### [↖](#3_5)[↑](#3_5_2_1)[↓](#3_5_2_3) Integrations
* Windows applications on EC2 can *join the domain* and run traditional AD applications
  * Sharepoint, ...
* RDS for SQL Server, AWS Workspaces, Quicksight, ...
* AWS SSO for 3rd party access (SAML)

<a name="3_5_2_3"></a>
#### [↖](#3_5)[↑](#3_5_2_2)[↓](#3_5_2_4) Connecting to on-premises AD
* Needs Direct Connect or VPN
* Three kinds of of forest trust
  * One way on-premises -> AWS
  * One way AWS -> on-premises
  * Two way AWS <-> on-premises
* Forest trust is different to syncronization!
  * Replication not supported
  * Users on both ADs are independent from each other

<a name="3_5_2_4"></a>
#### [↖](#3_5)[↑](#3_5_2_3)[↓](#3_5_3) Syncronizing with on-premises AD
* Have to install Microsoft AD on EC2 yourself and setup replication
* Establish forest trust between this installation and AWS Managed Microsoft AD

<a name="3_5_3"></a>
### [↖](#3_5)[↑](#3_5_2_4)[↓](#3_5_4) AD Connector
* AD Connector is a directory gateway (*proxy*) to redirect directory requests to your on-premises Microsoft Active Directory
* No caching capability
  * Has latency
* Manage users solely on-premises, no possibility of setting up a trust
  * No MFA
* VPN or Direct Connect -> can't function if connection goes down
* Doesn’t work with SQL Server, doesn’t do seamless joining, can’t share directory

<a name="3_5_4"></a>
### [↖](#3_5)[↑](#3_5_3)[↓](#3_6) Simple AD
* Simple AD is an inexpensive Active Directory–compatible service with the common directory features.
* Supports joining EC2 instances, manage users and groups
* Does not support MFA, RDS SQL server, AWS SSO
* Small: 500 users, large: 5000 users
* Powered by Samba 4, compatible with Microsoft AD
* Lower cost, low scale, basic AD compatible, or LDAP compatibility
* No trust relationship to on-premises Microsoft AD

---

<a name="3_6"></a>
## [↖](#top)[↑](#3_5_4)[↓](#3_6_1) AWS Organization
<!-- toc_start -->
* [Overview](#3_6_1)
  * [Benefits](#3_6_1_1)
  * [Multi-account strategies](#3_6_1_2)
* [Service Control Policies (SCP)](#3_6_2)
* [Tag Policies](#3_6_3)
* [Reserved Instances](#3_6_4)
<!-- toc_end -->
<a name="3_6_1"></a>
### [↖](#3_6)[↑](#3_6)[↓](#3_6_1_1) Overview
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

* Master accounts must invite child accounts
  * Invited accounts must approve enabling all features
* Master accounts can create child accounts
* Master can access child accounts using:
  * CloudFormation StackSets to create IAM roles in target accounts
  * Assume the roles using the STS Cross Account capability
* Recommended strategy to create a dedicated account for logging or security
* API is available to automate AWS account creation
* Integration with AWS Single Sign-On (SSO)
* On AWS: <a href="https://aws.amazon.com/organizations/" target="_blank">Service</a> - <a href="https://aws.amazon.com/organizations/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/organizations/latest/userguide/" target="_blank">User Guide</a>

<a name="3_6_1_1"></a>
#### [↖](#3_6)[↑](#3_6_1)[↓](#3_6_1_2) Benefits
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

<a name="3_6_1_2"></a>
#### [↖](#3_6)[↑](#3_6_1_1)[↓](#3_6_2) Multi-account strategies
• Create accounts per department, per cost center, per dev/test/prod, based on regulatory
  restrictions (using SCP), for better resource isolation (ex: VPC), to have separate per-account
  service limits, isolated account for logging,
• Multi account vs one account multi vPC
• Use tagging standards for billing purposes
• Enable CloudTrail on all accounts, send logs to central S3 account
• Send CloudWatch logs to central logging account
• Establish cross account roles for admin purposes

<a name="3_6_2"></a>
### [↖](#3_6)[↑](#3_6_1_2)[↓](#3_6_3) Service Control Policies (SCP)
Service control policies (SCPs) are one type of policy that you can use to manage your organization.
SCPs offer central control over the maximum available permissions for all accounts in your
organization, allowing you to ensure your accounts stay within your organization’s access control
guidelines. SCPs are available only in an organization that has all features enabled. SCPs aren't
available if your organization has enabled only the consolidated billing features. SCPs do *not* apply
for the master account itself.

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
* On AWS: <a href="https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_evaluation-logic.html" target="_blank">IAM policy evaluation logic</a>

<a name="3_6_3"></a>
### [↖](#3_6)[↑](#3_6_2)[↓](#3_6_4) Tag Policies
Tag policies are a type of policy that can help you standardize tags across resources in your
organization's accounts. In a tag policy, you specify tagging rules applicable to resources when they are tagged.

<a name="3_6_4"></a>
### [↖](#3_6)[↑](#3_6_3)[↓](#3_7) Reserved Instances
* For billing purposes, the consolidated billing feature of AWS Organizations treats all the
  accounts in the organization as one account.
* This means that all accounts in the organization can receive the hourly cost benefit of Reserved
  Instances that are purchased by any other account.
* The payer account (master account) of an organization can turn off Reserved Instance (RI)
  discount and Savings Plans discount sharing for any accounts in that organization, including the payer account
* This means that RIs and Savings Plans discounts aren't shared between any accounts that have sharing turned off.
* To share an RI or Savings Plans discount with an account, both accounts must have sharing turned on.

---

<a name="3_7"></a>
## [↖](#top)[↑](#3_6_4)[↓](#3_7_1) AWS Resource Access Manager
<!-- toc_start -->
* [Overview](#3_7_1)
<!-- toc_end -->
<a name="3_7_1"></a>
### [↖](#3_7)[↑](#3_7)[↓](#3_8) Overview
AWS RAM lets you share your resources with any AWS account or through AWS Organizations. If you
have multiple AWS accounts, you can create resources centrally and use AWS RAM to share those
resources with other accounts.

* Avoids resource duplication
* Key resources that can be shared
  * VPC Subnets
    * allow to have all the resources launched in the same subnets
    * must be from the same AWS Organizations.
    * Cannot share security groups and default VPC
    * Participants can manage their own resources in there
    * Participants can't view, modify, delete resources that belong to other participants or the owner
  * AWS Transit Gateway
  * Route 53 Resolver Rules
  * License Manager Configurations
* On AWS: <a href="https://aws.amazon.com/ram/" target="_blank">Service</a> - <a href="https://aws.amazon.com/ram/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/ram/latest/userguide/what-is.html" target="_blank">User Guide</a>

---

<a name="3_8"></a>
## [↖](#top)[↑](#3_7_1)[↓](#3_8_1) AWS Single Sign-On
<!-- toc_start -->
* [Overview](#3_8_1)
<!-- toc_end -->

<a name="3_8_1"></a>
### [↖](#3_8)[↑](#3_8)[↓](#4) Overview
AWS Single Sign-On is a cloud-based single sign-on (SSO) service that makes it easy to centrally
manage SSO access to all of your AWS accounts and cloud applications. Specifically, it helps you
manage SSO access and user permissions across all your AWS accounts in AWS Organizations. AWS SSO
also helps you manage access and permissions to commonly used third-party software as a service (SaaS)
applications, AWS SSO-integrated applications as well as custom applications that support Security
Assertion Markup Language (SAML) 2.0. AWS SSO includes a user portal where your end-users can find
and access all their assigned AWS accounts, cloud applications, and custom applications in one place.

* Centrally manage Single Sign-On to access multiple accounts and 3rd-party business applications.
  * No need for custom IdP login portal, AWS SSO communicates directly with SAML-compatible login portal
* Integrated with AWS Organizations
* Supports SAML 2.0 markup
* Integration with on-premises Active Directory
  * Standalone AWS Managed Microsoft AD
  * AD Connector to on-premises AD
  * AWS Managed Microsoft AD with two-way forest trust with on-premise AD
* Centralized permission management
* Centralized auditing with CloudTrail
* On AWS: <a href="https://aws.amazon.com/single-sign-on/" target="_blank">Service</a> - <a href="https://aws.amazon.com/single-sign-on/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/singlesignon/latest/userguide/what-is.html" target="_blank">User Guide</a>

---

<a name="4"></a>
# [↖](#top)[↑](#3_8_1)[↓](#4_1) Security

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
AWS CloudTrail is a service that enables governance, compliance, operational auditing, and risk
auditing of your AWS account. With CloudTrail, you can log, continuously monitor, and retain
account activity related to actions across your AWS infrastructure. CloudTrail provides event
history of your AWS account activity, including actions taken through the AWS Management Console,
AWS SDKs, command line tools, and other AWS services. This event history simplifies security
analysis, resource change tracking, and troubleshooting. In addition, you can use CloudTrail to
detect unusual activity in your AWS accounts. These capabilities help simplify operational
analysis and troubleshooting.

CloudTrail is enabled by default in every account. All activities in an AWS account are being
recorded as CloudTrail events.

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
AWS Key Management Service (KMS) makes it easy for you to create and manage cryptographic keys and
control their use across a wide range of AWS services and in your applications. AWS KMS is a
secure and resilient service that uses hardware security modules that have been validated under
FIPS 140-2, or are in the process of being validated, to protect your keys. AWS KMS is integrated
with AWS CloudTrail to provide you with logs of all key usage to help meet your regulatory and compliance needs.

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
* The value in KMS is that the CMK used to encrypt data can never be retrieved by the user, and
  the CMK can be rotated for extra security
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
* A customer master key (CMK) is a logical representation of a master key. The CMK includes
  metadata, such as the key ID, creation date, description, and key state. The CMK also contains
  the key material used to encrypt and decrypt data.
* Create, manage and use, can enable or disable
* Possibility of rotation policy (new key generated every year, old key preserved)
* Can add a key policy (resource policy)
* Leverage for envelope encryption

<a name="4_2_3_2"></a>
#### [↖](#4_2)[↑](#4_2_3_1)[↓](#4_2_3_3) Customer managed CMKs
Customer managed CMKs are CMKs in your AWS account that you create, own, and manage. You have full
control over these CMKs, including establishing and maintaining their key policies, IAM policies,
and grants, enabling and disabling them, rotating their cryptographic material, adding tags,
creating aliases that refer to the CMK, and scheduling the CMKs for deletion.

<a name="4_2_3_3"></a>
#### [↖](#4_2)[↑](#4_2_3_2)[↓](#4_2_3_4) AWS managed CMKs
AWS managed CMKs are CMKs in your account that are created, managed, and used on your behalf by an
AWS service that is integrated with AWS KMS. Some AWS services support only an AWS managed CMK.
Others use an AWS owned CMK or offer you a choice of CMKs.

<a name="4_2_3_4"></a>
#### [↖](#4_2)[↑](#4_2_3_3)[↓](#4_3) AWS owned CMKs
AWS owned CMKs are a collection of CMKs that an AWS service owns and manages for use in multiple
AWS accounts. Although AWS owned CMKs are not in your AWS account, an AWS service can use its AWS
owned CMKs to protect the resources in your account.

---

<a name="4_3"></a>
## [↖](#top)[↑](#4_2_3_4)[↓](#4_3_1) SSM Parameter Store
<!-- toc_start -->
* [Overview](#4_3_1)
<!-- toc_end -->
<a name="4_3_1"></a>
### [↖](#4_3)[↑](#4_3)[↓](#4_4) Overview
AWS Systems Manager Parameter Store provides secure, hierarchical storage for configuration data
management and secrets management. You can store data such as passwords, database strings, Amazon
Machine Image (AMI) IDs, and license codes as parameter values. You can store values as plain text
or encrypted data. You can reference Systems Manager parameters in your scripts, commands, SSM
documents, and configuration and automation workflows by using the unique name that you specified
when you created the parameter.

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
AWS Secrets Manager helps you protect secrets needed to access your applications, services, and IT
resources. The service enables you to easily rotate, manage, and retrieve database credentials,
API keys, and other secrets throughout their lifecycle. Users and applications retrieve secrets
with a call to Secrets Manager APIs, eliminating the need to hardcode sensitive information in
plain text. Secrets Manager offers secret rotation with built-in integration for Amazon RDS,
Amazon Redshift, and Amazon DocumentDB. Also, the service is extensible to other types of secrets,
including API keys and OAuth tokens. In addition, Secrets Manager enables you to control access to
secrets using fine-grained permissions and audit secret rotation centrally for resources in the
AWS Cloud, third-party services, and on-premises.

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
    * Amazon Route 53 supports DNSSEC for domain registration. However, Route 53 does not support DNSSEC for DNS service, regardless of whether the domain is registered with Route 53. If you want to configure DNSSEC for a domain that is registered with Route 53, you must use another DNS service provider.
    * You could run a custom DNS server on EC2

---

<a name="4_7"></a>
## [↖](#top)[↑](#4_6_4)[↓](#4_7_1) AWS Certificate Manager
<!-- toc_start -->
* [Overview](#4_7_1)
<!-- toc_end -->
<a name="4_7_1"></a>
### [↖](#4_7)[↑](#4_7)[↓](#4_8) Overview
AWS Certificate Manager is a service that lets you easily provision, manage, and deploy public and
private Secure Sockets Layer/Transport Layer Security (SSL/TLS) certificates for use with AWS
services and your internal connected resources. SSL/TLS certificates are used to secure network
communications and establish the identity of websites over the Internet as well as resources on
private networks. AWS Certificate Manager removes the time-consuming manual process of purchasing,
uploading, and renewing SSL/TLS certificates.

With AWS Certificate Manager, you can quickly request a certificate, deploy it on ACM-integrated
AWS resources, such as Elastic Load Balancers, Amazon CloudFront distributions, and APIs on API
Gateway, and let AWS Certificate Manager handle certificate renewals. It also enables you to
create private certificates for your internal resources and manage the certificate lifecycle
centrally. Public and private certificates provisioned through AWS Certificate Manager for use
with ACM-integrated services are free. You pay only for the AWS resources you create to run your
application. With AWS Certificate Manager Private Certificate Authority, you pay monthly for the
operation of the private CA and for the private certificates you issue.

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
  * To use with a global application (multiple ALB for example), you need to issue an SSL certificate in each region where you application is deployed.
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
AWS CloudHSM provides hardware security modules in the AWS Cloud. A hardware security module (HSM)
is a computing device that processes cryptographic operations and provides secure storage for cryptographic keys.

When you use an HSM from AWS CloudHSM, you can perform a variety of cryptographic tasks:
* Generate, store, import, export, and manage cryptographic keys, including symmetric keys and asymmetric key pairs.
* Use symmetric and asymmetric algorithms to encrypt and decrypt data.
* Use cryptographic hash functions to compute message digests and hash-based message authentication codes (HMACs).
* Cryptographically sign data (including code signing) and verify signatures.
* Generate cryptographically secure random data.

If you want a managed service for creating and controlling your encryption keys, but you don't
want or need to operate your own HSM, consider using AWS KMS.

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
• Detailed records for the requests that are made to a bucket
• Might take hours to deliver
• Might be incomplete (best effort)

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
You can use AWS WAF web access control lists (web ACLs) to help minimize the effects of a
distributed denial of service (DDoS) attack. For additional protection against DDoS attacks, AWS
also provides AWS Shield Standard and AWS Shield Advanced. AWS Shield Standard is automatically
included at no extra cost beyond what you already pay for AWS WAF and your other AWS services. AWS
Shield Advanced provides expanded DDoS attack protection for your Amazon EC2 instances, Elastic
Load Balancing load balancers, CloudFront distributions, Route 53 hosted zones, and AWS Global
Accelerator accelerators. AWS Shield Advanced incurs additional charges.

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
AWS WAF is a web application firewall that lets you monitor the HTTP and HTTPS requests that are
forwarded to an Amazon CloudFront distribution, an Amazon API Gateway REST API, an Application
Load Balancer, or an AWS AppSync GraphQL API. AWS WAF also lets you control access to your conten
. Based on conditions that you specify, such as the IP addresses that requests originate from or
the values of query strings, Amazon CloudFront, Amazon API Gateway, Application Load Balancer, or
AWS AppSync responds to requests either with the requested content or with an HTTP 403 status code
(Forbidden). You also can configure CloudFront to return a custom error page when a request is blocked.

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
* On AWS: <a href="https://aws.amazon.com/waf/" target="_blank">Service</a> - <a href="https://aws.amazon.com/waf/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/waf/latest/developerguide/what-is-aws-waf.html" target="_blank">User Guide</a>

<a name="4_10_5"></a>
### [↖](#4_10)[↑](#4_10_4)[↓](#4_11) AWS Firewall Manager
AWS Firewall Manager simplifies your administration and maintenance tasks across multiple accounts
and resources for AWS WAF, AWS Shield Advanced, Amazon VPC security groups, and AWS Network
Firewall. With Firewall Manager, you set up your AWS WAF firewall rules, Shield Advanced
protections, Amazon VPC security groups, and Network Firewall firewalls just once. The service
automatically applies the rules and protections across your accounts and resources, even as you
add new resources.

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
Amazon Inspector is an automated security assessment service that helps improve the security and
compliance of applications deployed on AWS. Amazon Inspector automatically assesses applications
for exposure, vulnerabilities, and deviations from best practices. After performing an assessment,
Amazon Inspector produces a detailed list of security findings prioritized by level of severity.
These findings can be reviewed directly or as part of detailed assessment reports which are
available via the Amazon Inspector console or API.

Amazon Inspector security assessments help you check for unintended network accessibility of your
Amazon EC2 instances and for vulnerabilities on those EC2 instances. Amazon Inspector assessments
are offered to you as pre-defined rules packages mapped to common security best practices and
vulnerability definitions. Examples of built-in rules include checking for access to your EC2
instances from the internet, remote root login being enabled, or vulnerable software versions
installed. These rules are regularly updated by AWS security researchers.

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
AWS resources. Config continuously monitors and records your AWS resource configurations and
allows you to automate the evaluation of recorded configurations against desired configurations.
With Config, you can review changes in configurations and relationships between AWS resources,
dive into detailed resource configuration histories, and determine your overall compliance against
the configurations specified in your internal guidelines. This enables you to simplify compliance
auditing, security analysis, change management, and operational troubleshooting.

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
## [↖](#top)[↑](#4_13_4)[↓](#4_15) AWS Managed Logs
* **Load Balancer** Access Logs (ALB, NLB, CLB) => to S3
  * Access logs for your Load Balancers
* **CloudTrail** Logs => to S3 and CloudWatch Logs
  * Logs for API calls made within your account
* **VPC Flow Logs** => to S3 and CloudWatch Logs
  * Information about IP traffic going to and from network interfaces in your VPC
* **Route 53** Access Logs => to CloudWatch Logs
  * Log information about the queries that Route 53 receives
* **S3** Access Logs => to S3
  * Server access logging provides detailed records for the requests that are made to a bucket
* **CloudFront** Access Logs => to S3
  * Detailed information about every user request that CloudFront receives
* **AWS Config** => to S3

---

<a name="4_15"></a>
## [↖](#top)[↑](#4_14)[↓](#4_15_1) GuardDuty
<!-- toc_start -->
* [Overview](#4_15_1)
<!-- toc_end -->

<a name="4_15_1"></a>
### [↖](#4_15)[↑](#4_15)[↓](#5) Overview
Amazon GuardDuty is a threat detection service that continuously monitors for malicious activity
and unauthorized behavior to protect your AWS accounts and workloads. With the cloud, the
collection and aggregation of account and network activities is simplified, but it can be time
consuming for security teams to continuously analyze event log data for potential threats. With
GuardDuty, you now have an intelligent and cost-effective option for continuous threat detection
in the AWS Cloud. The service uses machine learning, anomaly detection, and integrated threat
intelligence to identify and prioritize potential threats. GuardDuty analyzes tens of billions of
events across multiple AWS data sources, such as AWS CloudTrail, Amazon VPC Flow Logs, and DNS log.
With a few clicks in the AWS Management Console, GuardDuty can be enabled with no software or
hardware to deploy or maintain. By integrating with Amazon CloudWatch Events, GuardDuty alerts are
actionable, easy to aggregate across multiple accounts, and straightforward to push into existing
event management and workflow systems.

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
* [Payment Model/Launch Type](#5_2_2)
  * [Spot Instances](#5_2_2_1)
  * [Spot Fleets](#5_2_2_2)
  * [Pricing by](#5_2_2_3)
* [Instance Types](#5_2_3)
* [Placement Groups](#5_2_4)
* [Key metrics for EC2](#5_2_5)
* [EC2 Instance Recovery](#5_2_6)
<!-- toc_end -->
<a name="5_2_1"></a>
### [↖](#5_2)[↑](#5_2)[↓](#5_2_2) Overview
Amazon Elastic Compute Cloud (Amazon EC2) is a web service that provides secure, resizable compute
capacity in the cloud. It is designed to make web-scale cloud computing easier for developers.
Amazon EC2’s simple web service interface allows you to obtain and configure capacity with minimal
friction. It provides you with complete control of your computing resources and lets you run on
Amazon’s proven computing environment.

Amazon EC2 offers the broadest and deepest compute platform with choice of processor, storage,
networking, operating system, and purchase model. We offer the fastest processors in the cloud and
we are the only cloud with 400 Gbps ethernet networking. We have the most powerful GPU instances
for machine learning training and graphics workloads, as well as the lowest cost-per-inference
instances in the cloud.

* On AWS: <a href="https://aws.amazon.com/ec2/" target="_blank">Service</a> - <a href="https://aws.amazon.com/ec2/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/ec2/" target="_blank">User Guide</a>

<a name="5_2_2"></a>
### [↖](#5_2)[↑](#5_2_1)[↓](#5_2_2_1) Payment Model/Launch Type
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

<a name="5_2_2_1"></a>
#### [↖](#5_2)[↑](#5_2_2)[↓](#5_2_2_2) Spot Instances
* Can get a discount of up to 90% compared to On-demand
* Define max spot price and get the instance while current `spot price < max`
  * The hourly spot price varies based on offer and capacity
  * If the current spot price > your max price you can choose to stop or terminate your instance with a 2 minutes grace period.
* Other strategy: Spot Block
  * “block” spot instance during a specified time frame (1 to 6 hours) without interruptions
* In rare situations, the instance may be reclaimed

<a name="5_2_2_2"></a>
#### [↖](#5_2)[↑](#5_2_2_1)[↓](#5_2_2_3) Spot Fleets
* Collection (Fleet) of Spot Instances and optionally on-demand instances
  * Set a maximum price you’re willing to pay per Spot Instances or all
  * Can have a mix of instance types (M5.large, M5.xlarge, C5.2xlarge, etc..)
* Supports: EC2 standalone, Auto Scaling Groups (launch template), ECS (underlying ASG), AWS Batch (Managed Compute Environment)
* Soft limits:
  * Target capacity per Spot Fleet or EC2 fleet: 10,000
  * Target capacity across all Spot Fleet and EC2 Fleet in a region: 100,000

<a name="5_2_2_3"></a>
#### [↖](#5_2)[↑](#5_2_2_2)[↓](#5_2_3) Pricing by
* Instance Type
* Compute time
* Data transfer
* Storage
* Elastic IP address
* Monitoring
* Elastic load balancer

<a name="5_2_3"></a>
### [↖](#5_2)[↑](#5_2_2_3)[↓](#5_2_4) Instance Types
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

<a name="5_2_4"></a>
### [↖](#5_2)[↑](#5_2_3)[↓](#5_2_5) Placement Groups
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

<a name="5_2_5"></a>
### [↖](#5_2)[↑](#5_2_4)[↓](#5_2_6) Key metrics for EC2
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

<a name="5_2_6"></a>
### [↖](#5_2)[↑](#5_2_5)[↓](#5_3) EC2 Instance Recovery
You can create an Amazon CloudWatch alarm that monitors an Amazon EC2 instance and automatically
recovers the instance if it becomes impaired due to an underlying hardware failure or a problem
that requires AWS involvement to repair (`StatusCheckFailed_System`). Terminated instances cannot be recovered. A recovered
instance is identical to the original instance, including the instance ID, private IP addresses,
Elastic IP addresses, and all instance metadata. If the impaired instance is in a placement group,
the recovered instance runs in the placement group.

If your instance has a public IPv4 address, it retains the public IPv4 address after recovery.

---

<a name="5_3"></a>
## [↖](#top)[↑](#5_2_6)[↓](#5_3_1) Auto Scaling
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
*Amazon EC2 Auto Scaling* helps you ensure that you have the correct number of Amazon EC2 instances
available to handle the load for your application. You create collections of EC2 instances, called
*Auto Scaling Groups*. You can specify the **minimum** number of instances in each Auto Scaling Group,
and Amazon EC2 Auto Scaling ensures that your group never goes below this size. You can specify
the **maximum** number of instances in each Auto Scaling Group, and Amazon EC2 Auto Scaling ensures
that your group never goes above this size. If you specify the **desired** capacity, either when you
create the group or at any time thereafter, Amazon EC2 Auto Scaling ensures that your group has
this many instances. If you specify **scaling policies**, then Amazon EC2 Auto Scaling can launch or
terminate instances as demand on your application increases or decreases.

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
You can suspend and then resume one or more of the scaling processes for your Auto Scaling Group.
This can be useful for investigating a configuration problem or other issues with your web
application and making changes to your application without invoking the scaling processes.

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
## [↖](#top)[↑](#5_3_2_6)[↓](#5_4_1) ECS
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
*Amazon Elastic Container Service* (Amazon ECS) is a highly scalable, fast, container management
service that makes it easy to run, stop, and manage Docker containers on a cluster. You can host
your cluster on a serverless infrastructure that is managed by Amazon ECS by launching your
services or tasks using the Fargate launch type. For more control you can host your tasks on a
cluster of Amazon Elastic Compute Cloud (Amazon EC2) instances that you manage by using the EC2
launch type.

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
  * If a task should fail or stop, the ECS scheduler launches another instance of the task
    definition to replace it and to maintain the desired count of tasks in service
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
AWS Fargate is a serverless compute engine for containers that works with both Amazon Elastic
Container Service (ECS) and Amazon Elastic Kubernetes Service (EKS). Fargate makes it easy for you
to focus on building your applications. Fargate removes the need to provision and manage servers,
lets you specify and pay for resources per application, and improves security through application
isolation by design.

Fargate allocates the right amount of compute, eliminating the need to choose instances and scale
cluster capacity. You only pay for the resources required to run your containers, so there is no
over-provisioning and paying for additional servers. Fargate runs each task or pod in its own
kernel providing the tasks and pods their own isolated compute environment. This enables your
application to have workload isolation and improved security by design. This is why customers such
as Vanguard, Accenture, Foursquare, and Ancestry have chosen to run their mission critical applications on Fargate.

* Don't need to provision cluster
  * Does not need EC2 instance roles to create cluster
* Requires VPC
* On AWS: <a href="https://aws.amazon.com/fargate/" target="_blank">Service</a> - <a href="https://aws.amazon.com/fargate/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/AmazonECS/latest/developerguide/AWS_Fargate.html" target="_blank">User Guide</a

---

<a name="5_6"></a>
## [↖](#top)[↑](#5_5_1)[↓](#5_6_1) Lambda
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
* [Limits and Latencies](#5_6_5)
<!-- toc_end -->
<a name="5_6_1"></a>
### [↖](#5_6)[↑](#5_6)[↓](#5_6_2) Overview
*AWS Lambda* lets you run code without provisioning or managing servers. You pay only for the
compute time you consume - there is no charge when your code is not running. With Lambda, you can
run code for virtually any type of application or backend service - all with zero administration.
Just upload your code and Lambda takes care of everything required to run and scale your code with
high availability. You can set up your code to automatically trigger from other AWS services or
call it directly from any web or mobile app.

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
* The system creates a new version of your Lambda function each time that you *publish* the function.
  The new version is a copy of the *unpublished* version of the function.
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
  * Lambda manages the function's asynchronous invocation queue and attempts to retry failed
  events automatically. If the function returns an error, Lambda attempts to run it two more times
  * For retries, Lambda needs to be idempotent
  * You can also configure Lambda to send an invocation record to another service.
    * Lambda supports the following **destinations** for asynchronous invocation recordings: SQS, SNS, AWS Lambda, EventBridge
    * The invocation record contains details about the request and response in JSON format. You can
      configure separate destinations for events that are processed successfully, and events that fail
      all processing attempts. Alternatively, you can configure an SQS queue or SNS topic as a dead
      letter queue for discarded events. For dead-letter queues, Lambda only sends the content of the
      event, without details about the response.
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
* AWS Lambda automatically monitors Lambda functions on your behalf and reports metrics through
  Amazon CloudWatch. To help you monitor your code as it executes, Lambda automatically tracks the
  *number of requests*, the *execution duration per request*, and the *number of requests that result in an error*.
* It also publishes the associated CloudWatch metrics.
* Need *custom metric* for memory usage

<a name="5_6_5"></a>
### [↖](#5_6)[↑](#5_6_4_3)[↓](#5_7) Limits and Latencies

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
## [↖](#top)[↑](#5_6_5)[↓](#5_7_1) Load Balancers
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
Elastic Load Balancing automatically distributes incoming application traffic across multiple
targets, such as Amazon EC2 instances, containers, IP addresses, Lambda functions, and virtual
appliances. It can handle the varying load of your application traffic in a single Availability
Zone or across multiple Availability Zones. Elastic Load Balancing offers four types of load
balancers that all feature the high availability, automatic scaling, and robust security necessary
to make your applications fault tolerant.

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
An Application Load Balancer functions at the application layer, the seventh layer of the Open
Systems Interconnection (OSI) model. After the load balancer receives a request, it evaluates the
listener rules in priority order to determine which rule to apply, and then selects a target from
the target group for the rule action. You can configure listener rules to route requests to
different target groups based on the content of the application traffic. Routing is performed
independently for each target group, even when a target is registered with multiple target groups.
You can configure the routing algorithm used at the target group level. The default routing
algorithm is round robin; alternatively, you can specify the least outstanding requests routing algorithm.

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
A Network Load Balancer functions at the fourth layer of the Open Systems Interconnection (OSI)
model. It can handle millions of requests per second. After the load balancer receives a
connection request, it selects a target from the target group for the default rule. It attempts to
open a TCP connection to the selected target on the port specified in the listener configuration.

When you enable an Availability Zone for the load balancer, Elastic Load Balancing creates a load
balancer node in the Availability Zone. By default, each load balancer node distributes traffic
across the registered targets in its Availability Zone only. If you enable cross-zone load
balancing, each load balancer node distributes traffic across the registered targets in all
enabled Availability Zones.

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
Each target group is used to route requests to one or more registered targets. When you create a
listener, you specify a target group for its default action. Traffic is forwarded to the target
group specified in the listener rule. You can create different target groups for different types
of requests. For example, create one target group for general requests and other target groups for
requests to the microservices for your application.

You define health check settings for your load balancer on a per target group basis. Each target
group uses the default health check settings, unless you override them when you create the target
group or modify them later on. After you specify a target group in a rule for a listener, the load
balancer continually monitors the health of all targets registered with the target group that are
in an Availability Zone enabled for the load balancer. The load balancer routes requests to the
registered targets that are healthy.
* EC2 instances (can be managed by an ASG) – TCP
* ECS tasks (managed by ECS itself) – TCP
* IP addresses – Private IP only, even outside your VPC

<a name="5_7_4_3"></a>
#### [↖](#5_7)[↑](#5_7_4_2)[↓](#5_7_5) Proxy protocol
Network Load Balancers use proxy protocol version 2 to send additional connection information such
as the source and destination. Proxy protocol version 2 provides a binary encoding of the proxy
protocol header. The load balancer prepends a proxy protocol header to the TCP data. It does not
discard or overwrite any existing data, including any proxy protocol headers sent by the client or
any other proxies, load balancers, or servers in the network path. Therefore, it is possible to
receive more than one proxy protocol header. Also, if there is another network path to your
targets outside of your Network Load Balancer, the first proxy protocol header might not be the
one from your Network Load Balancer.
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
*Amazon API Gateway* is a fully managed service that makes it easy for developers to create, publish,
maintain, monitor, and secure APIs at any scale. With a few clicks in the AWS Management Console,
you can create *REST* and *WebSocket* APIs that act as a “front door” for applications to access data,
business logic, or functionality from your backend services, such as workloads running on Amazon
Elastic Compute Cloud (Amazon EC2), code running on AWS Lambda, any web application, or real-time
communication applications.

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
A hostname for an API in API Gateway that is deployed to a specific region. The hostname is of the
form `{api-id}.execute-api.{region}.amazonaws.com`.

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
After creating your API, you *must* deploy it to make it callable by your users. To deploy an API,
you create an *API deployment* and associate it with a *stage*. Each stage is a snapshot of the API
and is made available for client apps to call.

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
  * **All** AWS services support dedicated APIs to expose their features. However, the application
  protocols or programming interfaces are likely to differ from service to service. An API Gateway
  API with the AWS integration has the advantage of providing a consistent application protocol
  for your client to access different AWS services.

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
  * Can send logs directly into Kinesis Data Firehose (as an alternative to CW logs)
* CloudWatch Metrics
  * Metrics are by stage, possibility to enable detailed metrics
  * IntegrationLatency, Latency, CacheHitCount, CacheMissCount
* X-Ray
  * Enable tracing to get extra information about requests in API Gateway
  * X-Ray API Gateway + AWS Lambda gives you the full picture

---

<a name="5_9"></a>
## [↖](#top)[↑](#5_8_4)[↓](#5_9_1) Route 53
<!-- toc_start -->
* [Overview](#5_9_1)
  * [Terminology](#5_9_1_1)
* [ How it works](#5_9_2)
  * [Basic Flow](#5_9_2_1)
  * [Zone File & Records](#5_9_2_2)
  * [Route 53 Routing Policies](#5_9_2_3)
* [Health Checks with Route 53](#5_9_3)
  * [Trigger automated DNS failover](#5_9_3_1)
  * [Setup](#5_9_3_2)
  * [Private Hosted Zones](#5_9_3_3)
* [Sharing a Private Zone across multiple VPCs](#5_9_4)
<!-- toc_end -->
<a name="5_9_1"></a>
### [↖](#5_9)[↑](#5_9)[↓](#5_9_1_1) Overview
Amazon Route 53 is a highly available and scalable Domain Name System (DNS) web service. You can
use Route 53 to perform three main functions in any combination: domain registration, DNS routing,
and health checking. If you choose to use Route 53 for all three functions, perform the steps in this order:
* Register domain names
  * Your website needs a name, such as example.com. Route 53 lets you register a name for your
    website or web application, known as a domain name.
* Route internet traffic to the resources for your domain
  * When a user opens a web browser and enters your domain name (example.com) or subdomain name
    acme.example.com) in the address bar, Route 53 helps connect the browser with your website or web application
* Check the health of your resources
  * Route 53 sends automated requests over the internet to a resource, such as a web server, to
    verify that it's reachable, available, and functional. You also can choose to receive
    notifications when a resource becomes unavailable and choose to route internet traffic away
    from unhealthy resources.
* Private DNS:
  * Can use Route 53 for internal private DNS
  * Must enable the VPC settings enableDnsHostNames and enableDnsSupport
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

<a name="5_9_2"></a>
### [↖](#5_9)[↑](#5_9_1_1)[↓](#5_9_2_1)  How it works

<a name="5_9_2_1"></a>
#### [↖](#5_9)[↑](#5_9_2)[↓](#5_9_2_2) Basic Flow
* `Root Server` -> `TLD Server` -> `Domain-Level Name Server` -> `Zone File`
* Client requests Route 53, receives A record (host name to ip4) and TTL, client requests IP address from A record

<a name="5_9_2_2"></a>
#### [↖](#5_9)[↑](#5_9_2_1)[↓](#5_9_2_3) Zone File & Records
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
  * Amazon Route 53 alias records provide a Route 53–specific extension to DNS functionality.
  Alias records let you route traffic to selected AWS resources, such as CloudFront distributions
  and Amazon S3 bucket. They also let you route traffic from one record in a hosted zone to another record.
  * Unlike a CNAME record, you can create an alias record at the top node of a DNS namespace, also
  known as the *zone apex*. For example, if you register the DNS name example.com, the zone apex is
  example.com. You can't create a CNAME record for example.com, but you can create an alias record
  for example.com that routes traffic to www.example.com
  * Preferred choice over CNAME (TODO: why?)

<a name="5_9_2_3"></a>
#### [↖](#5_9)[↑](#5_9_2_2)[↓](#5_9_3) Route 53 Routing Policies
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
      * Route 53 has health checkers in locations around the world. When you create a health check that
        monitors an endpoint, health checkers start to send requests to the endpoint that you specify
        to determine whether the endpoint is healthy.
      * `evaluate target health`
    * DNS entries are then being associated with health checks and can be configured to failover as
      well (1 primary and n secondary recordsets)
  * **Geo location**
    * Geolocation routing lets you choose the resources that serve your traffic based on the geographic
      location of your users, meaning the location that DNS queries originate from. For example, you
      might want all queries from Europe to be routed to an ELB load balancer in the Frankfurt region.
    * Should create a “default” policy (in case there’s no match on location)
  * **Geo proximity Routing (Traffic Flow Only)**
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
  * **Complex/Nested records**
    * Can combine different routing policies by routing to alias records that point to route 53 again.
      * E.g. can use *latency* policy to route into certain region
      * From there (in the regions) a *weighted* routing policy distributes traffic further

<a name="5_9_3"></a>
### [↖](#5_9)[↑](#5_9_2_3)[↓](#5_9_3_1) Health Checks with Route 53
<a name="5_9_3_1"></a>
#### [↖](#5_9)[↑](#5_9_3)[↓](#5_9_3_2) Trigger automated DNS failover
* Monitor an **endpoint** (application, server, other AWS resource)
* Monitor other **health checks** (calculated health checks)
* Monitor **CloudWatch alarms** (full control !!) – e.g. throttles of DynamoDB, alarms on RDS, custom metrics, etc
* Health Checks are integrated with CW metric

<a name="5_9_3_2"></a>
#### [↖](#5_9)[↑](#5_9_3_1)[↓](#5_9_3_3) Setup
* Health Checks can be setup to pass/fail based on text in the first 5120 bytes of the response
* Health Checks pass only with the 2xx and 3xx status response
* Calculated health checks
  * Create separate individual health checks
  * Specify how many of the health checks need to pass to make the parent pass
* Health Checks can trigger CW Alarms

<a name="5_9_3_3"></a>
#### [↖](#5_9)[↑](#5_9_3_2)[↓](#5_9_4) Private Hosted Zones
* Route 53 health checkers are outside the VPC
* They can’t access private endpoints (private VPC or on-premise resource)

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
Amazon Elastic Block Store (EBS) is an easy to use, high-performance, block-storage service
designed for use with Amazon Elastic Compute Cloud (EC2) for both throughput and transaction
intensive workloads at any scale. A broad range of workloads, such as relational and non-relational
databases, enterprise applications, containerized applications, big data analytics engines, file
systems, and media workflows are widely deployed on Amazon EBS.

You can choose from six different volume types to balance optimal price and performance. You can
achieve single-digit-millisecond latency for high-performance database workloads such as SAP HANA
or gigabyte per second throughput for large, sequential workloads such as Hadoop. You can change
volume types, tune performance, or increase volume size without disrupting your critical
applications, so you have cost-effective storage when you need it.

Designed for mission-critical systems, EBS volumes are replicated within an Availability Zone (AZ)
and can easily scale to petabytes of data. Also, you can use EBS Snapshots with automated
lifecycle policies to back up your volumes in Amazon S3, while ensuring geographic protection of your data and business continuity.

* **Permanent block storage**, independent to instance
* Attachable to running EC2 instances (same AZ)
* Only accessible by a *single instance*
* Can be resized
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

* TODO: Look into moving instances into different regions/AZs

<a name="6_1_5"></a>
### [↖](#6_1)[↑](#6_1_4)[↓](#6_2) Encrypting root volumes
* Stop instance
* Create snapshot
* Copy to different region
  * Can encrypt while copying, resulting in an encrypted snapshot in the target region
* Create image from snapshot
* Launch instance from that image

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

<a name="6_3"></a>
## [↖](#top)[↑](#6_2_1)[↓](#6_3_1) EFS
<!-- toc_start -->
* [Overview](#6_3_1)
* [Performance & Storage Classes](#6_3_2)
<!-- toc_end -->
<a name="6_3_1"></a>
### [↖](#6_3)[↑](#6_3)[↓](#6_3_2) Overview
Amazon Elastic File System (Amazon EFS) provides a simple, scalable, fully managed elastic NFS
file system for use with AWS Cloud services and on-premises resources. It is built to scale on
demand to petabytes without disrupting applications, growing and shrinking automatically as you
add and remove files, eliminating the need to provision and manage capacity to accommodate growth.

Amazon EFS offers two storage classes: the Standard storage class, and the Infrequent Access
storage class (EFS IA). EFS IA provides price/performance that's cost-optimized for files not
accessed every day. By simply enabling EFS Lifecycle Management on your file system, files not
accessed according to the lifecycle policy you choose will be automatically and transparently
moved into EFS IA. The EFS IA storage class costs only $0.025/GB-month*.

While workload patterns vary, customers typically find that 80% of files are infrequently accessed
(and suitable for EFS IA), and 20% are actively used (suitable for EFS Standard), resulting in an
effective storage cost as low as $0.08/GB-month*. Amazon EFS transparently serves files from both
storage classes in a common file system namespace.

Amazon EFS is designed to provide massively parallel shared access to thousands of Amazon EC2
instances, enabling your applications to achieve high levels of aggregate throughput and IOPS with consistent low latencies.

Amazon EFS is well suited to support a broad spectrum of use cases from home directories to
business-critical applications. Customers can use EFS to lift-and-shift existing enterprise
applications to the AWS Cloud. Other use cases include: big data analytics, web serving and
content management, application development and testing, media and entertainment workflows, database backups, and container storage.

Amazon EFS is a regional service storing data within and across multiple Availability Zones (AZs)
for high availability and durability. Amazon EC2 instances can access your file system across AZs,
regions, and VPCs, while on-premises servers can access using AWS Direct Connect or AWS VPN.

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
* *AWS CloudTrail* logs S3-API calls for *bucket-level* operations (and many other information) and
  stores them in an S3 bucket. Could also send email notifications or trigger *SNS* notifications for specific events.
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
  * *Amazon S3 Transfer Acceleration* enables fast, easy, and secure transfers (upload & download) of files over long distances
  between your client and an S3 bucket. Transfer Acceleration takes advantage of Amazon CloudFront’s globally
  distributed edge locations. As the data arrives at an edge location, data is routed to Amazon S3 over an optimized network path.
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
Replication enables automatic, asynchronous copying of objects across Amazon S3 buckets. Buckets
that are configured for object replication can be owned by the same AWS account or by different
accounts. Object may be replicated to a single destination bucket or multiple destination buckets.
Destination buckets can be in different AWS Regions or within the same Region as the source bucket.

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
Glacier|**11x9**|.|**>=3**|.|Yes|For archival only, comes as *expedited*, *standard* or *bulk*
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
All objects are private by default. Only the object owner has permission to access these objects.
However, the object owner can optionally share objects with others by creating a **pre-signed URL**,
using their own security credentials, to grant time-limited permission to download the objects.

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
## [↖](#top)[↑](#7)[↓](#7_1_1) CloudFront
<!-- toc_start -->
* [Overview](#7_1_1)
* [Basic workflow](#7_1_2)
* [Origin](#7_1_3)
* [CloudFront vs S3 Cross Region Replication](#7_1_4)
* [CloudFront Geo Restriction](#7_1_5)
* [Signed URL/Signed Cookies](#7_1_6)
* [Caching](#7_1_7)
  * [CloudFront Caching vs API Gateway Caching](#7_1_7_1)
* [Lambda@Edge](#7_1_8)
* [https](#7_1_9)
  * [Scenario 1 (requires 2 certs)](#7_1_9_1)
  * [Scenario 2 (doesn't work)](#7_1_9_2)
  * [Scenario 2 (requires 1 cert)](#7_1_9_3)
<!-- toc_end -->
<a name="7_1_1"></a>
### [↖](#7_1)[↑](#7_1)[↓](#7_1_2) Overview
Amazon CloudFront is a web service that speeds up distribution of your static and dynamic web
content, such as .html, .css, .js, and image files, to your users. CloudFront delivers your
content through a worldwide network of data centers called edge locations. When a user requests
content that you're serving with CloudFront, the request is routed to the edge location that
provides the lowest latency (time delay), so that content is delivered with the best possible performance.

* If the content is already in the edge location with the lowest latency, CloudFront delivers it immediately.
* If the content is not in that edge location, CloudFront retrieves it from an origin that you've defined—such as an Amazon S3 bucket, a MediaPackage channel, or an HTTP server (for example, a web server) that you have identified as the source for the definitive version of your content.

CloudFront speeds up the distribution of your content by routing each user request through the AWS
backbone network to the edge location that can best serve your content. Typically, this is a
CloudFront edge server that provides the fastest delivery to the viewer. Using the AWS network
dramatically reduces the number of networks that your users' requests must pass through, which
improves performance. Users get lower latency—the time it takes to load the first byte of the file
and higher data transfer rates.

You also get increased reliability and availability because copies of your files (also known as
objects) are now held (or cached) in multiple edge locations around the world.
* Content Delivery Network (CDN)
* Improves read performance, content is cached at the edge
* 225 Point of Presence globally (edge locations)
* DDoS protection, integration with Shield, AWS Web Application Firewall
* Can expose external HTTPS and can talk to internal HTTPS backends
* On AWS: <a href="https://aws.amazon.com/cloudfront/" target="_blank">Service</a> - <a href="https://aws.amazon.com/cloudfront/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html" target="_blank">User Guide</a>

<a name="7_1_2"></a>
### [↖](#7_1)[↑](#7_1_1)[↓](#7_1_3) Basic workflow
* You specify origin servers, like an Amazon S3 bucket or your own HTTP server, from which CloudFront gets your files which will then be distributed from CloudFront edge locations all over the world.
* An origin server stores the original, definitive version of your objects.
* You upload your files to your origin servers.
* If you're using an Amazon S3 bucket as an origin server, you can make the objects in your bucket publicly readable, so that anyone who knows the CloudFront URLs for your objects can access them. You also have the option of keeping objects private and controlling who accesses them. See Serving private content with signed URLs and signed cookies.
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

Can have primary and secondary origin (HA - Failover)

Origin|How content is accessed
-|-
S3|CloudFront assumes Origin Access Identity<br/>S3 Bucket Policy
EC2|Must have public IPs
ALB (-> EC2)|ALB must have public IP, EC2 can be private

<a name="7_1_4"></a>
### [↖](#7_1)[↑](#7_1_3)[↓](#7_1_5) CloudFront vs S3 Cross Region Replication
* **CloudFront**
  * Global Edge network
  * Files are cached for a TTL (maybe a day)
  * Great for static content that must be available everywhere
* **S3 Cross Region Replication**
  * Must be setup for each region you want replication to happen
  * Files are updated in near real-time
  * Read only
  * Great for dynamic content that needs to be available at low-latency in few regions

<a name="7_1_5"></a>
### [↖](#7_1)[↑](#7_1_4)[↓](#7_1_6) CloudFront Geo Restriction
* You can restrict who can access your distribution
  * Whitelist: Allow your users to access your content only if they're in one of the countries on a list of approved countries.
  * Blacklist: Prevent your users from accessing your content if they're in one of the countries on a blacklist of banned countries.
* The “country” is determined using a 3 rd party Geo-IP database
* Use case: Copyright Laws to control access to content

<a name="7_1_6"></a>
### [↖](#7_1)[↑](#7_1_5)[↓](#7_1_7) Signed URL/Signed Cookies
* You want to distribute paid shared content to premium users over the world
* We can use CloudFront Signed URL/Cookie. We attach a policy with:
  * Includes URL expiration
  * Includes IP ranges to access the data from
  * Trusted signers (which AWS accounts can create signed URLs)
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

<a name="7_1_7"></a>
### [↖](#7_1)[↑](#7_1_6)[↓](#7_1_7_1) Caching
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

<a name="7_1_7_1"></a>
#### [↖](#7_1)[↑](#7_1_7)[↓](#7_1_8) CloudFront Caching vs API Gateway Caching
API Gateway now has two different kinds of endpoints. The original design is now called *edge
optimized*, and the new option is called *regional*. Regional endpoints do not use front-end services
from CloudFront, and may offer lower latency when accessed from EC2 within the same AWS region.
All existing endpoints were categorized as edge-optimized when the new regional capability was
rolled out. With a regional endpoint, the CloudFront-* headers are not present in the request,
unless you use your own CloudFront distribution and whitelist those headers for forwarding to the origin.

* Can deploy API Gateway in *regional mode* (comes with its own cache), *and* deploy a CloudFront distribution at the edge, that can have a cache too.
  * Allows for fine-grained control of caching
  * Many different options from here, could e.g. also disable API-Gateway cache

<a name="7_1_8"></a>
### [↖](#7_1)[↑](#7_1_7_1)[↓](#7_1_9) Lambda@Edge
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

<a name="7_1_9"></a>
### [↖](#7_1)[↑](#7_1_8)[↓](#7_1_9_1) https
* A viewer submits an HTTPS request to CloudFront. There's some SSL/TLS negotiation here between the viewer and CloudFront. In the end, the viewer submits the request in an encrypted format.
* If the object is in the CloudFront edge cache, CloudFront encrypts the response and returns it to the viewer, and the viewer decrypts it.
* If the object is not in the CloudFront cache, CloudFront performs SSL/TLS negotiation with your origin and, when the negotiation is complete, forwards the request to your origin in an encrypted format.
* Your origin decrypts the request, encrypts the requested object, and returns the object to CloudFront.
* CloudFront decrypts the response, re-encrypts it, and forwards the object to the viewer. CloudFront also saves the object in the edge cache so that the object is available the next time it's requested.
* The viewer decrypts the response.

<a name="7_1_9_1"></a>
#### [↖](#7_1)[↑](#7_1_9)[↓](#7_1_9_2) Scenario 1 (requires 2 certs)

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

<a name="7_1_9_2"></a>
#### [↖](#7_1)[↑](#7_1_9_1)[↓](#7_1_9_3) Scenario 2 (doesn't work)

.|CloudFront|ALB
-|-|-
hostname|www.example.com|www.example.com
ssl cert|www.example.com|www.example.com
origin|www.example.com|.

Impossible, as CloudFront distribution will loop over itself!

<a name="7_1_9_3"></a>
#### [↖](#7_1)[↑](#7_1_9_2)[↓](#7_2) Scenario 2 (requires 1 cert)

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
## [↖](#top)[↑](#7_1_9_3)[↓](#7_2_1) ElastiCache
<!-- toc_start -->
* [Overview](#7_2_1)
* [Scenarios](#7_2_2)
* [Memcached](#7_2_3)
* [Redis](#7_2_4)
<!-- toc_end -->

<a name="7_2_1"></a>
### [↖](#7_2)[↑](#7_2)[↓](#7_2_2) Overview
* Amazon ElastiCache allows you to seamlessly set up, run, and scale popular open-source compatible
in-memory data stores in the cloud. Build data-intensive apps or boost the performance of your
existing databases by retrieving data from high throughput and low latency in-memory data stores.
* Amazon ElastiCache is a popular choice for real-time use cases like Caching, Session Stores, Gamin, Geospatial Services, Real-Time Analytics, and Queuing.
* Amazon ElastiCache offers fully managed Redis and Memcached for your most demanding applications that require sub-millisecond response times.

• Caches are in-memory databases with really high performance, low latency
• Helps reduce load off of databases for read intensive workloads
• Helps make your application stateless
• AWS takes care of OS maintenance/patching, optimizations, setup, configuration, monitoring, failure recovery and backups
• Using ElastiCache involves heavy application code changes
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
* A widely adopted memory object caching system. ElastiCache is protocol compliant with Memcached,
  so popular tools that you use today with existing Memchached environments willwork seamlessly with
  the service.
* Multi-node for partitioning of data (sharding)
* Non persistent
* No backup and restore
* Multi-threaded architecture

<a name="7_2_4"></a>
### [↖](#7_2)[↑](#7_2_3)[↓](#7_3) Redis
* A popular open-source in-memory key-value store that supports data structures such as sorted sets
  and lists. ElastiCache supports master/slave replication and multi-AZ which can be used to achieve cross-AZ-redundancy.
* Also offers Pub/Sub, Sorted Sets and In-Memory Data Store
* Multi AZ with Auto-Failover
* Read Replicas to scale reads and have high availability
* Persistent, Data Durability:
  * Read Only File Feature (AOF),
  * backup and restore features

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
Amazon DynamoDB is a key-value and document database that delivers single-digit millisecond
performance at any scale. It's a fully managed, multi-region, multi-active, durable database with
built-in security, backup and restore, and in-memory caching for internet-scale applications.
DynamoDB can handle more than 10 trillion requests per day and can support peaks of more than 20
million requests per second.
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
* Multi AZ
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
## [↖](#top)[↑](#8_1_7_1)[↓](#8_2_1) ElasticSearch
<!-- toc_start -->
* [Overview](#8_2_1)
* [ELK](#8_2_2)
* [ElasticSearch Patterns](#8_2_3)
<!-- toc_end -->

<a name="8_2_1"></a>
### [↖](#8_2)[↑](#8_2)[↓](#8_2_2) Overview
Amazon Elasticsearch Service is a fully managed service that makes it easy for you to deploy,
secure, and run Elasticsearch cost effectively at scale. You can build, monitor, and troubleshoot
your applications using the tools you love, at the scale you need. The service provides support
for open source Elasticsearch APIs, managed Kibana, integration with Logstash and other AWS
services, and built-in alerting and SQL querying. Amazon Elasticsearch Service lets you pay only
for what you use – there are no upfront costs or usage requirements. With Amazon Elasticsearch
Service, you get the ELK stack you need, without the operational overhead.

* Managed version of Elasticsearch (open source project)
* Runs on servers (not a serverless offering)
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
Amazon Relational Database Service (Amazon RDS) makes it easy to set up, operate, and scale a
relational database in the cloud. It provides cost-efficient and resizable capacity while
automating time-consuming administration tasks such as hardware provisioning, database setup,
patching and backups. It frees you to focus on your applications so you can give them the fast
performance, high availability, security and compatibility they need

Amazon RDS is available on several database instance types - optimized for memory, performance or I/O -
and provides you with six familiar database engines to choose from, including Amazon Aurora,
PostgreSQL, MySQL, MariaDB, Oracle Database, and SQL Server. You can use the AWS Database
Migration Service to easily migrate or replicate your existing databases to Amazon RDS.

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
  * E.g. use read replica to implement bigger changes on db level, after these have been finished
  promote to master instance
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
Amazon Aurora (Aurora) is a fully managed relational database engine that's compatible with MySQL
and PostgreSQL. You already know how MySQL and PostgreSQL combine the speed and reliability of high-end
commercial databases with the simplicity and cost-effectiveness of open-source databases. The
code, tools, and applications you use today with your existing MySQL and PostgreSQL databases can
be used with Aurora. With some workloads, Aurora can deliver up to five times the throughput of
MySQL and up to three times the throughput of PostgreSQL without requiring changes to most of your existing applications.

Aurora includes a high-performance storage subsystem. Its MySQL- and PostgreSQL-compatible
database engines are customized to take advantage of that fast distributed storage. The underlying
storage grows automatically as needed. An Aurora cluster volume can grow to a maximum size of 128 tebibytes (TiB).
Aurora also automates and standardizes database clustering and replication, which are typically
among the most challenging aspects of database configuration and administration.

Aurora is part of the managed database service Amazon Relational Database Service (Amazon RDS). More
cloud-native, usually preferred over RDS

* DB Engines: PostgreSQL-compatible & MySQL-compatible
* Storage: *automatically* grows up to 128 TB, 6 copies of data, multi-AZ
* Read Replicas: up to 15 RR
  * Single reader endpoint to access them all
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
## [↖](#top)[↑](#9_2_2)[↓](#9_3_1) Simple Queue Service (SQS)
<!-- toc_start -->
* [Overview](#9_3_1)
* [Core features](#9_3_2)
* [Scenarios](#9_3_3)
* [Limits:](#9_3_4)
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
### [↖](#9_3)[↑](#9_3_3)[↓](#9_4) Limits:
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
## [↖](#top)[↑](#9_4_1)[↓](#9_5_1) Simple Notification Service (SNS)
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
  * Mobile Notifications (SNS Mobile Push - Android, Apple, Fire OS, Windows...)
* On AWS: <a href="https://aws.amazon.com/sns" target="_blank">Service</a> - <a href="https://aws.amazon.com/sns/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/sns" target="_blank">User Guide</a>

<a name="9_5_2"></a>
### [↖](#9_5)[↑](#9_5_1)[↓](#10) Scenarios
* SNS + SQS: Fan Out
  * `Producer` -> `SNS` -> per consumer: `SQS` - `Consumer`
    * Push once in SNS, receive in many SQS queues
    * Fully decoupled, no data loss, ability to add receivers of data later
    * SQS allows for delayed processing, retries of work
    * May have many workers on one queue and one worker on the other queue

<a name="10"></a>
# [↖](#top)[↑](#9_5_2)[↓](#10_1) Data Engineering

<a name="10_1"></a>
## [↖](#top)[↑](#10)[↓](#10_1_1) Kinesis
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

* Streams are divided in ordered *Shards*/partitions
* Data retention is 24 hours by default, can go up to 365 days (previously: 7 days)
* Ability to reprocess/replay data
* Multiple applications can consume the same stream
  * This is not possible with e.g. SQS
* Real-time processing with scale of throughput
  * The more Shards, the more scale
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
### [↖](#10_1)[↑](#10_1_4) Kinesis Data Analytics
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
