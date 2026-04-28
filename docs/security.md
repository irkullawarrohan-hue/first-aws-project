# Security Design

## Security Groups

### Load Balancer Security Group

- Inbound:
  - HTTP (80) from 0.0.0.0/0

- Outbound:
  - All traffic allowed

### EC2 Instance Security Group

- Inbound:
  - Port 8000 from ALB Security Group only

- Outbound:
  - All traffic allowed

### Bastion Host Security Group

- Inbound:
  - SSH (22) from trusted IP (or 0.0.0.0/0 for demo)

- Outbound:
  - All traffic allowed

## Security Principles Applied

- Least privilege access
- No direct internet exposure of application servers
- Controlled SSH access via bastion host
- Separation of public and private resources
