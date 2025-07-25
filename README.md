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
```
### 🔹 3. Install Node.js, npm, and Git
```bash
sudo apt update
sudo apt install nodejs npm git -y
node -v
npm -v
```
### 🔹 4. Upload Project Code
```bash
git clone https://github.com/Satishchoudhary94/WanderLust.git
cd WanderLust
```
### 🔹 5. Install Dependencies and Set Up .env
```bash
cd WanderLust
npm install
```
Create a .env file in the root of the project and add:
```bash
CLOUD_NAME=
CLOUD_API_KEY=
CLOUD_API_SECRET=
MAP_API_KEY=
ATLAS_URL=mongodb+srv://schoudhary3741:7y7EW1oIqPGKRpKk@cluster0.d6ptcxb.mongodb.net/?retryWrites=true&w=majority&appName=Cluster0
or
MONGO_URL=your_mongodb_connection_string
```
### 🔹 6. Start the Server
```bash
node app.js
```
### 🔹 8. Access the App
```bash
http://<your-ec2-public-ip>:3000
```

📁 Project Structure Overview
```bash
WanderLust/
├── app.js
├── package.json
├── .env
├── /routes
├── /views
├── /models
├── /controllers
├── /public
```
👨‍💻 Author
Satish Choudhary
GitHub: @Satishchoudhary94

Thanks



