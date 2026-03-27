<img width="455" height="310" alt="02-public-subnet-created" src="https://github.com/user-attachments/assets/fd0b6fa4-ffdc-4af7-b166-2f9b0a5f0250" /># aws-ec2-vpc-lab
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
<img width="1536" height="1024" alt="architecture-diagram" src="https://github.com/user-attachments/assets/cac95d88-3320-44fb-a777-ea4c16a51761" />


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
<img width="1651" height="387" alt="01-vpc-created" src="https://github.com/user-attachments/assets/9449bb0e-d333-437e-8538-f7fcef1f4fe1" />
<img width="455" height="310" alt="02-public-subnet-created" src="https://github.com/user-attachments/assets/b40d859f-2c38-448c-94eb-7d9a58851758" />
<img width="1116" height="154" alt="03-internet-gateway-attached" src="https://github.com/user-attachments/assets/d53807fb-5293-4650-86fe-fa49e37c1dbc" />
<img width="925" height="202" alt="04-route-table-created" src="https://github.com/user-attachments/assets/3612755b-33d4-4ccb-b920-d5b11b7652cc" />
<img width="971" height="155" alt="05-route-table-associated" src="https://github.com/user-attachments/assets/13ec8a03-95e6-4ac4-92a5-8faf34ea5f15" />
<img width="1644" height="222" alt="06-security-group-rules" src="https://github.com/user-attachments/assets/cef280eb-931e-442d-a2ee-c9ce217a6dbb" />
<img width="257" height="153" alt="07-key-pair-created" src="https://github.com/user-attachments/assets/a6d6ed85-fb03-46c4-8f29-cb773efc9ee6" />
<img width="521" height="522" alt="08-ec2-launch-summary" src="https://github.com/user-attachments/assets/3e3d4fdb-b403-4516-bff4-07044d6ddb13" />
<img width="1056" height="737" alt="09-ec2-running" src="https://github.com/user-attachments/assets/c0b0b229-f1bd-4984-bab1-10bc63cf10ec" />
<img width="661" height="418" alt="10-ec2-connected" src="https://github.com/user-attachments/assets/144394b6-517a-482a-ad3f-6164d0013bce" />
<img width="661" height="418" alt="11-apache-installed" src="https://github.com/user-attachments/assets/aeb1871b-8ac0-4f4f-aad9-675a61e20220" />
<img width="563" height="145" alt="12-webpage-working" src="https://github.com/user-attachments/assets/194a6ebd-7488-403c-82cf-0dce267feb4d" />
<img width="788" height="164" alt="13-cleanup-complete" src="https://github.com/user-attachments/assets/25879eef-8857-49ac-9ddb-d66fed117956" />

## Key Lessons Learned
- Public internet access requires both an internet gateway and a route table path
- Public subnet design depends on routing plus public IP assignment
- Security groups control instance-level access
- EC2 requires supporting VPC components to become reachable

## Cleanup
All lab resources were terminated and removed after validation to avoid unnecessary charges.
