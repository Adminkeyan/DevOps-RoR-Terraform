_******# DevOps Interview Project – Ruby on Rails App on AWS**_

This project deploys a Ruby on Rails application using AWS services and Terraform. It follows best practices for infrastructure-as-code and secure secrets management.
---
## 🚀 Architecture

- **ECS Fargate** – to run the Dockerized Rails app
- **Application Load Balancer (ALB)** – routes traffic to ECS
- **RDS PostgreSQL** – backend database
- **S3** – for file storage via ActiveStorage
- **Terraform** – used to provision all infrastructure

---

![Architecture](https://github.com/Adminkeyan/DevOps-RoR-Terraform/blob/main/architecture.drawio.png)


- ## ✅ Features

- Auto-scalable ECS Fargate service
- Environment variables securely passed to container
- Load-balanced and health-checked application
- S3 and RDS integrated via ENV

---

## 📁 Project Structure

```
├── alb.tf
├── dev.tfvars        # 🚫 DO NOT COMMIT (contains secrets)
├── ecs.tf
├── iam.tf
├── main.tf
├── outputs.tf
├── rds.tf
├── s3.tf
├── security_groups.tf
├── variables.tf
├── .gitignore
└── README.md

---

## ⚙️ How to Use

1. Fill in your `dev.tfvars` file:
```hcl
access_key_id     = "AKIA..."
secret_access_key = "..."
db_username       = "sampleuser"
db_password       = "SamplePssw0rd123"
```

2. Deploy infrastructure:
```bash
terraform init
terraform apply -var-file="dev.tfvars"
```

3. Access the app using ALB DNS shown in Terraform output.

---

## 🔐 Security Notes

- Credentials are passed using `.tfvars` (never hardcoded)
- `.gitignore` ensures secrets are not committed
- Use IAM roles for production-grade security

---

- ## 🙏 Credits

Submitted by **Karthi Keyan** as part of the DevOps Engineer evaluation task.****
