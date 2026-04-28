# Networking Design

## VPC Configuration

- Custom VPC with defined CIDR block
- Segregation of resources using subnet isolation

## Subnets

- Public Subnets:
  - Used for ALB, NAT Gateway, Bastion Host
  - Connected to Internet Gateway

- Private Subnets:
  - Used for application instances
  - No direct internet access

## Internet Gateway

- Attached to VPC
- Enables inbound and outbound internet traffic for public subnets

## NAT Gateway

- Deployed in public subnet
- Allows private instances to access internet (updates, packages)
- Prevents inbound connections from internet

## Route Tables

- Public Route Table:
  - Route: 0.0.0.0/0 → Internet Gateway

- Private Route Table:
  - Route: 0.0.0.0/0 → NAT Gateway

## Availability

- Resources distributed across multiple AZs
- Ensures fault tolerance and resilience
