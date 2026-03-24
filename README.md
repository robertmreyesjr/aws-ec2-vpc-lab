# aws-ec2-vpc-lab
Hands-on AWS lab building a public EC2 web server in a custom VPC

## Overview
This project demonstrates how to deploy an Amazon EC2 instance inside a custom Amazon VPC with a public subnet, internet gateway, route table, and security group. The instance was configured as a basic web server and tested through a public IP address.

## Objectives
- Create a custom VPC
- Create a public subnet
- Attach an internet gateway
- Configure a public route table
- Create a security group for SSH and HTTP
- Launch an EC2 instance
- Connect to the instance
- Install and validate Apache web server
- Document the deployment in GitHub

## Architecture
Include architecture-diagram.png here

## Services Used
- Amazon VPC
- Amazon EC2
- Internet Gateway
- Route Table
- Security Group

## Build Steps
1. Created a VPC with CIDR 10.0.0.0/16
2. Created a public subnet with CIDR 10.0.1.0/24
3. Enabled auto-assign public IPv4 on the subnet
4. Created and attached an internet gateway
5. Created a route table with 0.0.0.0/0 to the internet gateway
6. Associated the route table with the public subnet
7. Created a security group allowing SSH from my IP and HTTP from the internet
8. Created a key pair for secure access
9. Launched an Amazon Linux EC2 instance in the custom VPC
10. Connected to the instance and installed Apache
11. Verified web access through the instance public IP
12. Cleaned up resources after testing

## Validation
- Verified instance reached running state
- Verified SSH / EC2 Instance Connect access
- Verified Apache service was active
- Verified web page loaded successfully in browser

## Screenshots
Add screenshots from the screenshots folder here

## Key Lessons Learned
- Public internet access requires both an internet gateway and a route table path
- Public subnet design depends on routing plus public IP assignment
- Security groups control instance-level access
- EC2 requires supporting VPC components to become reachable

## Cleanup
All lab resources were terminated and removed after validation to avoid unnecessary charges.
