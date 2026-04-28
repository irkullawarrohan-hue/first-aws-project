# Architecture Overview

This project demonstrates a highly available and secure AWS infrastructure for hosting a web application using best practices.

## Core Components

- VPC with isolated networking
- Public and Private subnets across multiple Availability Zones
- Internet Gateway for inbound internet access
- NAT Gateway for outbound internet access from private instances
- Bastion Host for secure SSH access
- Application Load Balancer (ALB) for traffic distribution
- Auto Scaling Group (ASG) for high availability and scaling
- EC2 instances hosting the application

## Architecture Design

- Public Subnets:
  - ALB
  - NAT Gateway
  - Bastion Host

- Private Subnets:
  - Application EC2 instances (ASG)

## Request Flow

1. User sends request via browser
2. DNS resolves to ALB
3. ALB listens on port 80
4. ALB forwards traffic to target group
5. Target group routes to EC2 instances on port 8000
6. Response returns back through ALB to user

## Key Design Decisions

- Instances are placed in private subnets for security
- ALB acts as the only public entry point
- Bastion host is used for controlled SSH access
- Auto Scaling ensures fault tolerance and availability
