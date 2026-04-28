# Deployment Steps

## Step 1: Create VPC
- Define CIDR block
- Enable DNS hostnames

## Step 2: Create Subnets
- 2 Public Subnets (different AZs)
- 2 Private Subnets (different AZs)

## Step 3: Configure Internet Gateway
- Create and attach to VPC

## Step 4: Setup NAT Gateway
- Create in public subnet
- Associate Elastic IP

## Step 5: Configure Route Tables
- Public → Internet Gateway
- Private → NAT Gateway

## Step 6: Launch Bastion Host
- Place in public subnet
- Enable SSH access

## Step 7: Create Launch Template
- Define AMI, instance type, security group
- Configure application on port 8000

## Step 8: Create Target Group
- Protocol: HTTP
- Port: 8000
- Register instances

## Step 9: Create Application Load Balancer
- Internet-facing
- Listener: HTTP (80)
- Attach target group

## Step 10: Create Auto Scaling Group
- Attach launch template
- Attach target group
- Set min, max, desired capacity

## Step 11: Verify Deployment
- Access ALB DNS
- Confirm application loads successfully
