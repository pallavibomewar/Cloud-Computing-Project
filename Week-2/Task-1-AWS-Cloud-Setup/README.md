# AWS Cloud Setup Using Amazon EC2

## Project Overview

This project focuses on launching and configuring a virtual machine using Amazon Web Services (AWS) EC2. An Ubuntu server was configured, and the Nginx web server was installed to host a basic web page accessible through the public IP address.

## Technologies Used

- Amazon Web Services (AWS)
- Amazon EC2
- Ubuntu Server 22.04 LTS
- Nginx Web Server
- AWS Security Groups
- Amazon Machine Image (AMI)

## Implementation

### 1. EC2 Instance Creation

An EC2 instance was launched using Ubuntu Server 22.04 LTS. The instance was configured with an eligible instance type and a new key pair.

**Screenshot:** EC2 Running Instance

### 2. Security Group Configuration

Inbound security rules were configured to allow SSH and HTTP traffic.

| Type | Port | Purpose |
|---|---|---|
| SSH | 22 | Remote server access |
| HTTP | 80 | Web server access |

**Screenshot:** Security Group Inbound Rules

### 3. Connecting to EC2 Instance

Connected to the Ubuntu EC2 instance using EC2 Instance Connect.

### 4. Nginx Installation

Updated the package list and installed Nginx using the following commands.

```bash
sudo apt update
sudo apt install nginx -y
```

Started and enabled the Nginx service.

```bash
sudo systemctl start nginx
sudo systemctl enable nginx
```

Verified the service status.

```bash
sudo systemctl status nginx
```

**Screenshot:** Nginx Service Status

### 5. Web Server Verification

The public IPv4 address of the EC2 instance was opened in a web browser using HTTP.

The default Nginx Welcome Page was displayed successfully.

**Screenshot:** Nginx Welcome Page

### 6. AMI Creation

An Amazon Machine Image (AMI) was created from the configured EC2 instance.

The AMI creation was verified in the AWS console, and its status showed **Available**.

**Screenshot:** AMI Available Status

## Project Outcome

- Successfully launched an Ubuntu EC2 instance.
- Configured SSH and HTTP inbound rules.
- Connected to the instance.
- Installed and started the Nginx web server.
- Verified website accessibility through the public IP address.
- Created an AMI of the configured instance.

## Conclusion

Successfully completed the AWS Cloud Setup project by deploying an Ubuntu virtual machine on Amazon EC2, configuring the Nginx web server, verifying web accessibility, and creating an AMI.

