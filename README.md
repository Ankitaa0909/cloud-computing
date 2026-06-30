You work for XYZ Corporation and based on the expansion requirements of your corporation you have been asked to create and set up a distinct Amazon VPC for the production and development team. You are expected to perform the following tasks for the respective VPCs. Production Network: 1. Design and build a 4-tier architecture. 2. Create 5 subnets out of which 4 should be private named app1, app2, dbcache and db and one should be public, named web. 3. Launch instances in all subnets and name them as per the subnet that this was the assignment I didthey have been launched in. 4. Allow dbcache instance and app1 subnet to send internet requests. 5. Manage security groups and NACLs. Development Network: 1. Design and build 2-tier architecture with two subnets named web and db names. 2. Make sure only the web subnet can send internet requests. 3. Create peering connection between production network and development network. 4. Setup connection between db subnets of both production network and# AWS Multi-Tier VPC Architecture (Production & Development)

---

Project Overview
This project demonstrates the design and implementation of a secure multi-tier cloud network architecture on AWS. The objective was to create separate Production and Development environments using Amazon VPC and configure networking components to simulate a real enterprise infrastructure.

The architecture includes public and private subnets, EC2 instances, route tables, NAT configuration, VPC peering, and security controls.

---

Architecture Design
Production Network (4-Tier Architecture)
The production VPC is designed using a 4-tier architecture consisting of:

Web Layer
Application Layer
Cache Layer
Database Layer

## 🔗 Subnets Created

| Subnet | Type | CIDR | Purpose |
|:-------|:-----|:-----|:--------|
| `web` | Public | `10.0.1.0/24` | Internet-facing web server |
| `app1` | Private | `10.0.2.0/24` | Application server |
| `app2` | Private | `10.0.3.0/24` | Application server |
| `dbcache` | Private | `10.0.4.0/24` | Cache layer |
| `db` | Private | `10.0.5.0/24` | Database layer |

## 🖥️ EC2 Instances

Instances were deployed in each subnet to simulate application components.

| Instance Name | Subnet | Role |
|:--------------|:-------|:-----|
| `web` | `web` subnet | Web server |
| `app1` | `app1` subnet | Application server |
| `app2` | `app2` subnet | Application server |
| `prod-dbcache` | `dbcache` subnet | Cache layer |
| `prod-db` | `db` subnet | Database server |

Internet Access Rules
web subnet connects to the internet via Internet Gateway
app1 and dbcache are allowed to send outbound internet requests
db subnet remains fully private
Development Network (2-Tier Architecture)
The development VPC uses a 2-tier architecture.

---

Subnets Created
## 🔗 Subnets Created

| Subnet | Type | Purpose |
|:-------|:-----|:--------|
| `web`  | Public | Web access for development |
| `db`   | Private | Development database |

Network Rules
Only web subnet can access the internet
db subnet is isolated

---

VPC Peering

A VPC Peering connection was created between:

Production VPC
Development VPC
This allows private communication between both networks without using the internet.

Database Connectivity
A secure connection was configured between:

Production DB subnet
Development DB subnet
This enables controlled communication between both environments.

---

Security Implementation
Security Groups
Security groups were configured to control instance-level traffic.

---

Examples:

Web server allows HTTP/HTTPS
Application servers allow traffic from web tier
Database servers allow traffic only from application tier
Network ACLs (NACLs)
NACLs were implemented to provide subnet-level traffic filtering.

---

AWS Components Used
Amazon VPC
Public and Private Subnets
EC2 Instances
Internet Gateway
NAT Gateway
Route Tables
Security Groups
Network ACLs
VPC Peering

## 💰 Estimated Infrastructure Cost

Approximate cost of the architecture:

| Resource | Estimated Monthly Cost |
|:---------|:----------------------:|
| EC2 Instances (5 × `t3.micro`) | ~$37 |
| NAT Gateway | ~$32 |
| Other Networking Components | Free |

**Total Estimated Cost:** **~$70/month**

---

Resource	Estimated Monthly Cost
EC2 Instances (5 × t3.micro)	~$37
NAT Gateway	~$32
Other Networking Components	Free
Total Estimated Cost: ~$70/month

Key Learning Outcomes
Through this project, the following AWS networking concepts were implemented:

Multi-tier cloud architecture design
Public vs private subnet isolation
Controlled internet access
Route table configuration
NAT gateway usage
VPC peering between environments
Security groups and NACL management
Screenshots
Screenshots of the AWS console showing:

Subnet configuration
EC2 instances
Network architecture
are included in this repository.

Author
Ankita Kadam 
Cloud & DevOps Enthusiast Working on AWS infrastructure, DevOps automation, and cloud architecture projects.
Anubhav Sharma

Cloud & DevOps Enthusiast Working on AWS infrastructure, DevOps automation, and cloud architecture projec
