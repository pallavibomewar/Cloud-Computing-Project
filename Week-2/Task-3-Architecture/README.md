# AWS Three-Tier Web Application Architecture

## 1. Project Overview

This project demonstrates the design of a secure, scalable, and highly available three-tier web application architecture using Amazon Web Services (AWS).

The architecture is designed using AWS networking, compute, database, storage, and security services.

**AWS Region:** eu-north-1 (Stockholm)

## 2. Architecture Diagram

The architecture diagram represents the proposed AWS three-tier web application design.

It includes:
- Virtual Private Cloud (VPC)
- Public and Private Subnets
- Internet Gateway
- Application Load Balancer
- EC2 Auto Scaling Group
- Amazon RDS Multi-AZ
- Amazon S3
- Amazon CloudFront
- AWS WAF
- IAM Roles and Security Groups

## 3. AWS Services Used

### 3.1 Amazon VPC
Amazon VPC provides an isolated network environment to launch AWS resources securely.

Existing VPC CIDR: `172.31.0.0/16`

### 3.2 Public Subnet
Public subnets are used for resources that need internet connectivity, such as internet-facing load balancers.

### 3.3 Private Subnet
Private subnets are designed to host application servers and database resources without direct public internet access.

### 3.4 Internet Gateway
An Internet Gateway connects the VPC to the internet and enables internet communication for appropriately configured public resources.

### 3.5 Application Load Balancer
The Application Load Balancer distributes incoming application traffic across multiple EC2 instances.

### 3.6 Amazon EC2
Amazon EC2 provides virtual servers to run the web application.

### 3.7 Auto Scaling
Auto Scaling automatically increases or decreases the number of EC2 instances based on application demand.

### 3.8 Amazon RDS Multi-AZ
Amazon RDS is used to store application data. Multi-AZ provides a standby database in another Availability Zone for high availability.

### 3.9 Amazon S3
Amazon S3 is used to store static files, images, and website content.

### 3.10 Amazon CloudFront
CloudFront is a Content Delivery Network (CDN) that delivers website content to users with low latency.

### 3.11 AWS WAF
AWS WAF helps protect web applications against common web attacks.

### 3.12 IAM and Security Groups
IAM manages access permissions, while Security Groups control network traffic to AWS resources.

## 4. Working Flow

1. Users access the application through a web browser.
2. Internet traffic enters the VPC through the Internet Gateway.
3. The Application Load Balancer distributes requests to EC2 application servers.
4. EC2 instances process application requests.
5. Application servers communicate with the RDS database.
6. RDS stores application data and maintains a standby database in another Availability Zone.
7. Static website files are stored in Amazon S3.
8. CloudFront delivers static content to users.
9. AWS WAF and Security Groups help protect the application.

## 5. Existing AWS Infrastructure

The following resources were already available in my AWS account:

| Resource | Existing Configuration |
|---|---|
| Region | eu-north-1 |
| VPC | vpc-0cb400a1d428c544d |
| VPC CIDR | 172.31.0.0/16 |
| Subnets | 3 Public Subnets |
| Internet Gateway | Attached |
| NAT Gateway | Not Created |
| RDS | Not Created |

## 6. Proposed Architecture Components

The following services are included in the architecture design but have not been deployed in the AWS account:

- Private Subnets
- Application Load Balancer
- EC2 Auto Scaling Group
- Amazon RDS Multi-AZ
- Amazon CloudFront
- AWS WAF

These components are proposed to improve security, scalability, and availability.

**Note:** The architecture is a proposed design, not a fully deployed application. NAT Gateway and RDS were not created to avoid unnecessary AWS charges.

## 7. Cost Estimation

The actual cost depends on the AWS Region, resource configuration, and usage duration.

The main cost components to consider are:

- EC2 instance hours
- Application Load Balancer hours and traffic
- RDS database instance hours and storage
- NAT Gateway hours and data processing, if required
- S3 storage and requests
- CloudFront data transfer
- AWS WAF web ACL and request charges

A final monthly estimate should be calculated using the AWS Pricing Calculator with the selected Region and expected usage.

AWS Pricing Calculator: https://calculator.aws/

## 8. Security Considerations

- Use private subnets for application and database resources.
- Apply IAM roles with least-privilege permissions.
- Configure Security Groups to allow only required traffic.
- Use AWS WAF to help protect web applications.
- Avoid exposing database resources directly to the internet.

## 9. Conclusion

This project helped me understand how different AWS services work together to design a three-tier web application architecture.

The proposed architecture focuses on security, scalability, and high availability using AWS networking, compute, database, storage, and security services.

It also helped me understand the importance of VPC, subnets, Availability Zones, Load Balancing, Auto Scaling, and database availability in cloud infrastructure.
