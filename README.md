### Deployment Instructions

### 1. Clone repo
git clone https://github.com/ebikakpou/flask-cicd-app

### 2. Setup Terraform
cd terraform
terraform init
terraform apply

### 3. Configure GitHub Secrets
- DOCKER_USERNAME
- DOCKER_PASSWORD
- EC2_HOST
- EC2_SSH_KEY

### 4. Push code to trigger CI/CD
git push origin main

### 5. Access app
http://54.242.35.197/8080
