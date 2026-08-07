# 🚀 AWS EC2 + Nginx Web Application Deployment

A high-performance, cloud-native web application deployed on **Amazon Web Services (AWS)** using **Ubuntu Linux** and **Nginx Web Server**.

---

## 📌 Executive Summary

This project demonstrates the end-to-end deployment of a custom production-ready web page hosted on an AWS EC2 instance. The infrastructure uses **Nginx** as a reverse proxy/web server to serve modern web traffic efficiently.

---

## 🏗️ Architecture & Tech Stack

* **Cloud Provider:** Amazon Web Services (AWS)
* **Compute Service:** AWS EC2 (`t2.micro` / Ubuntu 26.04 LTS)
* **Web Server:** Nginx 1.28.x
* **Frontend:** Custom HTML5 / CSS3
* **Connection & Management:** EC2 Instance Connect / SSH

---

## 🛠️ Step-by-Step Implementation Guide

### 1. Instance Provisioning & Connection
* Launched an AWS EC2 Ubuntu instance in the `us-east-1` region.
* Configured Security Group inbound rules to allow **HTTP (Port 80)** and **SSH (Port 22)** traffic.
* Connected securely via **EC2 Instance Connect**.

### 2. Web Server Setup
Updated system packages and installed Nginx:

```bash
# Update Ubuntu package index
sudo apt update -y

# Install Nginx web server
sudo apt install nginx -y
#!/bin/bash

# Update package index and upgrade existing packages
echo "Updating system packages..."
sudo apt update -y && sudo apt upgrade -y

# Install Nginx web server
echo "Installing Nginx..."
sudo apt install nginx -y

# Start and enable Nginx service
echo "Starting Nginx service..."
sudo systemctl start nginx
sudo systemctl enable nginx

# Create a custom landing page
echo "Deploying custom web application..."
cat << 'EOF' | sudo tee /var/www/html/index.html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AWS EC2 Nginx Web Server</title>
    <style>
        body { font-family: Arial, sans-serif; text-align: center; margin-top: 50px; background-color: #f4f4f9; }
        .card { background: white; padding: 40px; border-radius: 10px; display: inline-block; box-shadow: 0 4px 8px rgba(0,0,0,0.1); }
        h1 { color: #232f3e; }
        .badge { background-color: #ff9900; color: white; padding: 10px 20px; border-radius: 5px; font-weight: bold; }
    </style>
</head>
<body>
    <div class="card">
        <h1>AWS EC2 Nginx Web Server</h1>
        <p>Deployed successfully by <strong>Shahabuddin</strong></p>
        <div class="badge">Project 01 Completed</div>
    </div>
</body>
</html>
EOF

# Restart Nginx to apply changes
sudo systemctl restart nginx
echo "Deployment Complete! Web server is running."
