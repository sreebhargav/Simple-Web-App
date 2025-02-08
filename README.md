# 🚀 Simple Web App - Patient EMR System

This project is a **Simple Web Application** (Patient EMR System) built with a **PostgreSQL** backend and deployed on **Amazon Web Services (AWS)** using **Elastic Beanstalk** and **RDS**. The infrastructure is designed to be **highly available**, **scalable**, and **secure**.

[![Live Demo](http://img.shields.io/badge/Live-Demo-blue)](https://simple-web-app1.us-east-1.elasticbeanstalk.com/patients/)

---

## 📄 Table of Contents
- [📚 Introduction](#-introduction)
- [📊 Infrastructure Overview](#-infrastructure-overview)
- [🚀 AWS Resource Configuration](#-aws-resource-configuration)
  - [🌐 Virtual Private Cloud (VPC)](#-virtual-private-cloud-vpc)
  - [🔒 Security Groups](#-security-groups)
  - [🚀 Elastic Beanstalk Configuration](#-elastic-beanstalk-configuration)
  - [📂 Amazon RDS (PostgreSQL)](#-amazon-rds-postgresql)
  - [🔍 Logging and Monitoring](#-logging-and-monitoring)
  - [📑 CloudFormation](#-cloudformation)
- [🚀 Future Considerations](#-future-considerations)
- [📅 Appendix](#-appendix)
- [📚 Getting Started](#-getting-started)
- [🌐 License](#-license)

---

## 📚 Introduction
This documentation outlines the step-by-step configuration and deployment process of a **simple Patient EMR (Electronic Medical Record) application** on the **AWS** platform. The application includes:

- **PostgreSQL** database hosted on **Amazon RDS**.
- **Elastic Beanstalk** for deploying the application backend.

The entire infrastructure is designed for **high availability**, **scalability**, and **security**.

---

## 📊 Infrastructure Overview
The architecture follows a **multi-tiered design** leveraging the following AWS services:

- **Amazon VPC**: Custom virtual private cloud with public and private subnets.
- **Elastic Beanstalk**: Managed service for deploying the web application.
- **Amazon RDS (PostgreSQL)**: Managed relational database service.
- **AWS IAM**: Identity and Access Management for security roles.
- **AWS CloudWatch**: Logging and monitoring services.
- **AWS Auto Scaling**: Ensures high availability and scalability.
- **AWS CloudFormation**: Infrastructure as Code for automated deployments.

---

## 🚀 AWS Resource Configuration

### 🌐 Virtual Private Cloud (VPC)
- **Two public subnets** for the web application and Elastic Load Balancer.
- **Two private subnets** for the PostgreSQL database.
- **Internet Gateway** for public access.
- **NAT Gateway** for secure internet access from private subnets.

### 🔒 Security Groups
- **Backend Security Group**: Allows inbound traffic on ports **8000** and **8080** from the load balancer, and outbound traffic to RDS on port **5432**.
- **Database Security Group**: Allows PostgreSQL connections on port **5432** from the backend security group.

### 🚀 Elastic Beanstalk Configuration
- The web application is **dockerized** and deployed to Elastic Beanstalk.
- The environment is provisioned with the necessary **environment variables** for PostgreSQL connection.
- The application is deployed across **two public subnets** for efficient scalability and high availability.

### 📂 Amazon RDS (PostgreSQL)
- **Multi-AZ deployment** ensures high availability.
- Hosted in **private subnets** to prevent direct internet access.
- **Automatic backups and snapshots** enabled for disaster recovery.

### 🔍 Logging and Monitoring
- **AWS CloudWatch** monitors logs and application health.
- **Elastic Beanstalk health monitoring** keeps track of instance health.
- **Amazon SNS** for incident management and event notifications.

### 📑 CloudFormation
- The entire infrastructure setup is managed using **AWS CloudFormation** (Infrastructure as Code).

---

## 🚀 Future Considerations

To further enhance the scalability, security, and maintainability of the application, future improvements could include:

- **AWS Web Application Firewall (WAF)**: Protection against common web attacks.
- **Amazon Aurora**: Optimized database for better scalability and failover.
- **CodePipeline Integration**: For more robust CI/CD automation.
- **Multi-region failover** using **Route 53 DNS failover** for higher availability.

---

## 📅 Appendix

- **Web Application Link**: [Patient EMR System](https://simple-web-app1.us-east-1.elasticbeanstalk.com/patients/)

---

## 📚 Getting Started

### 📅 Prerequisites
- **Docker** for containerization.
- **AWS CLI** configured with proper IAM roles.

### 🔄 Running Locally

1. **Clone the repository:**
```bash
git clone https://github.com/your-username/simple-web-app.git
cd simple-web-app
```

2. **Run the Application:**
```bash
docker build -t simple-web-app .
docker run -p 8000:8000 simple-web-app
```

---

## 🌐 License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.


