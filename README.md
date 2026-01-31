# CI/CD Pipeline on EC2 using Jenkins + Docker

## Project Overview
This project demonstrates a full **CI/CD pipeline** using **Jenkins** and **Docker** on an **EC2 instance**.  
The application is a simple **Node.js HTTP server** (or Python Flask app) that is automatically built, containerized, and deployed whenever changes are pushed to GitHub.

## Architecture
Developer
│
▼
GitHub Repository
│
▼
Jenkins (EC2)
├─ Pulls code
├─ Builds Docker image
└─ Deploys container
│
▼
Node.js App (EC2)

## Project Structure
ci-cd-jenkins-docker/
│
├── app/ # Application source code
│ ├── index.js # Main server file
│ └── package.json # Node.js dependencies
│
├── Dockerfile # Docker image definition
├── Jenkinsfile # CI/CD pipeline instructions
├── README.md # Project documentation
└── .gitignore # Files to ignore in git

## Prerequisites
- Ubuntu 22.04 EC2 instance
- Docker & Docker Compose installed
- Git installed
- Open ports in Security Group:
  - SSH (22)
  - Jenkins (8080)
  - Application port (3000 or 5000)
 
## Setup Instructions
1. Clone Repo
   git clone https://github.com/<username>/<repo>.git
   cd <repo>
2. Build Docker Image
   docker build -t project2-app .
3. Run Application
   docker run -d -p 3000:3000 --name project2-app project2-app
4. Test the app:
   http://<EC2_PUBLIC_IP>:5000

   

## CI/CD Pipeline   
Jenkins Pipeline is defined in Jenkinsfile
Stages:
Clone the repository
Build Docker image
Deploy container on EC2
Automatic deployment occurs when code is pushed to GitHub.

  
