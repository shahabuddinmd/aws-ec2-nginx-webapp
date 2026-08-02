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
