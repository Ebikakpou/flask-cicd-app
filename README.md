# Flask CI/CD Pipeline with GitHub Actions, Docker & AWS

## Overview
This project demonstrates a complete CI/CD pipeline for a Flask application using:

- Docker (containerization)
- GitHub Actions (CI/CD)
- AWS EC2 (deployment)
- Terraform (infrastructure provisioning)

---

## How It Works

1. Developer pushes code to GitHub
2. GitHub Actions:
   - Builds Docker image
   - Pushes image to Docker Hub
   - Connects to EC2 via SSH
   - Pulls latest image
   - Restarts container
3. Application is updated automatically

---

## Setup Instructions

### 1. Clone the repo
```bash
git clone https://github.com/Ebikakpou/flask-cicd-app.git
cd flask-cicd-app
