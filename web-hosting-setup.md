# 🛠️ Web Hosting Setup on AWS EC2 (Amazon Linux 2)

This guide explains how to host a static website on an **AWS EC2 instance** using **Apache HTTP Server**, managed entirely through the AWS Management Console.

---

### 🚀 Step-by-Step Hosting Instructions

### 🔹 Step 1: Launch EC2 Instance
1. Go to [AWS EC2 Console](https://console.aws.amazon.com/ec2/)
2. Click **Launch Instance**
3. Set the following:
   - **Name**: `WebServer`
   - **AMI**: Amazon Linux 2
   - **Instance Type**: `t2.micro` (Free Tier eligible)
   - **Key Pair**: Create new or use existing
4. Under **Network Settings**:
   - Create or select a security group
   - Allow the following:
     - ✅ SSH (port 22)
     - ✅ HTTP (port 80)
5. Launch the instance

---
### 🔹 Step 2: Connect to EC2 via Browser Console

1. Go to **EC2 > Instances**
2. Select your running instance
3. Click **Connect**
4. Choose **EC2 Instance Connect**
5. Click **Connect** to open the terminal as `root`

---
### 🔹 Step 3: Install Apache Web Server

sudo yum update -y
sudo yum install httpd -y

---
### 🔹 Step 4: Start and Enable Apache

sudo systemctl start httpd
sudo systemctl enable httpd

---
### 🔹 Step 6: Create index.html File (Your Website)

sudo vim /var/www/html/index.html

then paste the index.html file
add other few other files as well (demo.html)

---
### 🔹 Step 8: Access Your Website

Open your browser & go to: `http://your-ec2-public-ip`

Note-This will eventually land you to the index.html file, but for other files we need to write down the file name as well.
`http://your-ec2-public-ip/filename`
