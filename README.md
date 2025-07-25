# 🌍 WanderLust - Deploy Node.js App on AWS EC2 (Without Docker)

WanderLust is a full-stack Node.js web application that can be deployed on an AWS EC2 instance without using Docker. This guide walks you through every step to host your app using PM2 and Node.js on Ubuntu.

---

## 🚀 Deployment Steps (No Docker Required)

### 🔹 1. Launch EC2 Instance

1. Go to [AWS EC2 Console](https://console.aws.amazon.com/ec2/)
2. Click **Launch Instance**
3. Choose:
   - **Amazon Machine Image (AMI):** Ubuntu 22.04
   - **Instance Type:** t2.micro (Free Tier eligible)
   - **Key Pair:** Create or use an existing `.pem` file
4. **Security Group Configuration:**
   - ✅ Allow SSH (Port 22)
   - ✅ Allow HTTP (Port 80)
   - ✅ Add Custom TCP Rule: Port `3000`, Source: `0.0.0.0/0`

---

### 🔹 2. Connect to EC2

```bash
ssh -i /path/to/your-key.pem ubuntu@<your-ec2-public-ip>
