# 🌦️ Serverless Containerized Weather App on AWS (ECS + Terraform)

[![Infrastructure](https://img.shields.io/badge/Infrastructure-Terraform-5C4EE5?logo=terraform)](https://www.terraform.io/)
[![Platform](https://img.shields.io/badge/Platform-AWS-232F3E?logo=amazon-aws)](https://aws.amazon.com/)
[![Container](https://img.shields.io/badge/Container-Docker-2496ED?logo=docker)](https://www.docker.com/)
[![Backend](https://img.shields.io/badge/Backend-Flask-000000?logo=flask)](https://flask.palletsprojects.com/)


A Python Flask weather app, containerized with Docker and deployed on AWS ECS using Terraform. This project showcases how to build and deploy a scalable, serverless cloud-native application with secure networking and automated infrastructure.

---

## 📅 Project Date
**March 28, 2025**  
**Author**: Harvey Aland

---

## 🔍 Overview
- Flask backend fetching live weather data from OpenWeatherMap API
- Dockerized and hosted on ECS with Fargate
- Load-balanced via Application Load Balancer (ALB)
- Secure VPC with public/private subnets and NAT
- Provisioned entirely using Terraform

---

## 🧱 Tech Stack
- **Frontend**: HTML (Jinja2)
- **Backend**: Python (Flask)
- **Containerization**: Docker
- **Infrastructure**: ECS Fargate, ALB, VPC, IAM, Terraform
- **API**: OpenWeatherMap

---

## 📷 Demo

### 🔥 1. App Deployed via ALB (AWS ECS)
![Weather app live on ALB](screenshots/ALB%20DNS%20in%20url%20showing%20the%20container%20is%20now%20live.png)  
_App running live via Application Load Balancer in AWS._

---

### ⚙️ 2. ECS Service with Fargate Tasks
![ECS Fargate tasks running](screenshots/ECS%20cluster%20running%20with%20ecs%20tasks.png)  
_ECS cluster with 2 Fargate tasks managed by Terraform._

---

### ✅ 3. ALB Target Group Health Checks
![Health check success](screenshots/ALB%20Target%20group%20checking%20app%20health%20on%20Port%205000.png)  
_ALB verifying health of ECS tasks using `/health` route._

---

### 🐳 4. Docker Image Build
![Docker build process](screenshots/running%20the%20build%20command%20.png)  
_Building and tagging the Flask weather app Docker image._

---

### 📦 5. Terraform Infrastructure Apply
![Terraform apply](screenshots/Terraform%20apply%20on%20the%20code%20.png)  
_Provisioning VPC, ECS, ALB, IAM roles, and networking._

---

### 🌐 6. VPC Network Architecture
![VPC structure](screenshots/VPC%20with%20network%20map.png)  
_Secure VPC with public/private subnets and NAT Gateway._

---

## 📂 Project Structure

```
ECS/
├── app/
│   ├── Dockerfile
│   ├── requirements.txt
│   └── weather_app.py
├── templates/
│   └── index.html
├── terraform/
│   ├── main.tf
│   ├── outputs.tf
│   ├── providers.tf
│   └── modules/
├── screenshots/
├── docs/
│   └── Weather App Project Breakdown.pdf
└── README.md
```

---

## 🚀 Quick Start

```bash
# 1. Build the Docker image
docker build -t flask-weather-app .

# 2. Tag and push to ECR
docker tag flask-weather-app <account_id>.dkr.ecr.<region>.amazonaws.com/weather-repo
docker push <account_id>.dkr.ecr.<region>.amazonaws.com/weather-repo

# 3. Deploy infrastructure
cd terraform
terraform init
terraform apply
```

---

## ✅ Validation Checklist

- [x] App accessible via ALB DNS
- [x] /health endpoint passes ALB checks
- [x] ECS tasks are running in private subnet
- [x] Docker image pushed to ECR
- [x] Logs available in CloudWatch
- [x] Secure VPC and subnet architecture in place

---

## 📚 Full Breakdown

The full write-up including errors, troubleshooting, and design decisions is available in:  
📄 `docs/Weather App Project Breakdown.pdf`

---

## 💡 Lessons Learned

- Deepened understanding of container orchestration using ECS Fargate
- Implemented real-time API integration from OpenWeatherMap
- Solidified Terraform skills for AWS infrastructure
- Gained experience debugging container apps across local and cloud

---

## 🔭 Future Improvements

- Add HTTPS with ACM & ALB Listener
- Set up CI/CD pipeline with GitHub Actions or CodePipeline
- Add CloudWatch alarms for ECS and API failures
- Use Route 53 with a custom domain

---

## 👨‍💻 Author

**Harvey Aland**  
AWS Certified Solutions Architect – Associate  
[GitHub](https://github.com/HarveyAland) • [LinkedIn](https://www.linkedin.com/in/harvey-aland-172542295)
