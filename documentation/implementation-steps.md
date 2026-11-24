# AWS Project – Implementation Steps

## 1. Project Setup

**Project Name:** Resilient and Scalable Web Application Deployment on AWS

**AWS Region:** Asia Pacific (Mumbai) – ap-south-1

**Availability Zones:**
- ap-south-1a
- ap-south-1b

The project was implemented using AWS services to build a highly available and scalable web application infrastructure.

## 2. VPC Configuration

- Created a custom Virtual Private Cloud (VPC).
- Configured IPv4 CIDR block: `192.168.0.0/24`.
- Created an isolated networking environment for the application.
- Configured networking resources across two Availability Zones.

## 3. Subnet Configuration

Created four subnets across two Availability Zones.

| Subnet | CIDR Block | Availability Zone |
|---|---|---|
| Public Subnet 1A | 192.168.0.0/26 | ap-south-1a |
| Public Subnet 2B | 192.168.0.64/26 | ap-south-1b |
| Private Subnet 1A | 192.168.0.128/26 | ap-south-1a |
| Private Subnet 2B | 192.168.0.192/26 | ap-south-1b |

Configured public and private subnet separation to support application security and network isolation.

## 4. Internet Gateway and NAT Gateway

- Created an Internet Gateway and attached it to the custom VPC.
- Created a NAT Gateway in a public subnet.
- Configured internet connectivity for public resources.
- Enabled outbound internet connectivity for resources in private subnets through NAT Gateway routing.

## 5. Route Table Configuration

- Created separate public and private route tables.
- Associated public route tables with public subnets.
- Associated private route tables with private subnets.
- Configured the default internet route through the Internet Gateway for public subnets.
- Configured the default outbound route through the NAT Gateway for private subnets.

## 6. EC2 Configuration

- Launched Amazon EC2 instances.
- Selected the required Amazon Machine Image (AMI) and instance type.
- Configured security groups and network access.
- Installed the required application dependencies.
- Deployed the web application on EC2 instances.

## 7. Amazon EFS Configuration

- Created an Amazon Elastic File System (EFS).
- Configured EFS mount targets across the Availability Zones.
- Configured network access using security groups.
- Mounted the EFS file system on the EC2 instances.
- Verified shared storage access between application instances.

## 8. Launch Template and Auto Scaling

- Created a custom AMI based on the configured application environment, if applicable.
- Created an EC2 Launch Template.
- Configured an Auto Scaling Group.
- Selected the required Availability Zones and subnets.
- Defined minimum, maximum and desired instance capacity.
- Configured scaling policies to adjust EC2 capacity based on demand.

## 9. Application Load Balancer Configuration

- Created an internet-facing Application Load Balancer.
- Selected the required public subnets across two Availability Zones.
- Created and configured a target group.
- Configured listener rules and health checks.
- Integrated the target group with the Auto Scaling Group.
- Verified target registration and health status.

## 10. Application Testing and Validation

- Accessed the application using the Application Load Balancer DNS endpoint.
- Verified application accessibility.
- Checked target group health status.
- Tested connectivity between application components.
- Verified EFS shared storage functionality.
- Checked Auto Scaling Group activity and instance behaviour.

## 11. Troubleshooting and Optimization

During implementation, investigated infrastructure and application connectivity issues.

Activities included:
- Troubleshooting EC2 connectivity.
- Investigating unhealthy target group instances.
- Checking application port configuration.
- Verifying security group rules.
- Checking EFS mount status and storage accessibility.

Refer to `troubleshooting.md` for detailed issues and resolutions.

## 12. Future Enhancement

- Integrate Amazon Route 53 for custom domain management and DNS routing.
- Configure HTTPS using AWS Certificate Manager.

## 13. Project Completion

Successfully completed the core infrastructure implementation and application deployment activities.

This project provided practical experience in AWS networking, compute, shared storage, load balancing, Auto Scaling and infrastructure troubleshooting.