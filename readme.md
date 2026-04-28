# AWS Scalable Web Application Deployment

## Overview
This project demonstrates the deployment of a scalable and highly available web application on AWS using core infrastructure services. The architecture is designed with security, fault tolerance, and scalability in mind.

## Architecture Summary
The application is deployed inside a custom VPC with both public and private subnets across multiple availability zones.

- Public Subnets:
  - Application Load Balancer (ALB)
  - NAT Gateway
  - Bastion Host

- Private Subnets:
  - EC2 instances running the application
  - Auto Scaling Group

## Services Used
- Amazon EC2
- Auto Scaling Group
- Application Load Balancer
- VPC
- Subnets (Public and Private)
- Internet Gateway
- NAT Gateway
- Route Tables
- Security Groups

## Application Access
The application is accessible through the Load Balancer DNS:

http://first-aws-project-1763822301.us-east-1.elb.amazonaws.com

## Traffic Flow
1. The user sends a request to the Load Balancer DNS on port 80
2. The Internet Gateway allows incoming traffic into the VPC
3. The Application Load Balancer receives the request
4. The Load Balancer forwards traffic to the target group
5. Target group routes traffic to EC2 instances on port 8000
6. The response is sent back to the user through the Load Balancer

## Security Design
- Load Balancer Security Group allows HTTP traffic from the internet on port 80
- EC2 Security Group allows traffic only from the Load Balancer on port 8000
- SSH access is restricted through a Bastion Host
- Private EC2 instances do not have public IP addresses

## Auto Scaling Configuration
- Minimum instances: 1
- Desired instances: 2
- Maximum instances: 4
- Instances are distributed across multiple availability zones

## High Availability
- Multi-AZ deployment ensures fault tolerance
- Load Balancer distributes traffic evenly across instances
- Health checks ensure only healthy instances receive traffic

## Key Features
- Scalable architecture using Auto Scaling
- Secure network design using private subnets
- Centralized access using Load Balancer
- Controlled outbound internet access using NAT Gateway

## Challenges Faced
- Initial Load Balancer routing issues
- Security group misconfiguration between ALB and EC2
- Port mismatch between Load Balancer and application

## Solutions Implemented
- Corrected security group rules to allow ALB to EC2 communication
- Configured target group to use correct application port (8000)
- Verified health checks and listener configuration

## Proof of Deployment
Refer to the screenshots folder for:
- Load Balancer configuration
- Target group health status
- Auto Scaling setup
- EC2 instances in private subnets
- Security groups and networking components

## Learning Outcomes
- Understanding of VPC architecture and subnet isolation
- Practical implementation of Load Balancer and Auto Scaling
- Security group configuration and traffic control
- Real-world troubleshooting of AWS networking issues
