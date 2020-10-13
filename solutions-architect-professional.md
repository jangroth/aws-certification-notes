<!-- toc_start -->
<a name="top"></a>
---
* [Solutions Architect Professional](#1)
* [Exam Objectives](#2)
  * [Content](#2_1)
* [Identity and Federation](#3)
  * [IAM](#3_1)
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
## [↖](#top)[↑](#3)[↓](#3_1_1) IAM
<!-- toc_start -->
* [Overview](#3_1_1)
* [Users](#3_1_2)
* [Groups](#3_1_3)
* [Roles](#3_1_4)
* [Policies](#3_1_5)
<!-- toc_end -->

<a name="3_1_1"></a>
### [↖](#3_1)[↑](#3_1)[↓](#3_1_2) Overview
AWS Identity and Access Management (IAM) enables you to manage access to AWS services and
resources securely. Using IAM, you can create and manage AWS users and groups, and use permissions
to allow and deny their access to AWS resources.

* **Policies** - defines one or more permissions
  * Can be attached to users, groups or roles (preferred)

* On AWS: <a href="https://aws.amazon.com/iam/" target="_blank">Service</a> - <a href="https://aws.amazon.com/iam/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html" target="_blank">User Guide</a>

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

<a name="3_1_5"></a>
### [↖](#3_1)[↑](#3_1_4) Policies
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
  user or role). That policy defines the maximum permissions that the identity-based policies can
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

