<!-- toc_start -->
<a name="top"></a>
---
* [Advanced Networking - Speciality](#1)
* [Exam Objectives](#2)
  * [Content](#2_1)
* [Design and Implement AWS Network](#3)
  * [AWS Infrastructure](#3_1)
---
<!-- toc_end -->
---
<a name="1"></a>
# [↖](#top)[↓](#2) Advanced Networking - Speciality

> 8/2021 -

Following [Exam Readiness: AWS Certified Advanced Networking - Specialty (Digital)](https://www.aws.training/Details/Curriculum?id=21330).

---

<a name="2"></a>
# [↖](#top)[↑](#1)[↓](#2_1) Exam Objectives
* Design, develop, and deploy cloud-based solutions using AWS.
* Implement core AWS services according to basic architectural best practices.
* Design and maintain network architecture for all AWS services.
* Leverage tools to automate AWS networking tasks.

<a name="2_1"></a>
## [↖](#top)[↑](#2)[↓](#2_1_1) Content
<!-- toc_start -->
* [Domain 1: Design and Implement Hybrid IT Network Architectures at Scale](#2_1_1)
* [Domain 2: Design and Implement AWS Networks](#2_1_2)
* [Domain 3: Automate AWS Tasks](#2_1_3)
* [Domain 4: Configure Network Integration with Application Services](#2_1_4)
* [Domain 5: Design and Implement for Security and Compliance](#2_1_5)
* [Domain 6: Manage, Optimize, and Troubleshoot the Network](#2_1_6)
<!-- toc_end -->
<a name="2_1_1"></a>
### [↖](#2_1)[↑](#2_1)[↓](#2_1_2) Domain 1: Design and Implement Hybrid IT Network Architectures at Scale
* 1.1 Implement connectivity for hybrid IT
* 1.2 Given a scenario, derive an appropriate hybrid IT architecture connectivity solution
* 1.3 Explain the process to extend connectivity using AWS Direct Connect
* 1.4 Evaluate design alternatives that leverage AWS Direct Connect
* 1.5 Define routing policies for hybrid IT architectures
<a name="2_1_2"></a>
### [↖](#2_1)[↑](#2_1_1)[↓](#2_1_3) Domain 2: Design and Implement AWS Networks
* 2.1 Apply AWS networking concepts
* 2.2 Given customer requirements, define network architectures on AWS
* 2.3 Propose optimized designs based on the evaluation of an existing implementation
* 2.4 Determine network requirements for a specialized workload
* 2.5 Derive an appropriate architecture based on customer and application requirements
* 2.6 Evaluate and optimize cost allocations given a network design and application data flow
<a name="2_1_3"></a>
### [↖](#2_1)[↑](#2_1_2)[↓](#2_1_4) Domain 3: Automate AWS Tasks
* 3.1 Evaluate automation alternatives within AWS for network deployments
* 3.2 Evaluate tool-based alternatives within AWS for network operations and management
<a name="2_1_4"></a>
### [↖](#2_1)[↑](#2_1_3)[↓](#2_1_5) Domain 4: Configure Network Integration with Application Services
* 4.1 Leverage the capabilities of Route 53
* 4.2 Evaluate DNS solutions in a hybrid IT architecture
* 4.3 Determine the appropriate configuration of DHCP within AWS
* 4.4 Given a scenario, determine an appropriate load balancing strategy within the AWS ecosystem
* 4.5 Determine a content distribution strategy to optimize for performance
* 4.6 Reconcile AWS service requirements with network requirements
<a name="2_1_5"></a>
### [↖](#2_1)[↑](#2_1_4)[↓](#2_1_6) Domain 5: Design and Implement for Security and Compliance
* 5.1 Evaluate design requirements for alignment with security and compliance objectives
* 5.2 Evaluate monitoring strategies in support of security and compliance objectives
* 5.3 Evaluate AWS security features for managing network traffic
* 5.4 Utilize encryption technologies to secure network communications
<a name="2_1_6"></a>
### [↖](#2_1)[↑](#2_1_5)[↓](#3) Domain 6: Manage, Optimize, and Troubleshoot the Network
* 6.1 Given a scenario, troubleshoot and resolve a network issu

<a name="3"></a>
# [↖](#top)[↑](#2_1_6)[↓](#3_1) Design and Implement AWS Network

<a name="3_1"></a>
## [↖](#top)[↑](#3)[↓](#3_1_1) AWS Infrastructure
<!-- toc_start -->
* [Regions, AZs, Edge Locations and Local Zones](#3_1_1)
<!-- toc_end -->

<a name="3_1_1"></a>
### [↖](#3_1)[↑](#3_1) Regions, AZs, Edge Locations and Local Zones
AWS has the concept of a **Region**, which is a physical location around the world where we cluster data centers. We call each group of logical data centers an Availability Zone. Each AWS Region consists of multiple, isolated, and physically separate AZs within a geographic area.

An **Availability Zone (AZ)** is one or more discrete data centers with redundant power, networking, and connectivity in an AWS Region. AZs give customers the ability to operate production applications and databases that are more highly available, fault tolerant, and scalable than would be possible from a single data center.

**Edge locations** are AWS data centers ('endpoints') designed to deliver services with the lowest latency possible. Amazon has dozens of these data centers spread across the world. They’re closer to users than Regions or Availability Zones, often in major cities, so responses can be fast and snappy. A subset of services for which latency really matters use edge locations, including:
* *CloudFront*, which uses edge locations to cache copies of the content that it serves, so the content is closer to users and can be delivered to them faster.
* *Lambda@Edge*, is a feature of Amazon CloudFront that lets you run code closer to users of your application, which improves performance and reduces latency.
* *Route 53*, which serves DNS responses from edge locations, so that DNS queries that originate nearby can resolve faster (and, contrary to what you might think, is also Amazon’s premier database).
* *Web Application Firewall* and *AWS Shield*, which filter traffic in edge locations to stop unwanted traffic as soon as possible.

**AWS Local Zones** place compute, storage, database, and other select AWS services closer to end-users. With AWS Local Zones, you can easily run highly-demanding applications that require single-digit millisecond latencies to your end-users such as media & entertainment content creation, real-time gaming, reservoir simulations, electronic design automation, and machine learning:
* A Local Zone is an extension of an AWS Region that is geographically close to your users.
* You can extend any VPC from the parent AWS Region into Local Zones by creating a new subnet and assigning it to the AWS Local Zone. When you create a subnet in a Local Zone, your VPC is extended to that Local Zone. The subnet in the Local Zone operates the same as other subnets in your VPC.

