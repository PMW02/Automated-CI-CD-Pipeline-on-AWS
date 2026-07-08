🚀 Automated CI/CD Pipeline on AWS

📌 Overview
This project implements a complete CI/CD pipeline using AWS, Jenkins, Docker, and GitHub. Whenever code is pushed to GitHub, Jenkins automatically builds, containerizes, and deploys the application on an AWS EC2 instance.

🛠️ Tech Stack
- AWS EC2
- Amazon Linux 2023
- Git & GitHub
- Jenkins
- Docker & Docker Hub
- Nginx

🔄 Workflow
Developer → GitHub → Jenkins → Docker Build → Docker Hub → AWS EC2 → Running Website

✨ Features
- Automated build and deployment
- Dockerized application
- GitHub Webhook integration
- Continuous Integration & Continuous Deployment
- Zero manual deployment process

🚀 Deployment Steps
```bash
git clone https://github.com/PMW02/Automated-CI-CD-Pipeline-on-AWS.git
cd Automated-CI-CD-Pipeline-on-AWS
docker build -t automated-ci-cd-pipeline-on-aws:v1 .
docker run -d -p 80:80 automated-ci-cd-pipeline-on-aws:v1
```

📚 Skills Learned
- CI/CD Pipeline Development
- Jenkins Pipelines
- Docker Containerization
- AWS EC2 Deployment
- Git & GitHub Integration
- Linux Administration
