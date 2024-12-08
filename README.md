# 🎉 Blog App CI/CD Pipeline on EKS 🚀

## Introduction 📝

Welcome to the **Blog App CI/CD Pipeline on EKS** repository! This project demonstrates an automated and robust CI/CD pipeline for deploying a full-stack blogging application on Kubernetes (EKS). The pipeline includes automation, monitoring, code quality checks, and vulnerability scanning, ensuring smooth deployments from code commit to production. 🔧✨

## Table of Contents 📚

- [Project Overview](#project-overview)
- [Technologies Used](#technologies-used)
- [Pipeline Architecture](#pipeline-architecture)
- [Setup Instructions](#setup-instructions)
- [CI/CD Pipeline](#cicd-pipeline)
- [Monitoring & Alerts](#monitoring--alerts)
- [Contributing](#contributing)
- [License](#license)

## Project Overview 💻

This repository provides the complete infrastructure for a CI/CD pipeline that automates the **building**, **testing**, **deployment**, and **monitoring** of a blogging app. The application is containerized with **Docker** and deployed to **Amazon EKS**. Tools like **SonarQube** and **Nexus** are integrated for code quality checks and artifact management, while **Prometheus** and **Grafana** offer powerful monitoring and visualization features. 📊📈

## Technologies Used 🛠️

- **Jenkins**: Automates continuous integration and deployment pipelines.
- **SonarQube**: Performs static code analysis to ensure security and quality.
- **Docker**: Containerizes the app to ensure consistency across environments.
- **Kubernetes (EKS)**: Manages and orchestrates containerized applications on AWS.
- **Prometheus & Grafana**: Collects and visualizes metrics to monitor application health.
- **Blackbox Exporter**: Monitors the availability of the application.
- **Nexus**: Stores and manages build artifacts.
- **Terraform**: Automates the provisioning of EKS clusters via Infrastructure as Code (IaC).

## Pipeline Architecture 🏗️

The CI/CD pipeline consists of the following stages:

1. **Code Checkout & Build**:
   - Jenkins fetches the latest code from GitHub and triggers the build process.
   - **SonarQube** performs static code analysis to ensure code quality and security.

2. **Docker Image Build & Push**:
   - The app is containerized using **Docker**.
   - Jenkins builds and pushes the Docker image to **DockerHub** and **Nexus** for artifact management.

3. **Deployment**:
   - The application is deployed to **Amazon EKS** using Kubernetes manifests.

4. **Monitoring**:
   - **Prometheus** collects health data and application metrics.
   - **Grafana** visualizes these metrics to provide insights into performance and uptime.

## Setup Instructions ⚙️

### 1. Clone the Repository 🔁

Clone the repository to get started:

```bash
git clone https://github.com/Mariam-Ghamgui/blog-app-CICD-EKS.git
cd blog-app-CICD-EKS
```

## 2. Install Dependencies 🔌

To set up the required tools for the pipeline, run these scripts:

### Jenkins Setup:
```bash
./ci-scripts/install_jenkins.sh 
```

### Docker Setup:
```bash
./ci-scripts/install_docker.sh
```

### Prometheus & Grafana Setup:
```bash
./ci-scripts/install_prometheus.sh
./ci-scripts/install_grafana.sh
```

## 3. Set up Kubernetes (EKS) 🌐

Provision the EKS cluster with Terraform:
```bash
cd terraform
terraform init
terraform apply --auto-approve
```

Once the infrastructure is set, deploy Kubernetes resources:
```bash
kubectl apply -f kubernetes/deployment.yml
kubectl apply -f kubernetes/service.yml
```

4. Access the Application 🖥️

Once deployed, access the application and monitoring tools:
   - **Grafana** http://<your-server-ip>:3000
   - **Prometheus** http://<your-server-ip>:9090

## CI/CD Pipeline 🎯   

1. **GitHub Integration**:
   - Jenkins pulls the latest changes from GitHub and starts 

2. **Build & Code Analysis**:
   - Jenkins compiles the app with Maven, while SonarQube checks the code for quality.

3. **Vulnerability Scanning**:
   - Trivy scans the Docker image for security vulnerabilities.

4. **Docker Image Build & Push**:
   - Jenkins builds and pushes the Docker image to DockerHub and Nexus.

5. **Kubernetes Deployment**:
   - The app is deployed to the EKS cluster using Kubernetes manifests.

6. **Monitoring: Prometheus**:
   - collects metrics, and Grafana visualizes the data for performance insights.  

## Monitoring & Alerts ⚠️ 

   - Prometheus collects metrics from the application and the Blackbox Exporter to monitor uptime and health.
   - Grafana visualizes the metrics, providing real-time performance data.
   - Alerts are configured to notify the team of availability or performance issues.

## Contributing 🤝

We welcome contributions! To contribute, follow these steps:

1. Fork the repository.

2. Clone your fork locally:
```bash
git clone https://github.com/yourusername/blog-app-CICD-EKS.git
```

3. Create a new branch:
```bash
git checkout -b feature-branch
```

4. Make changes and commit them:
```bash
git commit -m "Add new feature or fix"
```

5. Push your changes:
```bash
git push origin feature-branch
```

6. Open a pull request with a detailed description of your changes. 

 