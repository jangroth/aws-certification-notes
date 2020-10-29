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
* [Federating users of a mobile or web-based app with Amazon Cognito](#3_3_2)
<!-- toc_end -->

<a name="3_3_1"></a>
### [↖](#3_3)[↑](#3_3)[↓](#3_3_2) Overview
If you already manage user identities outside of AWS, you can use IAM identity providers instead of creating
IAM users in your AWS account. With an identity provider (IdP), you can manage your user identities outside of
AWS and give these external user identities permissions to use AWS resources in your account.

<a name="3_3_2"></a>
### [↖](#3_3)[↑](#3_3_1) Federating users of a mobile or web-based app with Amazon Cognito
If you create a mobile or web-based app that accesses AWS resources, the app needs security credentials in order to make programmatic requests to AWS. For most mobile application scenarios, we recommend that you use Amazon Cognito
