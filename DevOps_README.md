# 🚀 End-to-End DevOps CI/CD Pipeline (Jenkins + Docker + Nexus + SonarQube + Kubernetes)

## 📌 Project Description

This project demonstrates a **complete DevOps CI/CD pipeline** that
automates build, testing, security scanning, artifact management,
containerization, and Kubernetes deployment using Jenkins.

------------------------------------------------------------------------

## 🔄 CI/CD Pipeline Flow (Your Project)

1.  Code pushed to GitHub
2.  Jenkins Pipeline triggers automatically
3.  Maven builds & runs tests
4.  Trivy scans project files for vulnerabilities
5.  SonarQube performs code quality analysis
6.  Quality Gate validation
7.  Artifact packaged & uploaded to Nexus
8.  Docker image is built
9.  Trivy scans Docker image
10. Docker image pushed to DockerHub
11. Application deployed to Kubernetes
12. Deployment verification (pods & services)
13. Email notification sent with report

------------------------------------------------------------------------

## 🧰 Tech Stack Used

-   Jenkins (CI/CD)
-   Maven (Build Tool)
-   SonarQube (Code Quality)
-   Nexus (Artifact Repository)
-   Docker (Containerization)
-   Trivy (Security Scanning)
-   Kubernetes (Deployment)
-   GitHub (Source Code)

------------------------------------------------------------------------

## 🔐 Jenkins Credentials Configuration

### 1. DockerHub

-   ID: docker1027
-   Type: Username & Password
-   Password = Docker Access Token

### 2. Nexus (via settings.xml)

-   ID: maven-settings
-   Contains server credentials

### 3. Kubernetes

-   ID: k8s
-   Kubeconfig file

------------------------------------------------------------------------

## ⚙️ Pipeline Stages Explained

### 🔹 Git Checkout

``` bash
git clone <repo>
```

### 🔹 Compile

``` bash
mvn compile
```

### 🔹 Test

``` bash
mvn test
```

### 🔹 File System Security Scan

``` bash
trivy fs .
```

### 🔹 SonarQube Analysis

``` bash
sonar-scanner
```

### 🔹 Quality Gate

-   Stops pipeline if code quality fails

### 🔹 Build Package

``` bash
mvn package
```

### 🔹 Publish to Nexus

``` bash
mvn deploy
```

### 🔹 Build Docker Image

``` bash
docker build -t prajwal1027/database-app:latest .
```

### 🔹 Scan Docker Image

``` bash
trivy image prajwal1027/database-app:latest
```

### 🔹 Login to DockerHub

``` bash
echo $PASS | docker login -u $USER --password-stdin
```

### 🔹 Push Docker Image

``` bash
docker push prajwal1027/database-app:latest
```

### 🔹 Deploy to Kubernetes

``` bash
kubectl apply -f deployment-service.yml -n appr
```

### 🔹 Verify Deployment

``` bash
kubectl get pods -n appr
kubectl get svc -n appr
```

------------------------------------------------------------------------

## 📂 Project Structure

    .
    ├── Jenkinsfile
    ├── pom.xml
    ├── deployment-service.yml
    ├── src/
    ├── target/

------------------------------------------------------------------------

## 📊 Outputs

-   ✅ Nexus Artifact Stored
-   ✅ Docker Image Pushed
-   ✅ Kubernetes Deployment Running
-   ✅ Trivy Security Reports Generated

------------------------------------------------------------------------

## 📧 Email Notification

-   Triggered on Success & Failure
-   Includes:
    -   Build status
    -   Trivy report
    -   Jenkins link

------------------------------------------------------------------------

## 🚀 How to Run

### Step 1: Clone Repo

``` bash
git clone https://github.com/PrajwalDataScientist/Devops_project_k8s.git
```

### Step 2: Build Locally

``` bash
mvn clean install
```

### Step 3: Build Docker Image

``` bash
docker build -t test-app .
```

### Step 4: Run Container

``` bash
docker run -p 8080:8080 test-app
```

------------------------------------------------------------------------

## 🎯 Key Highlights

-   Full CI/CD automation
-   Integrated security scanning
-   Code quality enforcement
-   Artifact versioning with Nexus
-   Containerized deployment
-   Kubernetes orchestration

------------------------------------------------------------------------

## 👨‍💻 Author

Prajwal B
