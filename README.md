# 🚀 Jenkins CI/CD Pipeline with Docker

✨ **Automate Code Build, Testing, and Deployment using Jenkins, Docker, and GitHub!**

## 📌 Project Overview

This project demonstrates a simple **Continuous Integration and Continuous Deployment (CI/CD) pipeline** using Jenkins and Docker. The pipeline automatically builds a Docker image, performs basic application checks, and deploys a web application inside a Docker container.

🎯 **Project Goal:** Automate the application deployment process and understand the practical implementation of DevOps CI/CD.

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| 🐧 Ubuntu on WSL | Linux development environment |
| 🔧 Git | Version control |
| 🐙 GitHub | Source code repository |
| 🤵 Jenkins | CI/CD pipeline automation |
| 🐳 Docker | Containerization |
| 🌐 Nginx | Web server |
| 💻 HTML & CSS | Frontend application |

## 🏗️ Project Architecture

```text
👩‍💻 Developer
      |
      v
🐙 GitHub Repository
      |
      v
🤵 Jenkins Pipeline
      |
      +-------------------+
      |        |          |
      v        v          v
   🏗️ Build  🧪 Test   🚀 Deploy
      |        |          |
      +--------+----------+
               |
               v
       🐳 Docker Container
               |
               v
     🌐 Nginx Web Application
        http://localhost:8081
```

## ⚙️ CI/CD Pipeline Stages

### 1️⃣ Build 🏗️
- Jenkins retrieves the project files from GitHub.
- Docker builds an image using the `Dockerfile`.
- The image is tagged as `jenkins-demo:latest`.

### 2️⃣ Test 🧪
- Checks that `index.html` exists.
- Verifies that the expected success message is present.
- Confirms that the Docker image was created successfully.

### 3️⃣ Deploy 🚀
- Removes the previous application container, if present.
- Starts a new container named `jenkins-demo-app`.
- Maps host port `8081` to container port `80`.

## 📂 Project Structure

```text
jenkins-docker-cicd-elevate-labs/
│
├── 📄 Jenkinsfile
├── 🐳 Dockerfile
└── 🌐 index.html
```

| File | Description |
|---|---|
| `Jenkinsfile` | Defines the automated Build, Test, and Deploy stages |
| `Dockerfile` | Defines how the Docker image is built |
| `index.html` | Contains the web application's HTML and CSS |

## ▶️ How to Run the Project

### Step 1: Clone the repository

```bash
git clone https://github.com/ruchi1792/jenkins-docker-cicd-elevate-labs.git
cd jenkins-docker-cicd-elevate-labs
```

### Step 2: Build the Docker image

```bash
docker build -t jenkins-demo:latest .
```

### Step 3: Run the application

```bash
docker run -d \
  --name jenkins-demo-app \
  -p 8081:80 \
  jenkins-demo:latest
```

### Step 4: Open the application

🌐 **Application URL:** http://localhost:8081

### Step 5: Verify the container

```bash
docker ps
```

## 📸 Project Verification

The pipeline was executed successfully in Jenkins.

- ✅ GitHub repository checkout completed.
- ✅ Docker image built successfully.
- ✅ Basic application checks passed.
- ✅ Docker container deployed successfully.
- ✅ Jenkins build result: `SUCCESS`.

## 🎓 Key Learnings

- 🔹 Understanding CI/CD concepts and pipeline automation.
- 🔹 Creating declarative Jenkins pipelines using a `Jenkinsfile`.
- 🔹 Building and running Docker images and containers.
- 🔹 Integrating GitHub with Jenkins.
- 🔹 Deploying a web application using Nginx.
- 🔹 Verifying pipeline execution through Jenkins Console Output.

## 🔮 Future Improvements

- 🔔 Configure GitHub webhooks for faster automatic builds.
- 🧪 Add automated application and integration tests.
- 📦 Publish Docker images to Docker Hub.
- 🔐 Store credentials securely using Jenkins Credentials.
- ☁️ Deploy the application to a cloud platform.

## 👩‍💻 Author

**Ruchita Deshmukh**

🔗 GitHub Repository: [jenkins-docker-cicd-elevate-labs](https://github.com/ruchi1792/jenkins-docker-cicd-elevate-labs)

---

⭐ If you find this project useful, consider giving the repository a star!

💡 *This project was created for learning and practicing DevOps CI/CD pipeline automation.*
