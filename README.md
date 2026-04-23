# Secure CI/CD Pipeline to AWS ECS (DevSecOps)

## Overview

This project demonstrates a **secure, automated CI/CD pipeline** that builds, scans, and deploys a containerized application to AWS ECS using GitHub Actions.

It simulates a real-world DevSecOps workflow where code is automatically built, pushed to a registry, and deployed to a live cloud environment.

---

## Key Features

* Dockerized Python (Flask) application
* CI/CD pipeline using GitHub Actions
* Image push to AWS ECR
* Deployment to AWS ECS (Fargate)
* Automatic service updates on push
* IAM least privilege security model
* Secure credential handling via GitHub Secrets

---

## Architecture

GitHub → CI Pipeline → Docker Build → ECR → ECS → Live Application

---

## CI/CD Workflow

1. Code is pushed to GitHub
2. GitHub Actions pipeline is triggered
3. Docker image is built
4. Image is pushed to AWS ECR
5. ECS service is updated
6. New container version is deployed automatically

---

## Security Implementation

* No hardcoded credentials
* AWS keys stored securely in GitHub Secrets
* IAM user configured with **least privilege access**
* No root user usage
* Public access limited to required application port

---

## Deployment

The application is deployed on **AWS ECS Fargate** and is accessible via a public IP.

---

## Run Locally

```bash
docker build -t test-app .
docker run -p 5000:5000 test-app
```

Visit:
http://localhost:5000

---

## Project Structure

```
.
├── app/
│   └── app.py
├── Dockerfile
├── requirements.txt
├── .github/workflows/
│   └── pipeline.yml
├── .gitignore
└── README.md
```

---

## Skills Demonstrated

* DevOps: Docker, CI/CD pipelines, AWS ECS
* DevSecOps: IAM, secure pipelines, secrets management
* Cloud: ECR, ECS Fargate deployment
* Automation: GitHub Actions

---

## Future Improvements

* Replace access keys with OIDC authentication
* Add Application Load Balancer (ALB)
* Enable HTTPS (TLS)
* Multi-environment setup (dev/staging/prod)

---

## Summary

This project demonstrates the ability to design and implement a **secure CI/CD pipeline for cloud-native applications**, following modern DevOps and DevSecOps best practices.
