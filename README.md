# AWS EC2 + Django Notes App Deployment (Shell Scripts)

This project contains shell scripts to:

1. **Create and prepare an AWS EC2 instance**  
2. **Deploy a Django Notes app using Docker & Docker Compose**

It is mainly for **DevOps / Cloud Automation practice** using **Bash, AWS CLI, Docker, and Nginx**.

---

## 📁 Project Files

- `prep_ec2.sh`  
  - Checks/installs **AWS CLI**
  - Creates an **EC2 instance** with given configuration
  - Waits until the instance is in **running** state

- `clone.sh`  
  - Clones the **Django Notes App** repository  
  - Installs required packages: **Docker, Docker Compose, Nginx**
  - Fixes Docker socket permission
  - Builds the Docker image and runs the app using **Docker Compose**

---

## ✅ Prerequisites

Before using these scripts, make sure you have:

- An **AWS account**
- **AWS CLI** installed & configured locally (`aws configure`)
- A **VPC, Subnet, Security Group, and Key Pair** already created in AWS
- **Git** installed on your local machine
- Basic knowledge of **Linux terminal**, **SSH**, and **EC2**

---

## ⚙️ Configure `prep_ec2.sh`

Open `prep_ec2.sh` and update these variables:

```bash
AMI_ID=""            # e.g. ami-0abcdef1234567890
INSTANCE_TYPE="t2.micro"
KEY_NAME=""          # Your existing EC2 key pair name
SUBNET_ID=""         # Subnet ID where you want to launch instance
SECURITY_GROUP_IDS="" # One or more security group IDs
INSTANCE_NAME="Shell-Script-EC2-Demo"
