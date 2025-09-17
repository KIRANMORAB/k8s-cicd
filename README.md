
---

# 📦 App Repo (CI/CD for Application)

This repo handles **building, testing, scanning, containerizing, and deploying the app** on the infra (EKS) created by the other repo.

```markdown
# 🚀 Vprofile Application CI/CD

This repository contains the CI/CD pipeline for building, testing, and deploying the Vprofile application on AWS EKS.

---

## 🏗️ Architecture

![Architecture](docs/architecture.png)

---

## 🔹 CI/CD Workflow: `vprofile actions`
### Jobs:
1. **Testing**
   - Run `mvn test`
   - Checkstyle
   - SonarQube Scan & Quality Gate
2. **Build & Publish**
   - Build Docker image
   - Push to AWS ECR (`vprofileapp`)
3. **Deploy to EKS**
   - Update kubeconfig
   - Create ECR pull secret
   - Deploy via Helm (`vprofilecharts`)
4. **Slack Notification**
   - Always runs (success/failure)

---

## 🛠️ Tools Used
- **Java + Maven** (unit tests & build)
- **SonarQube** (code quality/security)
- **Docker + AWS ECR** (image repository)
- **Helm + EKS** (deployment)
- **Slack** (notifications)

---

## 🔑 GitHub Secrets
- `AWS_ACCESS_KEY_ID`
- `AWS_SECRET_ACCESS_KEY`
- `REGISTRY`
- `SONAR_URL`
- `SONAR_TOKEN`
- `SONAR_ORGANIZATION`
- `SONAR_PROJECT_KEY`
- `SLACK_WEBHOOK_URL`

---


