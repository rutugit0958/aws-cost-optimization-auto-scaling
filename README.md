
# AWS Cost Optimization with Auto Scaling

##  Project Overview
This project demonstrates how to implement cost optimization in AWS using free-tier eligible resources, minimal infrastructure, and Auto Scaling to avoid over-provisioning. The setup ensures that resources scale only when needed, helping reduce unnecessary cloud costs.

---

##  Objective
To build a cost-efficient AWS infrastructure by:
- Using free-tier / low-cost instances
- Allocating minimal resources
- Enabling Auto Scaling based on load
- Setting budget alerts to control spending

---

## Services Used
- AWS EC2 (Ubuntu AMI)
- t3.micro (free-tier / low-cost eligible)
- Launch Template
- Auto Scaling Group (ASG)
- Application Load Balancer (ALB)
- CloudWatch Monitoring
- AWS Budgets

---

## ⚙️ Implementation Steps

###  EC2 Setup
- Launched Ubuntu EC2 instance
- Selected **t3.micro** for cost efficiency
- Configured minimal storage and default VPC
- Allowed HTTP and SSH in Security Group

###  Application Setup
- Deployed a simple web application on EC2
- Verified access using public IP

###  AMI Creation
- Created a custom AMI from configured EC2 instance
- Used as base image for scaling

###  Launch Template
- Created launch template using custom AMI
- Set instance type to t3.micro
- Attached security group and key pair

###  Load Balancer
- Created Application Load Balancer
- Configured target group and health checks
- Routed HTTP traffic to instances

###  Auto Scaling Group
- Created ASG using launch template
- Min capacity: 1
- Desired capacity: 1
- Max capacity: 2 (cost control limit)

###  Scaling Policy
- Target tracking policy based on CPU utilization
- Scale out when CPU increases
- Scale in when load decreases
- Prevents over-provisioning

###  Budget Control
- Configured AWS Budget alert
- Set monthly cost limit
- Enabled alert notification

---

##  Load Testing
- Performed CPU stress test on instance
- Observed CPU spike in CloudWatch
- Verified Auto Scaling activity triggered

---

##  Cost Optimization Techniques Used
- Free-tier / low-cost instance type
- Minimal resource allocation
- Limited max instance count
- Automatic scale in/out
- Budget alerts enabled
- Avoided idle over-provisioned servers

---

##  Project Proof
All setup and testing screenshots are available in the **screenshots** folder of this repository.

---
## Author ##
Rutuja Patil
