# AWS Project – Troubleshooting Guide

This document covers troubleshooting activities and common infrastructure issues investigated during the AWS Capstone Project.

## 1. Application Load Balancer – 502 Bad Gateway

**Issue:**

The application returned a 502 Bad Gateway error when accessed through the Application Load Balancer DNS endpoint.

**Investigation:**
- Checked the Target Group health status.
- Verified EC2 instance status.
- Reviewed application service status.
- Checked security group inbound rules.
- Verified application listening ports.
- Investigated connectivity between the ALB and EC2 instances.

**Resolution:**

Verified the application service, port configuration, health check settings and security group rules to identify the cause.

**Learning:**

Understood how ALB communicates with registered targets and how incorrect application configuration can affect application availability.

## 2. Target Group – Unhealthy Instances

**Issue:**

EC2 instances were showing an unhealthy status in the ALB Target Group.

**Investigation:**
- Checked target group health check configuration.
- Verified the application port.
- Reviewed health check path.
- Checked EC2 security group rules.
- Verified application availability on the EC2 instance.

**Resolution:**

Investigated the health check configuration and application connectivity to identify and correct the issue.

**Learning:**

Learned how ALB health checks monitor application availability and determine whether targets can receive traffic.

## 3. EC2 – SSH Connectivity Issue

**Issue:**

Experienced SSH connection timeout while attempting to connect to an EC2 instance.

**Investigation:**
- Checked EC2 instance state.
- Verified instance status checks.
- Reviewed security group inbound SSH rules.
- Checked network connectivity and subnet routing.
- Verified the correct key pair and connection details.

**Resolution:**

Investigated network access, SSH permissions and connectivity configuration.

**Learning:**

Improved understanding of EC2 remote connectivity and network-level troubleshooting.

## 4. Application Port Configuration

**Issue:**

The application was not responding as expected on the configured ports.

**Investigation:**
- Checked the application service status.
- Verified listening ports.
- Reviewed security group rules.
- Checked ALB listener and target group port configuration.

**Resolution:**

Investigated application and load balancer port configurations to ensure that traffic was directed to the correct application port.

**Learning:**

Understood the importance of matching application ports, listener configurations and target group settings.

## 5. EFS Mounting and Connectivity

**Issue:**

Investigated EFS mounting and accessibility from EC2 instances.

**Investigation:**
- Checked EFS file system status.
- Verified mount targets.
- Reviewed security group rules.
- Checked NFS connectivity on port 2049.
- Verified the EFS mount status on EC2.

**Resolution:**

Reviewed mount target availability, network access and mount configuration.

**Learning:**

Improved understanding of shared storage, NFS connectivity and EFS integration with EC2.

## Key Takeaways

- Developed practical AWS infrastructure troubleshooting skills.
- Improved understanding of network connectivity and security groups.
- Learned to investigate ALB and Target Group health issues.
- Practiced EC2 connectivity troubleshooting.
- Improved understanding of EFS mounting and shared storage.

**Note:** This document describes troubleshooting activities performed during the project. Specific resolutions should be updated with the actual root causes and corrective actions verified during implementation.