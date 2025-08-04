# Node.js Demo App — Automated CI/CD Pipeline

## Overview

This project demonstrates a complete CI/CD pipeline for a Node.js application using GitHub Actions and Docker. The pipeline is configured to automate building, testing, and containerizing the application, and to push Docker images to DockerHub on every code commit.

---

## Features

- **Automated Build and Test:**  
  Runs `npm install` and unit tests on every push to the `master` branch.
- **Docker Build & Push:**  
  Builds a Docker image and pushes it to DockerHub using GitHub Actions.
- **Secure Secrets Management:**  
  Uses encrypted GitHub repository secrets for DockerHub credentials.

---

## Tech Stack / Tools

- Node.js 18.19.1
- GitHub Actions
- Docker & DockerHub

---

## Getting Started

### 1. Clone the Repository

- git clone https://github.com/<your-username>/nodejs-demo-app.git
- cd nodejs-demo-app


### 2. Install Dependencies

- npm install


### 3. Run Locally

- node app.js
- Visit http://localhost:3000


---

## CI/CD Pipeline Setup

### GitHub Actions Workflow

The workflow is defined in `.github/workflows/main.yml`:

- On push to `master`, the job will:
    1. Install dependencies and run tests.
    2. Build a Docker image named `<dockerhub-username>/nodejs-demo-app:latest`.
    3. Push the image to DockerHub with authentication via encrypted secrets.

### Required Repository Secrets

- `DOCKERHUB_USERNAME`: Your DockerHub username.
- `DOCKERHUB_TOKEN`: Your DockerHub personal access token with **Read, Write** (and optionally Delete) permissions.

> **How to set secrets:**  
> GitHub Repo → Settings → Secrets and variables → Actions → New repository secret

---

## How It Works

1. **Code Push:** Developer pushes code to `master`.
2. **CI Build/Test:** GitHub Actions runs install & tests in a clean environment.
3. **Docker Build/Push:** On success, builds and pushes a Docker image to DockerHub.
4. **Release Ready!**: Latest image is available on DockerHub for deployment.

---

## Author

S Nagaveena




