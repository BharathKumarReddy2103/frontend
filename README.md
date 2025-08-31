# Roboshop Frontend Microservice CICD

This repository contains the **frontend microservice** for the [Roboshop Application](https://github.com/BharathKumarReddy2103), a microservices-based e-commerce platform for selling robots. The frontend service provides the user interface and interacts with various backend microservices to deliver a seamless shopping experience.

## Table of Contents

- [Overview](#overview)
- [Architecture](#architecture)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [CI/CD Pipeline](#cicd-pipeline)
- [Deployment](#deployment)
- [Getting Started](#getting-started)
- [Jenkins Shared Library](#jenkins-shared-library)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

Roboshop is a cloud-native, microservices-based e-commerce platform designed for buying and selling robots. This repository specifically contains the frontend microservice, responsible for the web UI and user interactions.

## Architecture

- **Microservices Architecture:** Each service is independently deployable and scalable.
- **Frontend Service:** This repository; interacts with backend APIs (catalog, cart, user, payment, etc.).
- **Deployment:** All services, including frontend, are deployed on AWS EKS (Elastic Kubernetes Service).
- **CI/CD:** Automated build, test, and deployment using Jenkins and Docker.

## Features

- Modern, responsive web UI for Roboshop
- Interacts with backend microservices via REST APIs
- Supports user registration, product browsing, cart management, and checkout
- Containerized for easy deployment and scaling

## Tech Stack

- **Frontend:** Java
- **Containerization:** Docker
- **CI/CD:** Jenkins with [Jenkins Shared Library](https://github.com/BharathKumarReddy2103/jenkins-shared-library)
- **Orchestration:** Kubernetes (AWS EKS)

## CI/CD Pipeline

- **Jenkinsfile:** Automates build, test, and deployment steps.
- **Jenkins Shared Library:** Common pipeline logic and reusable steps.
- **Docker:** Builds and pushes images to the registry.
- **Kubernetes (EKS):** Automated deployment of Docker images.

### How CI/CD Works

1. **Code Commit:** Push changes to this repo.
2. **Jenkins Pipeline:** Triggered via Jenkinsfile.
3. **Build & Test:** Source code is built and tested.
4. **Docker Image:** Image is built and pushed to container registry.
5. **Deploy:** Image is deployed to EKS using Kubernetes manifests.

## Deployment

This frontend service is deployed on AWS EKS as a containerized application. Deployment is automated via the Jenkins pipeline.

### Prerequisites

- Docker
- Kubernetes CLI (`kubectl`)
- AWS CLI & EKS access (for production deployment)
- Jenkins access

### Steps

1. **Clone the repository:**
   ```bash
   git clone https://github.com/BharathKumarReddy2103/frontend.git
   cd frontend
   ```
2. **Build Docker Image:**
   ```bash
   docker build -t roboshop-frontend:latest .
   ```
3. **Push to Registry:**  
   *(Configure your registry details in Jenkins or manually push as needed)*
4. **Deploy to EKS:**  
   Jenkins pipeline automates this, or use your Kubernetes manifests.

## Getting Started (Local Development)

1. **Install dependencies:**  
   *(Instructions for your frontend framework, e.g., `npm install` for Node.js projects)*
2. **Run locally:**  
   ```bash
   npm start  # or relevant start command
   ```
3. **Access the app:**  
   Visit `http://localhost:3000` (or the port used by your app).

## Jenkins Shared Library

This repository uses a [Jenkins Shared Library](https://github.com/BharathKumarReddy2103/jenkins-shared-library) to manage common CI/CD tasks, ensuring consistent and reusable pipeline code across all Roboshop microservices.

## Contributing

We welcome contributions. Please fork the repo and submit a Pull Request.

1. Fork this repository
2. Create your feature branch (`git checkout -b feature/my-feature`)
3. Commit your changes (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature/my-feature`)
5. Open a Pull Request

## License

[MIT License](LICENSE)  
*(Update this section if you use a different license)*

---

**Roboshop Frontend Microservice**  
Maintained by [@BharathKumarReddy2103](https://github.com/BharathKumarReddy2103)
