# DevOps Project 4 - Containerize an Application Using Docker

## 📌 Project Overview
This project demonstrates how to containerize a Node.js application using Docker.  
The application is built into a Docker image and deployed inside a container on AWS EC2.

---

## 🎯 Objective
To create a Docker image and run an application inside a container so that it works consistently across different environments.

---

## 🛠 Tools & Technologies Used
- Docker
- Node.js
- Ubuntu Linux
- AWS EC2
- Git & GitHub

---

## 🖥 Infrastructure Details
- Cloud Platform: AWS EC2
- Operating System: Ubuntu Linux
- Instance Type: t2.micro
- Access Method: SSH

---

## 📁 Project Structure
docker-project/
│
├── Dockerfile
├── app.js
└── package.json

yaml
Copy code

---

## 📝 Application Code

### app.js
A simple Node.js HTTP server running on port 3000.

---

## 📦 Dockerfile

FROM node:18-alpine
WORKDIR /usr/src/app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 3000
CMD ["npm", "start"]

yaml
Copy code

---

## 🔨 Docker Commands Used

### Build Docker Image
docker build -t docker-demo-app .

shell
Copy code

### Run Docker Container
docker run -d -p 3000:3000 --name docker-container docker-demo-app

shell
Copy code

### Verify Running Container
docker ps

yaml
Copy code

---

## 🌐 Application Access

Browser:
http://<EC2-PUBLIC-IP>:3000

yaml
Copy code

Expected Output:
Hello from Docker Container!

yaml
Copy code

---

## 📊 Docker Workflow

Dockerfile → Docker Image → Docker Container → Port Mapping → Browser Access

---

## ✅ Outcome
- Docker image successfully built
- Container running on AWS EC2
- Port 3000 exposed
- Application accessible through browser

---

## 📌 Author
Adwaith Rahul  
DevOps Internship Project
