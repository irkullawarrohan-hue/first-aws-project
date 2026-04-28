# Troubleshooting

## Issue: Target Group Unhealthy

Cause:
- Application not running on port 8000
- Health check mismatch

Fix:
- Verified application running
- Corrected port and health check settings

---

## Issue: Unable to access application via ALB

Cause:
- Security group blocking traffic

Fix:
- Allowed port 8000 from ALB to EC2

---

## Issue: SSH access not working

Cause:
- Incorrect key or security group rules

Fix:
- Verified key pair
- Opened port 22 in bastion security group

---

## Issue: No internet access in private instances

Cause:
- NAT Gateway or route table misconfiguration

Fix:
- Verified NAT Gateway placement
- Updated private route table
