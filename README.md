
# AWS EC2 Static Website Hosting Using Nginx

## 📌 Project Overview

This project demonstrates how to host a static website on an AWS EC2 instance using the Nginx web server.

An Ubuntu Linux server is launched on AWS EC2, Nginx is installed and configured, and a custom HTML webpage is deployed and made accessible through the EC2 public IP address.

## 🛠️ Technologies Used

- **AWS EC2** – Cloud virtual server
- **Ubuntu Linux** – Operating system
- **Nginx** – Web server
- **HTML** – Website development
- **SSH** – Secure remote server access
- **Git & GitHub** – Version control and project hosting

## 🏗️ Project Architecture

User Browser → EC2 Public IP → Nginx Web Server → HTML Website

## 🚀 Implementation Steps

### 1. Launch AWS EC2 Instance

- Logged into the AWS Management Console.
- Created an EC2 instance named `my-web-server`.
- Selected Ubuntu Server as the operating system.
- Selected the `t3.micro` instance type.
- Configured an SSH key pair.

### 2. Connect to EC2 Using SSH

Connect to the Ubuntu server using the downloaded PEM private key.

```bash
chmod 400 my-web-server.pem

ssh -i my-web-server.pem ubuntu@YOUR_PUBLIC_IP
```

### 3. Update Ubuntu Packages

```bash
sudo apt update
```

### 4. Install Nginx

```bash
sudo apt install nginx -y
```

Start Nginx:

```bash
sudo systemctl start nginx
```

Enable Nginx at system startup:

```bash
sudo systemctl enable nginx
```

Verify Nginx status:

```bash
sudo systemctl status nginx
```

### 5. Create a Static Website

Create an HTML file:

```bash
sudo nano /var/www/html/index.html
```

Add your website HTML content and save the file.

### 6. Configure AWS Security Group

Configure the inbound security group rules:

| Type | Protocol | Port | Source |
|---|---|---|---|
| SSH | TCP | 22 | My IP |
| HTTP | TCP | 80 | 0.0.0.0/0 |

### 7. Access the Website

Open a web browser and enter:

```text
http://YOUR_PUBLIC_IP
```

The custom website should be displayed in the browser.

## 🔍 Verification

Check the Nginx service:

```bash
sudo systemctl status nginx
```

Test the website locally:

```bash
curl http://localhost
```

## 📚 Skills Learned

- AWS EC2 instance creation and management.
- Linux server administration.
- SSH-based remote server connectivity.
- Nginx installation and configuration.
- Static website deployment.
- AWS Security Group configuration.
- Basic web server troubleshooting.
- Git and GitHub version control.

## 🔐 Security Considerations

- Never upload PEM private keys to GitHub.
- Restrict SSH access to your own IP address.
- Use appropriate AWS Security Group rules.
- Avoid sharing AWS credentials or access keys publicly.

## 🎯 Project Outcome

The objective of this project is to understand how to deploy and host a static website on a cloud-based Linux server using AWS EC2 and Nginx.

---

**Author:** Aiswarya M  
**Project Category:** Cloud Computing & DevOps
