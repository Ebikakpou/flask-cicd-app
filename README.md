# 🚀 Flask CI/CD Pipeline with GitHub Actions, Docker & Terraform (AWS)

## 📌 Project Overview

This project demonstrates a complete CI/CD pipeline for a Python Flask application using:

* GitHub Actions (CI/CD)
* Docker (Containerization)
* Terraform (Infrastructure as Code)
* AWS EC2 (Deployment)

The pipeline automatically:

* Builds the application
* Runs tests
* Builds & pushes Docker image
* Deploys to AWS EC2

---

## 🏗️ Architecture

Developer → GitHub → GitHub Actions → DockerHub → AWS EC2 (Docker Container)

---

## 📁 Project Structure

```
flask-cicd-app/
│
├── app/
│   ├── app.py
│   ├── requirements.txt
│   └── test_app.py
│
├── Dockerfile
├── docker-compose.yml
│
├── .github/
│   └── workflows/
│       └── ci-cd.yml
│
├── terraform/
│   ├── main.tf
│   ├── variables.tf
│   ├── outputs.tf
│
└── README.md
```

---

## ⚙️ Prerequisites

Before you begin, ensure you have:

* AWS Account
* DockerHub Account
* Terraform Installed
* Git Installed
* SSH Key Pair (for EC2)

---

## ☁️ Step 1: Provision Infrastructure (Terraform)

Navigate to terraform folder:

```
cd terraform
```

Initialize Terraform:

```
terraform init
```

Apply configuration:

```
terraform apply
```

Type `yes` when prompted.

After completion, copy the **EC2 Public IP** from output.

---

## 🔐 Step 2: Configure GitHub Secrets

Go to your GitHub repository:

Settings → Secrets → Actions

Add the following secrets:

```
DOCKER_USERNAME=your_dockerhub_username
DOCKER_PASSWORD=your_dockerhub_password
EC2_HOST=your_ec2_public_ip
EC2_SSH_KEY=your_private_key
```

---

## 🐳 Step 3: Docker Setup (Optional Local Test)

Build and run locally:

```
docker build -t flask-app .
docker run -p 5000:5000 flask-app
```

Visit:

```
http://localhost:5000
```

---

## 🔁 Step 4: Trigger CI/CD Pipeline

Push code to main branch:

```
git add .
git commit -m "Trigger pipeline"
git push origin main
```

This will trigger GitHub Actions pipeline.

---

## ⚙️ CI/CD Pipeline Stages

### 1. Build & Test

* Install dependencies
* Run pytest

### 2. Docker Build & Push

* Build Docker image
* Push to DockerHub

### 3. Deployment

* SSH into EC2
* Pull latest Docker image
* Run container on port 80

---

## 🌍 Step 5: Access Application

Open browser:

```
http://<EC2_PUBLIC_IP>
```

---

## 🧪 Test Endpoint

```
/health
```

---

## 🛠️ Troubleshooting

* Ensure port 80 is open in AWS Security Group
* Verify Docker is installed on EC2
* Check GitHub Actions logs for errors

---

## 📦 Future Improvements

* Add AWS RDS (PostgreSQL)
* Use Nginx reverse proxy
* Enable HTTPS (SSL)
* Add monitoring (Prometheus/Grafana)
* Implement Blue-Green Deployment

---

## 👨‍💻 Author

Samuel Ebika Kpou
DevOps Engineer

---

## ⭐ Conclusion

This project showcases an end-to-end CI/CD pipeline using modern DevOps tools and best practices.
