### Deployment Instructions

### 1. Clone repo
git clone https://github.com/your-username/flask-cicd-app

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
http://<EC2_PUBLIC_IP>
