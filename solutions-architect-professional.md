<!-- toc_start -->
<a name="top"></a>
---
* [Solutions Architect Professional](#1)
* [Exam Objectives](#2)
  * [Content](#2_1)
* [Identity and Federation](#3)
  * [Identity and Access Management (IAM)](#3_1)
  * [STS (Security Token Service)](#3_2)
  * [Identity Federation](#3_3)
  * [AWS Active Directory Services](#3_4)
  * [AWS Organization](#3_5)
  * [AWS Resource Access Manager](#3_6)
  * [AWS Single Sign-On](#3_7)
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

## Summary
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

<a name="3_1"></a>
## [↖](#top)[↑](#3)[↓](#3_1_1) Identity and Access Management (IAM)
<!-- toc_start -->
* [Overview](#3_1_1)
* [Users](#3_1_2)
* [Groups](#3_1_3)
* [Roles](#3_1_4)
* [Policies](#3_1_5)
  * [Policy Conditions](#3_1_5_1)
  * [Policy Variables & Tags](#3_1_5_2)
  * [Identity-based vs resource-based policies](#3_1_5_3)
* [Automated Scanning](#3_1_6)
  * [Access Advisor](#3_1_6_1)
  * [Access Analyzer](#3_1_6_2)
<!-- toc_end -->

<a name="3_1_1"></a>
### [↖](#3_1)[↑](#3_1)[↓](#3_1_2) Overview
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

<a name="3_1_2"></a>
### [↖](#3_1)[↑](#3_1_1)[↓](#3_1_3) Users
* An AWS Identity and Access Management (IAM) user is an entity that you create in AWS to
  represent the person or application that uses it to interact with AWS. A user in AWS consists of a
  name and credentials.
* Hold long-term credentials

<a name="3_1_3"></a>
### [↖](#3_1)[↑](#3_1_2)[↓](#3_1_4) Groups
* An IAM group is a collection of IAM users. Groups let you specify permissions for multiple users,
  which can make it easier to manage the permissions for those users.
* Typically only provides permission to assume a role

<a name="3_1_4"></a>
### [↖](#3_1)[↑](#3_1_3)[↓](#3_1_5) Roles
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


<a name="3_1_5"></a>
### [↖](#3_1)[↑](#3_1_4)[↓](#3_1_5_1) Policies
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
<a name="3_1_5_1"></a>
#### [↖](#3_1)[↑](#3_1_5)[↓](#3_1_5_2) Policy Conditions
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

<a name="3_1_5_2"></a>
#### [↖](#3_1)[↑](#3_1_5_1)[↓](#3_1_5_3) Policy Variables & Tags
Example: `${aws:username}`
• "Resource": ["arn:aws:s3:::mybucket/${aws:username}/*"]
AWS Specific:
• `aws:CurrentTime`, `aws:TokenIssueTime`, `aws:principaltype`, `aws:SecureTransport`, `aws:SourceIp`, `aws:userid`, `ec2:SourceInstanceARN`
Service Specific:
• `s3:prefix`, `s3:max-keys`, `s3:x-amz-acl`, `sns:Endpoint`, `sns:Protocol`...
Tag Based:
• `iam:ResourceTag/key-name`, `aws:PrincipalTag/key-name`...

<a name="3_1_5_3"></a>
#### [↖](#3_1)[↑](#3_1_5_2)[↓](#3_1_6) Identity-based vs resource-based policies
* **Identity-based policies** are attached to an IAM user, group, or role. These policies let you specify what that identity can do (its permissions).
* **Resource-based policies** are attached to a resource.
<a href="https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_aws-services-that-work-with-iam.html" target="_blank">AWS services that work with IAM</a>

<a name="3_1_6"></a>
### [↖](#3_1)[↑](#3_1_5_3)[↓](#3_1_6_1) Automated Scanning

<a name="3_1_6_1"></a>
#### [↖](#3_1)[↑](#3_1_6)[↓](#3_1_6_2) Access Advisor
Access Advisor shows the services that a certain user or role can access and when those services
were last accessed. Review this data to remove unused permissions.

<a name="3_1_6_2"></a>
#### [↖](#3_1)[↑](#3_1_6_1)[↓](#3_2) Access Analyzer
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

<a name="3_2"></a>
## [↖](#top)[↑](#3_1_6_2)[↓](#3_2_1) STS (Security Token Service)
<!-- toc_start -->
* [Overview](#3_2_1)
* [Providing access to an IAM user in another AWS account that you own](#3_2_2)
* [Providing access to an IAM user from a third party AWS account](#3_2_3)
<!-- toc_end -->

<a name="3_2_1"></a>
### [↖](#3_2)[↑](#3_2)[↓](#3_2_2) Overview
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

<a name="3_2_2"></a>
### [↖](#3_2)[↑](#3_2_1)[↓](#3_2_3) Providing access to an IAM user in another AWS account that you own
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

<a name="3_2_3"></a>
### [↖](#3_2)[↑](#3_2_2)[↓](#3_3) Providing access to an IAM user from a third party AWS account
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

<a name="3_3"></a>
## [↖](#top)[↑](#3_2_3)[↓](#3_3_1) Identity Federation
<!-- toc_start -->
* [Overview](#3_3_1)
* [SAML 2.0](#3_3_2)
* [Custom Identity Broker](#3_3_3)
* [Federating users of a mobile or web-based app with WebIdentity](#3_3_4)
* [Federating users of a mobile or web-based app with Amazon Cognito](#3_3_5)
<!-- toc_end -->

<a name="3_3_1"></a>
### [↖](#3_3)[↑](#3_3)[↓](#3_3_2) Overview
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

<a name="3_3_2"></a>
### [↖](#3_3)[↑](#3_3_1)[↓](#3_3_3) SAML 2.0
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

<a name="3_3_3"></a>
### [↖](#3_3)[↑](#3_3_2)[↓](#3_3_4) Custom Identity Broker
* If identity provider is not compatible with SAML 2.0
* The identity broker must determine the appropriate IAM policy (talks directly to STS, unlike SAML scenarios)
* Use STS `AssumeRole` or `GetFederationToken`
* <a href="https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_common-scenarios_federated-users.html" target="_blank">Documentation On AWS</a>

<a name="3_3_4"></a>
### [↖](#3_3)[↑](#3_3_3)[↓](#3_3_5) Federating users of a mobile or web-based app with WebIdentity
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

<a name="3_3_5"></a>
### [↖](#3_3)[↑](#3_3_4)[↓](#3_4) Federating users of a mobile or web-based app with Amazon Cognito
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

<a name="3_4"></a>
## [↖](#top)[↑](#3_3_5)[↓](#3_4_1) AWS Active Directory Services
<!-- toc_start -->
* [Overview](#3_4_1)
* [AWS Managed Microsoft AD](#3_4_2)
  * [Overview](#3_4_2_1)
  * [Integrations](#3_4_2_2)
  * [Connecting to on-premises AD](#3_4_2_3)
  * [Syncronizing with on-premises AD](#3_4_2_4)
* [AD Connector](#3_4_3)
* [Simple AD](#3_4_4)
<!-- toc_end -->

<a name="3_4_1"></a>
### [↖](#3_4)[↑](#3_4)[↓](#3_4_2) Overview

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

<a name="3_4_2"></a>
### [↖](#3_4)[↑](#3_4_1)[↓](#3_4_2_1) AWS Managed Microsoft AD
<a name="3_4_2_1"></a>
#### [↖](#3_4)[↑](#3_4_2)[↓](#3_4_2_2) Overview

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

<a name="3_4_2_2"></a>
#### [↖](#3_4)[↑](#3_4_2_1)[↓](#3_4_2_3) Integrations
* Windows applications on EC2 can *join the domain* and run traditional AD applications
  * Sharepoint, ...
* RDS for SQL Server, AWS Workspaces, Quicksight, ...
* AWS SSO for 3rd party access (SAML)

<a name="3_4_2_3"></a>
#### [↖](#3_4)[↑](#3_4_2_2)[↓](#3_4_2_4) Connecting to on-premises AD
* Needs Direct Connect or VPN
* Three kinds of of forest trust
  * One way on-premises -> AWS
  * One way AWS -> on-premises
  * Two way AWS <-> on-premises
* Forest trust is different to syncronization!
  * Replication not supported
  * Users on both ADs are independent from each other

<a name="3_4_2_4"></a>
#### [↖](#3_4)[↑](#3_4_2_3)[↓](#3_4_3) Syncronizing with on-premises AD
* Have to install Microsoft AD on EC2 yourself and setup replication
* Establish forest trust between this installation and AWS Managed Microsoft AD

<a name="3_4_3"></a>
### [↖](#3_4)[↑](#3_4_2_4)[↓](#3_4_4) AD Connector
* AD Connector is a directory gateway (*proxy*) to redirect directory requests to your on-premises Microsoft Active Directory
* No caching capability
  * Has latency
* Manage users solely on-premises, no possibility of setting up a trust
  * No MFA
* VPN or Direct Connect -> can't function if connection goes down
* Doesn’t work with SQL Server, doesn’t do seamless joining, can’t share directory

<a name="3_4_4"></a>
### [↖](#3_4)[↑](#3_4_3)[↓](#3_5) Simple AD
* Simple AD is an inexpensive Active Directory–compatible service with the common directory features.
* Supports joining EC2 instances, manage users and groups
* Does not support MFA, RDS SQL server, AWS SSO
* Small: 500 users, large: 5000 users
* Powered by Samba 4, compatible with Microsoft AD
* Lower cost, low scale, basic AD compatible, or LDAP compatibility
* No trust relationship to on-premises Microsoft AD

<a name="3_5"></a>
## [↖](#top)[↑](#3_4_4)[↓](#3_5_1) AWS Organization
<!-- toc_start -->
* [Overview](#3_5_1)
  * [Benefits](#3_5_1_1)
  * [Multi-account strategies](#3_5_1_2)
* [Service Control Policies (SCP)](#3_5_2)
* [Tag Policies](#3_5_3)
* [Reserved Instances](#3_5_4)
<!-- toc_end -->
<a name="3_5_1"></a>
### [↖](#3_5)[↑](#3_5)[↓](#3_5_1_1) Overview
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

<a name="3_5_1_1"></a>
#### [↖](#3_5)[↑](#3_5_1)[↓](#3_5_1_2) Benefits
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

<a name="3_5_1_2"></a>
#### [↖](#3_5)[↑](#3_5_1_1)[↓](#3_5_2) Multi-account strategies
• Create accounts per department, per cost center, per dev / test / prod, based on regulatory
  restrictions (using SCP), for better resource isolation (ex: VPC), to have separate per-account
  service limits, isolated account for logging,
• Multi account vs one account multi vPC
• Use tagging standards for billing purposes
• Enable CloudTrail on all accounts, send logs to central S3 account
• Send CloudWatch logs to central logging account
• Establish cross account roles for admin purposes

<a name="3_5_2"></a>
### [↖](#3_5)[↑](#3_5_1_2)[↓](#3_5_3) Service Control Policies (SCP)
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

<a name="3_5_3"></a>
### [↖](#3_5)[↑](#3_5_2)[↓](#3_5_4) Tag Policies
Tag policies are a type of policy that can help you standardize tags across resources in your
organization's accounts. In a tag policy, you specify tagging rules applicable to resources when they are tagged.

<a name="3_5_4"></a>
### [↖](#3_5)[↑](#3_5_3)[↓](#3_6) Reserved Instances
* For billing purposes, the consolidated billing feature of AWS Organizations treats all the
  accounts in the organization as one account.
* This means that all accounts in the organization can receive the hourly cost benefit of Reserved
  Instances that are purchased by any other account.
* The payer account (master account) of an organization can turn off Reserved Instance (RI)
  discount and Savings Plans discount sharing for any accounts in that organization, including the payer account
* This means that RIs and Savings Plans discounts aren't shared between any accounts that have sharing turned off.
* To share an RI or Savings Plans discount with an account, both accounts must have sharing turned on.

<a name="3_6"></a>
## [↖](#top)[↑](#3_5_4)[↓](#3_6_1) AWS Resource Access Manager
<!-- toc_start -->
* [Overview](#3_6_1)
<!-- toc_end -->
<a name="3_6_1"></a>
### [↖](#3_6)[↑](#3_6)[↓](#3_7) Overview
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

<a name="3_7"></a>
## [↖](#top)[↑](#3_6_1)[↓](#3_7_1) AWS Single Sign-On
<!-- toc_start -->
* [Overview](#3_7_1)
<!-- toc_end -->

<a name="3_7_1"></a>
### [↖](#3_7)[↑](#3_7) Overview
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

# Security

## CloudTrail

### Overview
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
### [↖](#4_8)[↑](#4_8_1)[↓](#4_8_2_1) Concepts

<a name="4_8_2_1"></a>
#### [↖](#4_8)[↑](#4_8_2)[↓](#4_8_3) Event
* JSON format, who did what (API calls).
* ~15min delay
* Stored for 90 days

<a name="4_8_3"></a>
### [↖](#4_8)[↑](#4_8_2_1)[↓](#4_9) Trail
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
