<!-- toc_start -->
<a name="top"></a>
---
* [Advanced Networking - Speciality](#1)
* [Exam Objectives](#2)
  * [Content](#2_1)
* [Design and Implement AWS Networks](#3)
  * [AWS Global Network Infrastructure](#3_1)
  * [Virtual Private Cloud (VPC)](#3_2)
  * [Connecting VPCs to other VPCs](#3_3)
* [Topics still to cover](#4)
  * [Supporting Material](#4_1)
---
<!-- toc_end -->
---
<a name="1"></a>
# [↖](#top)[↓](#2) Advanced Networking - Speciality

> 8/2021 -

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
# [↖](#top)[↑](#2_1_6)[↓](#3_1) Design and Implement AWS Networks

<a name="3_1"></a>
## [↖](#top)[↑](#3)[↓](#3_1_1) AWS Global Network Infrastructure
<!-- toc_start -->
* [Overview](#3_1_1)
<!-- toc_end -->

<a name="3_1_1"></a>
### [↖](#3_1)[↑](#3_1)[↓](#3_2) Overview
AWS has the concept of a **Region**, which is a physical location around the world where we cluster data centers. We call each group of logical data centers an Availability Zone. Each AWS Region consists of multiple, isolated, and physically separate AZs within a geographic area.

An **Availability Zone (AZ)** is one or more discrete data centers with redundant power, networking, and connectivity in an AWS Region. AZs give customers the ability to operate production applications and databases that are more highly available, fault tolerant, and scalable than would be possible from a single data center.

A **transit center** provides redundant connectivity between AZs and internet backbones.

**Edge locations** are AWS data centers ('endpoints') designed to deliver services with the lowest latency possible. Amazon has dozens of these data centers spread across the world. They’re closer to users than Regions or Availability Zones, often in major cities, so responses can be fast and snappy. A subset of services for which latency really matters use edge locations, including:
* *CloudFront*, which uses edge locations to cache copies of the content that it serves, so the content is closer to users and can be delivered to them faster.
* *Lambda@Edge*, is a feature of Amazon CloudFront that lets you run code closer to users of your application, which improves performance and reduces latency.
* *Route 53*, which serves DNS responses from edge locations, so that DNS queries that originate nearby can resolve faster (and, contrary to what you might think, is also Amazon’s premier database).
* *Web Application Firewall* and *AWS Shield*, which filter traffic in edge locations to stop unwanted traffic as soon as possible.

**AWS Local Zones** place compute, storage, database, and other select AWS services closer to end-users. With AWS Local Zones, you can easily run highly-demanding applications that require single-digit millisecond latencies to your end-users such as media & entertainment content creation, real-time gaming, reservoir simulations, electronic design automation, and machine learning:
* A Local Zone is an extension of an AWS Region that is geographically close to your users.
* You can extend any VPC from the parent AWS Region into Local Zones by creating a new subnet and assigning it to the AWS Local Zone. When you create a subnet in a Local Zone, your VPC is extended to that Local Zone. The subnet in the Local Zone operates the same as other subnets in your VPC.

<a name="3_2"></a>
## [↖](#top)[↑](#3_1_1)[↓](#3_2_1) Virtual Private Cloud (VPC)
<!-- toc_start -->
* [Overview](#3_2_1)
  * [Default VPC (Amazon specific)](#3_2_1_1)
  * [Non-default VPC (regular VPC)](#3_2_1_2)
  * [VPC Scenarios](#3_2_1_3)
* [Core Components](#3_2_2)
* [Security Components](#3_2_3)
* [Structure & Package Flow](#3_2_4)
  * [Package flow through VPC components](#3_2_4_1)
* [Limits](#3_2_5)
<!-- toc_end -->

<a name="3_2_1"></a>
### [↖](#3_2)[↑](#3_2)[↓](#3_2_1_1) Overview
**Amazon Virtual Private Cloud (Amazon VPC)** is a service that lets you launch AWS resources in a logically isolated virtual network that you define. You have complete control over your virtual networking environment, including selection of your own IP address range, creation of subnets, and configuration of route tables and network gateways. You can use both IPv4 and IPv6 for most resources in your virtual private cloud, helping to ensure secure and easy access to resources and applications.

As one of AWS's foundational services, Amazon VPC makes it easy to customize your VPC's network configuration. You can create a public-facing subnet for your web servers that have access to the internet. It also lets you place your backend systems, such as databases or application servers, in a private-facing subnet with no internet access. Amazon VPC lets you to use multiple layers of security, including security groups and network access control lists, to help control access to Amazon EC2 instances in each subnet.
* Provisions a logically isolated section of the AWS cloud
* Spans over all AZs in a region
* Allows to create layered architecture
* Shared or dedicated tenancy (exclusive hardware or not)
  * Cannot be changed after VPC creation
* *Security groups* and subnet-level *network ACLs*
* Ability to extend on-premises network to cloud
* Can be extended *after creation* by adding 1 to utmost 4 CIDR blocks
* On AWS
	* <a href="https://aws.amazon.com/vpc/" target="_blank">Service</a> - <a href="https://aws.amazon.com/vpc/faqs/" target="_blank">FAQs</a> - <a href="https://docs.aws.amazon.com/toolkit-for-visual-studio/latest/user-guide/vpc-tkv.html" target="_blank">User Guide</a>

<a name="3_2_1_1"></a>
#### [↖](#3_2)[↑](#3_2_1)[↓](#3_2_1_2) Default VPC (Amazon specific)
* Gives easy access to a VPC without having to configure it from scratch
* Has different subnets in different AZs and an internet Gateway (HA, spread out to all AZs)
* Each instance launched automatically receives a *public IP* (and a private IP), this is usually not the case for non-default VPCs
* Cannot be restored if deleted
* Comes with default NACL that allows all inbound/outbound traffic
<a name="3_2_1_2"></a>
#### [↖](#3_2)[↑](#3_2_1_1)[↓](#3_2_1_3) Non-default VPC (regular VPC)
* Only has private IP addresses
* Resources *only* accessible through *Elastic IP*, *VPN* or *Internet Gateways*
<a name="3_2_1_3"></a>
#### [↖](#3_2)[↑](#3_2_1_2)[↓](#3_2_2) VPC Scenarios
* VPC with private subnet only -> single tier apps
* VPC with public and private subnets -> layered apps
* VPC with public, private subnets and hardware connected VPN -> extending apps to on-premises
* VPC with private subnets and hardware connected VPN -> extended VPN

<a name="3_2_2"></a>
### [↖](#3_2)[↑](#3_2_1_3)[↓](#3_2_3) Core Components
* **CIDR range**
  * VPCs are private networks and use RFC1918 ranges
    * 10.0.0.0/8 (-> `10.255.255.255`)
    * 172.16.0.0/12 (-> `172.31.255.255`)
    * 192.168.0.0/16 (-> `192.168.255.255`)
  * This guarantees that VPCs cannot conflict in the public internet
* **Subnet**
  * In exactly one AZ
  * If traffic is routed to an Internet Gateway, the subnet is known as a *public subnet*
    * Gets public IP through Internet Gateway
  * If a subnet doesn't have a route to the Internet Gateway, it's known as a *private subnet*
    * Can get internet access through NAT Gateway
  * EC2 instances are launched into subnets
  * Sometimes grouped into Subnet Groups, e.g. for caching or DB. Typically across AZs
* **Route Table**
  * Contains a set of rules, called *routes* that determine where network traffic is directed to
  * Each VPC automatically comes with a *main route table* that can be configured
    * Each subnet in a VPC must be associated with a route table; the table controls the routing for the subnet.
    * A subnet can only be associated with one route table at a time, but multiple subnets can be associated with the same route table
  * Each route in a table specifies a destination CIDR and a target
  * Every route table contains a local route for communication within the VPC
  * Has a *local route* for communication within the VPC (e.g. `172.31.0.0/16`)
  * Can have a *default route* `0.0.0.0/0` to route everything that doesn't have a specific rule

|Route Table Type|Description|
|-|-|
|Main|The route table that automatically comes with your VPC. It controls the routing for all subnets that are not explicitly associated with any other route table.|
|Subnet|A route table that's associated with a subnet.|
|Gateway|A route table that's associated with an internet gateway or virtual private gateway.|
|Local gateway|A route table that's associated with an Outposts local gateway.|

* **Elastic IP**
  * Static IPv4 address mapped to an instance or network interface
  * If attached to network interface it's decoupled from the instance's lifecycle
  * Routes to private IP address of instance
  * Can be remapped in case of failure
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
  * *Virtual Private* Gateway (VGW)
    * AWS side of Site-to-site VPN
    * Has VPN connection to customer gateway attached
    * Serves as VPN concentrator on the Amazon side of the VPN connection
    * Only one virtual private gateway can be attached to a VPC at a time
  * *Customer Gateway*
    * Customer side of Site-to-site VPN
    * A physical device or software application on your side of the VPN connection
* **NAT**
  * 'One-way valve' that allows access *to* the internet, but not *from*.
  * *NAT Instances*
    * Manually configured instance from an NAT AMI
    * Need to manually disable *source/destination check* on the instance
  * *NAT Gateway*
    * AWS-mananged service
    * HA per AZ, create one gateway per AZ
* **DNS**
  * Route53 resolver is provided for VPC (can be disabled)
    * Can provide DHCP options to provide own DNS configuration
  * DNS hostnames are provides (can be disabled)
    * Private (internal) hostname: `ip-private-ipv4-address.region.compute.internal`
    * Public (external) hostname: `ec2-public-ipv4-address.region.compute.amazonaws.com`
<a name="3_2_3"></a>
### [↖](#3_2)[↑](#3_2_2)[↓](#3_2_4) Security Components
* **Security Groups**
  * Acts as a virtual, distributed firewall to control inbound and outbound traffic to instances
  * Acts on instance level, not subnet level
  * 'Allow rules' for inbound and outbound traffic (*no* explicite deny rules)
    * All outbound traffic is allowed by default
    * All inbound traffic is denied per default
  * Support *allow* rules only
    * Cannot block individual IP adresses (use NACL for that)
  * *Stateful* - will always allow response to (allowed) outbound traffic
  * Can refer to other security groups, e.g. allow traffic from there
  * Can have mulitple security groups attached to an instance
  * Can have any number of instances within a security group
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
* **VPC Flow Logs**
  * Capture information about the IP traffic going to and from network interfaces in a VPC.
    * Contains description of networking packets, but not their payload
  * Log data can be published to Amazon CloudWatch Logs and Amazon S3
  * Can be created at 3 levels:
    * VPC
    * Subnet
    * Network interface

<a name="3_2_4"></a>
### [↖](#3_2)[↑](#3_2_3)[↓](#3_2_4_1) Structure & Package Flow
<a name="3_2_4_1"></a>
#### [↖](#3_2)[↑](#3_2_4)[↓](#3_2_5) Package flow through VPC components
* VPC (has *CIDR*)
	* Gateway (Internet or VPN)
  * Router
	* Route table (one per subnet, can be shared)
	* Network ACL (one per subnet, can be shared)
	* Subnets (CIDRs match VPC's CIDR)
	* Security Group (on VPC level)
	* Instance (needs public IP for internet communication, either ELB or Elastic IP)


<a name="3_2_5"></a>
### [↖](#3_2)[↑](#3_2_4_1)[↓](#3_3) Limits
|||
|-|-|
|VPCs per region|5|
|Min/max VPC size|`/28`/`/16`|
|Subnets per VPC|200|
|Customer gateways per region|50|
|Gateway per region|5 Internet|
|Elastic IPs per account per region|5|
|VPN connections per region|50|
|Route tables per region|200|
|Security groups per region|500|

---

<a name="3_3"></a>
## [↖](#top)[↑](#3_2_5)[↓](#3_3_1) Connecting VPCs to other VPCs
<!-- toc_start -->
* [VPC Peering](#3_3_1)
  * [Unsupported VPC peering configurations](#3_3_1_1)
  * [Establishing a VPC peering](#3_3_1_2)
  * [Longest prefix match](#3_3_1_3)
  * [Limits](#3_3_1_4)
* [Transit Gateway](#3_3_2)
  * [Overview](#3_3_2_1)
* [Previously: Transit VPC (=Software VPN)](#3_3_3)
* [AWS PrivateLink](#3_3_4)
<!-- toc_end -->

<a name="3_3_1"></a>
### [↖](#3_3)[↑](#3_3)[↓](#3_3_1_1) VPC Peering
* Connect VPCs through direct network routing
	* Cross-region, cross-account
* Allows instances to communicate with each other as if they were in the same network
	* Full private IP connectivity between VPCs
* Connectivity must be established for each VPC that need to communicate with one another
* Can reference a security group of a peered VPC (even cross-account)
* Must update route tables in each VPC’s subnets to ensure instances can communicate
* On AWS:
	* <a href="https://docs.aws.amazon.com/vpc/latest/peering/what-is-vpc-peering.html" target="_blank">Documentation</a> - <a href="https://aws.amazon.com/vpc/faqs/" target="_blank">FAQs</a>

<a name="3_3_1_1"></a>
#### [↖](#3_3)[↑](#3_3_1)[↓](#3_3_1_2) Unsupported VPC peering configurations
* *Overlapping CIDR blocks*
	* Cannot create a VPC peering connection between VPCs with matching or overlapping IPv4 CIDR blocks
* *Transitive peering*
	* You have a VPC peering connection between VPC A and VPC B (pcx-aaaabbbb), and between VPC A and VPC C (pcx-aaaacccc). There is no VPC peering connection between VPC B and VPC C. You cannot route packets directly from VPC B to VPC C through VPC A.
* *Edge to edge routing through a gateway or private connection*
	* A VPN connection or an AWS Direct Connect connection to a corporate network
	* An internet connection through an internet gateway
	* An internet connection in a private subnet through a NAT device
	* A gateway VPC endpoint to an AWS service; for example, an endpoint to Amazon S3.
	* (IPv6) A ClassicLink connection. You can enable IPv4 communication between a linked EC2-Classic instance and instances in a VPC on the other side of a VPC peering connection. However, IPv6 is not supported in EC2-Classic, so you cannot extend this connection for IPv6 communication.

<a name="3_3_1_2"></a>
#### [↖](#3_3)[↑](#3_3_1_1)[↓](#3_3_1_3) Establishing a VPC peering
* Consumer VPC initiates peering request
* Provider VPC accepts peering request
* Route tables on both sides are updated, to ensure traffic can flow

<a name="3_3_1_3"></a>
#### [↖](#3_3)[↑](#3_3_1_2)[↓](#3_3_1_4) Longest prefix match
* VPC uses the longest prefix match to select the most specific route
* Other way of saying it is “most specific route”

<a name="3_3_1_4"></a>
#### [↖](#3_3)[↑](#3_3_1_3)[↓](#3_3_2) Limits
||soft|hard|
|-|-|-|
|Active VPC peering connections per VPC|50|125|

<a name="3_3_2"></a>
### [↖](#3_3)[↑](#3_3_1_4)[↓](#3_3_2_1) Transit Gateway

<a name="3_3_2_1"></a>
#### [↖](#3_3)[↑](#3_3_2)[↓](#3_3_3) Overview
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

<a name="3_3_3"></a>
### [↖](#3_3)[↑](#3_3_2_1)[↓](#3_3_4) Previously: Transit VPC (=Software VPN)
* Not an AWS offering, newer managed solution is Transit Gateway
* Uses the public internet with a software VPN solution
* Allows for transitive connectivity between VPC & locations
* More complex routing rules, overlapping CIDR ranges, network-level packet filtering

<a name="3_3_4"></a>
### [↖](#3_3)[↑](#3_3_3)[↓](#4) AWS PrivateLink

---

<a name="4"></a>
# [↖](#top)[↑](#3_3_4)[↓](#4_1) Topics still to cover
* IPv4 vs IPv6

---

<a name="4_1"></a>
## [↖](#top)[↑](#4) Supporting Material
* [Exam Readiness: AWS Certified Advanced Networking - Specialty](https://www.aws.training/Details/Curriculum?id=21330) (free aws training)
* [AWS Networking Fundamentals](https://www.youtube.com/watch?v=hiKPPy584Mg) (youtube)

