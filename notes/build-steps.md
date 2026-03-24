# Build Steps – AWS EC2 + VPC Lab

## What did you build?

I built a basic AWS network and compute environment by creating a custom Amazon VPC, a public subnet, an Internet Gateway, a route table, a security group, and an Amazon EC2 instance. The EC2 instance was launched inside the public subnet, assigned a public IP address, and configured as a simple web server using Apache.

The final result was a publicly reachable EC2-hosted web page running inside a custom VPC architecture that I built manually.

---

## Why did you build it?

I built this lab to strengthen my hands-on understanding of foundational AWS infrastructure services, especially the relationship between networking and compute. I wanted practical experience creating the underlying network components required for an EC2 instance to become reachable from the internet.

This lab also helped me create a GitHub project that demonstrates beginner-to-intermediate AWS skills in a way that is easy for recruiters and hiring managers to review.

---

## What AWS services were involved?

The following AWS services and components were used in this lab:

- **Amazon VPC** – to create an isolated virtual network
- **Public Subnet** – to host internet-accessible resources
- **Internet Gateway** – to provide internet connectivity for the VPC
- **Route Table** – to route internet-bound traffic to the Internet Gateway
- **Security Group** – to allow SSH and HTTP access to the EC2 instance
- **Amazon EC2** – to launch and run the Linux virtual server
- **EC2 Key Pair** – to securely connect to the instance
- **Amazon Linux / Apache HTTP Server** – to host a basic web page on the instance

---

## Build Process

### 1. Created a custom VPC
I created a custom VPC with the CIDR block `10.0.0.0/16` to provide the network foundation for the lab.

### 2. Created a public subnet
Inside the VPC, I created a public subnet with the CIDR block `10.0.1.0/24` and enabled auto-assign public IPv4 so resources launched into the subnet could receive public IP addresses.

### 3. Created and attached an Internet Gateway
I created an Internet Gateway and attached it to the custom VPC so the VPC could communicate with the internet.

### 4. Created a public route table
I created a custom route table and added a default route:
`0.0.0.0/0 -> Internet Gateway`

I then associated that route table with the public subnet so internet-bound traffic from the subnet would be directed correctly.

### 5. Created a security group
I created a security group for the EC2 instance with these inbound rules:

- **SSH (22)** from **My IP**
- **HTTP (80)** from **0.0.0.0/0**

This allowed secure admin access while still permitting public web traffic.

### 6. Created a key pair
I created an EC2 key pair to securely connect to the Linux instance.

### 7. Launched an EC2 instance
I launched an Amazon EC2 instance into the public subnet using the custom VPC, attached the security group, and assigned a public IP address.

### 8. Connected to the instance
I connected to the EC2 instance using either EC2 Instance Connect or SSH.

### 9. Installed Apache
After connecting, I installed Apache and started the web service using the following commands:

```bash
sudo yum update -y
sudo yum install -y httpd
sudo systemctl start httpd
sudo systemctl enable httpd
echo "<h1>EC2 + VPC Lab Web Server Working</h1>" | sudo tee /var/www/html/index.html