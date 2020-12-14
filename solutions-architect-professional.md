<!-- toc_start -->
<a name="top"></a>
---
* [Solutions Architect Professional](#1)
* [Exam Objectives](#2)
  * [Content](#2_1)
* [Identity and Federation](#3)
  * [Summary](#3_1)
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
---
<!-- toc_end -->
<a name="1"></a>
# [↖](#top)[↓](#2) Solutions Architect Professional

> 10/2020 -
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

<a name="3"></a>
# [↖](#top)[↑](#2_1_5)[↓](#3_1) Identity and Federation

<a name="3_1"></a>
## [↖](#top)[↑](#3)[↓](#3_2) Summary
* Users and Accounts all in AWS
* AWS Organizations
* Federation with SAML
* Federation without SAML with a custom IdP (GetFederationToken)
* Federation with SSO for multiple accounts with AWS Organizations
* Web Identity Federation (not recommended)
* Cognito for most web and mobile applications (has anonymous mode, MFA)
* Active Directory on AWS:
  * Microsoft AD: standalone or setup trust AD with on-premise, has MFA, seamless join, RDS integration
  * AD Connector: proxy requests to on-premise
  * Simple AD: standalone & cheap AD-compatible with no MFA, no advanced capabilities
  * Single Sign On to connect to multiple AWS Accounts (Organization) and SAML apps

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
AWS Identity and Access Management (IAM) enables you to manage access to AWS services and
resources securely. Using IAM, you can create and manage AWS users and groups, and use permissions
to allow and deny their access to AWS resources.

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

IAM on AWS:
* <a href="https://aws.amazon.com/iam/" target="_blank">Service</a> - <a href="https://aws.amazon.com/iam/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html" target="_blank">User Guide</a>

<a name="3_2_2"></a>
### [↖](#3_2)[↑](#3_2_1)[↓](#3_2_3) Users
* An AWS Identity and Access Management (IAM) user is an entity that you create in AWS to
  represent the person or application that uses it to interact with AWS. A user in AWS consists of a
  name and credentials.
* Hold long-term credentials

<a name="3_2_3"></a>
### [↖](#3_2)[↑](#3_2_2)[↓](#3_2_4) Groups
* An IAM group is a collection of IAM users. Groups let you specify permissions for multiple users,
  which can make it easier to manage the permissions for those users.
* Typically only provides permission to assume a role

<a name="3_2_4"></a>
### [↖](#3_2)[↑](#3_2_3)[↓](#3_2_5) Roles
* **Role** - An IAM identity that you can create in your account that has specific permissions. An IAM role
  has some similarities to an IAM user. Roles and users are both AWS identities with permissions
  policies that determine what the identity can and cannot do in AWS. However, instead of being
  uniquely associated with one person, a role is intended to be assumable by anyone who needs it.
  Also, a role does not have standard long-term credentials such as a password or access keys
  associated with it. Instead, when you assume a role, it provides you with temporary security
  credentials for your role session, provided by STS.
* **AWS service role** - A role that a service assumes to perform actions in your account on your
  behalf. When you set up some AWS service environments, you must define a role for the service to
  assume. This service role must include all the permissions required for the service to access the
  AWS resources that it needs. Service roles vary from service to service, but many allow you to
  choose your permissions, as long as you meet the documented requirements for that service. Service
  roles provide access only within your account and cannot be used to grant access to services in
  other accounts. You can create, modify, and delete a service role from within IAM.
* **AWS service role for an EC2 instance** - A special type of service role that an application
  running on an Amazon EC2 instance can assume to perform actions in your account. This role is
  assigned to the EC2 instance when it is launched. Applications running on that instance can
  retrieve temporary security credentials and perform actions that the role allows.
* **AWS service-linked role** - A unique type of service role that is linked directly to an AWS
  service. Service-linked roles are predefined by the service and include all the permissions that
  the service requires to call other AWS services on your behalf. The linked service also defines
  how you create, modify, and delete a service-linked role. A service might automatically create or
  delete the role. It might allow you to create, modify, or delete the role as part of a wizard or
  process in the service. Or it might require that you use IAM to create or delete the role.
  Regardless of the method, service-linked roles make setting up a service easier because you don't
  have to manually add the necessary permissions.
* **Trust policy** - A JSON policy document in which you define the principals that you trust to
  assume the role. A role trust policy is a required resource-based policy that is attached to a
  role in IAM. The principals that you can specify in the trust policy include users, roles, accounts,
  and services.
* **Permissions boundary** - An advanced feature in which you use policies to limit the maximum
  permissions that an identity-based policy can grant to a role. You cannot apply a permissions
  boundary to a service-linked role.
* **Role for cross-account access** - A role that grants access to resources in one account to a
  trusted principal in a different account. Roles are the primary way to grant cross-account access.
  However, some AWS services allow you to attach a policy directly to a resource (instead of using a
  role as a proxy). These are called resource-based policies, and you can use them to grant
  principals in another AWS account access to the resource. Some of these resources include S3,
  S3 Glacier vaults, SNS and SQS.

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
* You manage access in AWS by creating policies and attaching them to IAM identities (users,
  groups of users, or roles) or AWS resources. A policy is an object in AWS that, when associated
  with an identity or resource, defines their permissions. AWS evaluates these policies when an IAM
  principal (user or role) makes a request. Permissions in the policies determine whether the
  request is allowed or denied. Most policies are stored in AWS as JSON documents. AWS supports six
  types of policies:
  * **Identity-based policies** – Attach managed and inline policies to IAM identities (users,
    groups to which users belong, or roles). Identity-based policies grant permissions to an identity.
  * **Resource-based policies** – Attach inline policies to resources. The most common examples of
    resource-based policies are Amazon S3 bucket policies and IAM role trust policies. Resource
    based policies grant permissions to the principal that is specified in the policy. Principals
    can be in the same account as the resource or in other accounts.
  * **Permissions boundaries** – Use a managed policy as the permissions boundary for an IAM entity
    (user or role). That policy defines the maximum permissions that the identity-based policies can
    grant to an entity, but does not grant permissions. Permissions boundaries do not define the
    maximum permissions that a resource-based policy can grant to an entity.
  * **Organizations SCPs** – Use an AWS Organizations service control policy (SCP) to define the
    maximum permissions for account members of an organization or organizational unit (OU). SCPs
    limit permissions that identity-based policies or resource-based policies grant to entities
    (users or roles) within the account, but do not grant permissions.
  * **Access control lists (ACLs)** – Use ACLs to control which principals in other accounts can
    access the resource to which the ACL is attached. ACLs are similar to resource-based policies,
    although they are the only policy type that does not use the JSON policy document structure.
    ACLs are cross-account permissions policies that grant permissions to the specified principal.
    ACLs cannot grant permissions to entities within the same account.
  * **Session policies** – Pass advanced session policies when you use the AWS CLI or AWS API to
    assume a role or a federated user. Session policies limit the permissions that the role or
    user's identity-based policies grant to the session. Session policies limit permissions for a
    created session, but do not grant permissions. For more information, see Session Policies.
* An **AWS managed policy** is a standalone policy that is created and administered by AWS. Standalone policy means that the policy has its own Amazon Resource Name (ARN) that includes the policy name.
* <a href="https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_examples.html" target="_blank">Policy Examples</a>

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
Access Advisor shows the services that a certain user or role can access and when those services
were last accessed. Review this data to remove unused permissions.

<a name="3_2_6_2"></a>
#### [↖](#3_2)[↑](#3_2_6_1)[↓](#3_3) Access Analyzer
Makes it simple for security teams and administrators to check that their policies provide only
the intended access to resources. Resource policies allow customers to granularly control who is
able to access a specific resource and how they are able to use it across the entire cloud
environment.

IAM Access Analyzer continuously monitors policies for changes, meaning customers no longer need
to rely on intermittent manual checks in order to catch issues as policies are added or updated.
Using IAM Access Analyzer, customers can proactively address any resource policies that violate
their security and governance best practices around resource sharing and protect their resources
from unintended access. IAM Access Analyzer delivers comprehensive, detailed findings through the
AWS IAM, Amazon S3, and AWS Security Hub consoles and also through its APIs. Findings can also be
exported as a report for auditing purposes. IAM Access Analyzer findings provide definitive
answers of who has public and cross-account access to AWS resources from outside an account.

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
  * To integrate Active Directory / ADFS with AWS (or any SAML 2.0)
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
• Create accounts per department, per cost center, per dev / test / prod, based on regulatory
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
  * Route53 Resolver Rules
  * License Manager Configurations
* On AWS: <a href="https://aws.amazon.com/ram/" target="_blank">Service</a> - <a href="https://aws.amazon.com/ram/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/ram/latest/userguide/what-is.html" target="_blank">User Guide</a>

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
* Version tracking of configurations / secrets
* Configuration management using path & IAM
* Notifications with CloudWatch Events
* Integration with CloudFormation
* Can retrieve secrets from Secrets Manager using the SSM Parameter Store API
* On AWS: <a href="https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-parameter-store.html" target="_blank">User Guide</a>

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

<a name="4_5"></a>
## [↖](#top)[↑](#4_4_1)[↓](#4_5_1) RDS Security
<!-- toc_start -->
* [Overview](#4_5_1)
<!-- toc_end -->
<a name="4_5_1"></a>
### [↖](#4_5)[↑](#4_5)[↓](#4_6) Overview
* KMS encryption at rest for underlying EBS volumes / snapshots
* Transparent Data Encryption (TDE) for Oracle and SQL Server
* SSL encryption to RDS is possible for all DB (in-flight)
* IAM authentication (only) for MySQL and PostgreSQL
* Authorization still happens within RDS (not in IAM)
* Can copy an un-encrypted RDS snapshot into an encrypted one
* CloudTrail cannot be used to track queries made within RDS

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
    * You could run a custom DNS server on Ama

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
Key Storage and Management|Accessible from multiple regions<br/>Centralized management from IAM|Deployed and managed from a customer VPC.<br/>Accessible and can be shared across VPCs using VPC peering
Free Tier Availability|Yes|No

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
* Encryption in flight is also called SSL / TLS

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
* Users given a pre-signed URL inherit the permissions of the person who generated the URL for GET / PUT
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
* [Blocking IP addresses](#4_10_6)
* [Amazon Inspector](#4_10_7)
  * [Overview](#4_10_7_1)
* [Config](#4_10_8)
  * [Overview](#4_10_8_1)
  * [Config Rules](#4_10_8_2)
  * [Automation](#4_10_8_3)
  * [Aggregation](#4_10_8_4)
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
* Separate static resources (S3 / CloudFront) from dynamic ones (EC2 / ALB)

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
### [↖](#4_10)[↑](#4_10_4)[↓](#4_10_6) AWS Firewall Manager
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

<a name="4_10_6"></a>
### [↖](#4_10)[↑](#4_10_5)[↓](#4_10_7) Blocking IP addresses
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

<a name="4_10_7"></a>
### [↖](#4_10)[↑](#4_10_6)[↓](#4_10_7_1) Amazon Inspector

<a name="4_10_7_1"></a>
#### [↖](#4_10)[↑](#4_10_7)[↓](#4_10_8) Overview
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

<a name="4_10_8"></a>
### [↖](#4_10)[↑](#4_10_7_1)[↓](#4_10_8_1) Config

<a name="4_10_8_1"></a>
#### [↖](#4_10)[↑](#4_10_8)[↓](#4_10_8_2) Overview
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
* On AWS: <a href="https://aws.amazon.com/config/" target="_blank">Service</a> - <a href="https://aws.amazon.com/config/faq/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/config/latest/developerguide/WhatIsConfig.html" target="_blank">User Guide</a>

<a name="4_10_8_2"></a>
#### [↖](#4_10)[↑](#4_10_8_1)[↓](#4_10_8_3) Config Rules
* Evaluate the configuration settings of AWS resources
* A Config rule represents your ideal configuration settings
* Predefined rules called *managed rules* to help you get started
* Can also create *custom rules*
* AWS Config continuously tracks the configuration changes that occur among your resources
	* Checks whether these changes violate any of the conditions in your rules.
	* If a resource violates a rule, AWS Config flags the resource and the rule as *noncompliant*.
* Can remediate using AWS Systems Manager Automation Documents

<a name="4_10_8_3"></a>
#### [↖](#4_10)[↑](#4_10_8_2)[↓](#4_10_8_4) Automation
* SNS notification on *all* Config events (cannot configure which events)
* CloudWatch Events to observe *specific* events/rules

<a name="4_10_8_4"></a>
#### [↖](#4_10)[↑](#4_10_8_3) Aggregation
An aggregator is an AWS Config resource type that collects AWS Config configuration and compliance data from the following:
* Multiple accounts and multiple regions.
* Single account and multiple regions.
* An organization in AWS Organizations and all the accounts in that organization.
* Is limited to 50 per account
  * *"We are unable to complete the request at this time. Try again later or contact AWS Support"*
