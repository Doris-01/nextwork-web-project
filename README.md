# Cloud Web App Deployment Project

This project demonstrates how to set up and deploy a simple web application in the cloud using **AWS EC2** and **VS Code** with GitHub integration.

---

## 🚀 Project Overview

The goal is to:

- Launch a cloud-based EC2 instance
- Set up VS Code for remote development
- Connect and sync code with a GitHub repository
- Configure and deploy your web app

---

## 🛠️ Prerequisites

- An AWS account
- GitHub account
- VS Code installed with the **Remote - SSH** extension
- SSH key pair generated via AWS or locally

---

## 1. Launch an EC2 Instance

1. Go to the AWS Console.
2. Launch an Amazon Linux 2 EC2 instance.
3. Choose instance type (e.g., `t2.micro` under Free Tier).
4. Add a security group that allows **SSH (port 22)** and **HTTP (port 80)** access.
5. Download or use an existing key pair (.pem file).

---

## 2. Set Up VS Code for Remote Development

1. Open VS Code.
2. Install the **Remote - SSH** extension from the Extensions tab.
3. Press `F1` → search for and select `Remote-SSH: Connect to Host`.
4. Use the SSH command:
   ```bash
   ssh -i /path/to/your-key.pem ec2-user@your-ec2-public-ip

Once connected, open the folder where you'll place your web app.

## 3. Set Up Git on the EC2 Instance
SSH into your EC2 instance.

Install Git if it's not already installed:

sudo yum update -y
sudo yum install git -y

## 4. Connect GitHub to Your EC2 Web App
Step 1: Create a GitHub Repo
Create a new repository on GitHub (e.g., nextwork-web-project)

Step 2: Initialize Git Locally

git init

Step 3: Set Up Git Identity

git config --global user.name "Your Name"
git config --global user.email "your@email.com"

Step 4: Add Remote Repo

git remote add origin https://github.com/your-username/nextwork-web-project.git
Replace your-username and repo name accordingly.

## 5. Authenticate Using GitHub Token
On GitHub, go to Settings > Developer Settings > Personal Access Tokens.

Generate a new token (classic), with repo permissions.

When pushing your code:

Use your GitHub username.

Use the token as your password when prompted.

## 6. Push Your Web App to GitHub
Add your project files:


git add .
Commit changes:


git commit -m "Initial commit"
Push to GitHub:

git push -u origin master

✅ Done!
Your cloud-hosted development environment is now ready, and your code is version-controlled with GitHub.
You can now continue developing and deploying your web application from the cloud!

---

