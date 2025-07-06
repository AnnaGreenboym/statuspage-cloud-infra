# StatusPage Cloud Infrastructure

This repository showcases the end-to-end deployment of a cloud-native Status Page application using AWS and Kubernetes.  
The project was developed as a practical learning experience to explore DevOps tools, CI/CD pipelines, observability, and cloud infrastructure.

---

## Architecture Overview

Key components of the deployed infrastructure:

- **Cloud Provider**: AWS
- **Kubernetes Platform**: Amazon EKS (multi-AZ, high availability)
- **App Stack**: Python-based Status Page, Redis, PostgreSQL
- **Containerization**: Docker, pushed to Amazon ECR
- **Ingress & Routing**: NGINX Ingress Controller, TLS via ACM, Route 53 domain
- **Storage**: Amazon RDS (PostgreSQL), EFS for shared static content
- **CI/CD**: GitHub Actions for CI, Argo CD for GitOps-based CD
- **Monitoring**: Prometheus + Grafana
- **Security**: TLS, WAF, network segmentation, RBAC, encrypted data flows

---

## CI/CD Workflow

**GitHub Actions** handles the continuous integration pipeline:
- Docker build and test
- Vulnerability scan (Snyk)
- Push to Amazon ECR

**Argo CD** handles continuous deployment:
- Watches GitHub for manifest changes
- Deploys updates to EKS cluster
- Manages access using Kubernetes-native permissions
- Offers audit trail and real-time sync status

---

## Monitoring & Observability

- Metrics collection via **Prometheus**
- Visualization through **Grafana**
- Includes dashboards for system health, pod status, and performance trends

---

## Security Features

- HTTPS enforcement via TLS
- Application-level rate limiting (100 requests/2 min via WAF)
- RBAC and namespace-level isolation in Kubernetes
- Encryption for data in transit and at rest

---

## Estimated AWS Monthly Cost

Total estimate: **$206.49/month**

> Breakdown includes EKS, RDS, NAT Gateway, and other supporting services.

---

## Project Purpose

This project is meant for educational use — specifically to get hands-on experience with real-world DevOps practices, infrastructure as code, and cloud-native deployment patterns.

---

