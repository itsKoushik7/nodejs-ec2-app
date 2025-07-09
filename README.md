# 🚀 Node.js App Deployment on AWS EC2 (Free Tier)

This project demonstrates how to deploy a basic Node.js + Express application on an AWS EC2 instance using the Free Tier. It includes everything from local setup to live deployment with PM2 for process management.

---

 📦 Tech Stack

- Backend: Node.js, Express.js
- Cloud: AWS EC2 (Ubuntu 20.04)
- DevOps Tools: Git, PM2, SSH
- Version Control: Git + GitHub
- Operating System: Ubuntu Linux

---

 🧩 Features

- Full-stack Node.js app created and tested locally
- Code pushed to GitHub for version control
- EC2 instance setup with SSH key and security groups
- App deployed on EC2 with public access
- PM2 used for auto-restarts and production-like behavior

---

 🌐 Live App URL (While EC2 is Running)



> Replace with your actual EC2 IP.

---

 📁 Project Folder Structure

my-app/
├── bin/ # Express server entry point
├── public/ # Static files
├── routes/ # Route handlers
├── views/ # Templates (if used)
├── app.js # Main application file
├── package.json # Project metadata and dependencies
├── .gitignore
└── README.md



---

 🛠 Step-by-Step Deployment Guide

# 1. 🔧 Local Setup

```bash
npx express-generator my-app
cd my-app
npm install
npm start

Check in browser: http://localhost:3000



3. ☁️ Launch EC2 Instance
Go to AWS EC2 Console

Select Ubuntu 20.04 LTS

Instance Type: t2.micro (Free Tier)

Create/download .pem key pair

Configure Security Group:

Allow port 22 (SSH)

Allow port 3000 (Custom TCP)


4. 🔐 SSH Into EC2

chmod 400 your-key.pem
ssh -i your-key.pem ubuntu@<your-ec2-public-ip>


5. ⚙️ Install Dependencies on EC2
sudo apt update
sudo apt install nodejs npm git -y
node -v
npm -v


6. 📥 Clone & Run App on EC2

git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
npm install
npm start



Test in browser:

http://<your-ec2-public-ip>:3000


🔐 Security Group Rules

| Type       | Protocol | Port | Source    |
| ---------- | -------- | ---- | --------- |
| SSH        | TCP      | 22   | 0.0.0.0/0 |
| Custom TCP | TCP      | 3000 | 0.0.0.0/0 |


⛔ Don’t Forget to Stop EC2 When Done
# In AWS Console:
EC2 → Instances → Select Instance → Instance State → Stop


🧠 Key Learnings
Setting up and securing EC2 instances

Using Git and GitHub for CI-style workflow

Hosting a live Node.js app on the cloud

Using PM2 to keep the app running in production




👨‍💻 Author
LaxmiKoushik Nandikanti

GitHub : https://github.com/itsKoushik7
Linkedin : https://www.linkedin.com/in/nlkoushik/


