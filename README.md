# 🚀 Spring Boot DevOps Demo #

An end-to-end DevOps project demonstrating the complete CI/CD lifecycle of a Spring Boot application using Git, GitHub, Jenkins, Docker, Docker Hub, Kubernetes, and AWS concepts.

This project was built to gain hands-on experience with DevOps tools and practices used in production environments.


# 📌 Project Overview #

The project automates the complete software delivery pipeline:

- Develop a Spring Boot REST API
- Store source code in GitHub
- Build the application using Maven
- Create a Docker image
- Push the image to Docker Hub
- Deploy the application to Kubernetes
- Perform rolling updates and rollbacks
- Configure readiness and liveness probes
- Demonstrate Kubernetes self-healing

---

# 🏗 Architecture #



Developer
│
▼
Git
│
▼
GitHub Repository
│
▼
Jenkins Pipeline
│
├── Checkout Source Code
├── Maven Build
├── Unit Tests
├── Docker Image Build
├── Push Image to Docker Hub
└── Kubernetes Deployment
│
▼
Kubernetes Cluster
│
▼
Spring Boot Application


🛠  # Tech Stack #


| Category | Details |
| --- | --- |
| **[Language](ca://s?q=Explain_Java_17)** | Java 17 |
| **[Framework](ca://s?q=Explain_Spring_Boot)** | Spring Boot |
| **[Build Tool](ca://s?q=Explain_Maven)** | Maven |
| **[Version Control](ca://s?q=Explain_Git)** | Git |
| **[Repository](ca://s?q=Explain_GitHub)** | GitHub |
| **[CI/CD](ca://s?q=Explain_Jenkins)** | Jenkins |
| **[Containerization](ca://s?q=Explain_Docker)** | Docker |
| **[Image Registry](ca://s?q=Explain_Docker_Hub)** | Docker Hub |
| **[Orchestration](ca://s?q=Explain_Kubernetes_Kind)** | Kubernetes (Kind) |
| **[Operating System](ca://s?q=Explain_Windows_vs_Linux)** | Windows / Linux |
| **[IDE](ca://s?q=Explain_VS_Code)** | Visual Studio Code |


📂 Project Structure #


springboot-devops-demo/
│
├── src/
├── target/
├── Dockerfile
├── Jenkinsfile
├── pom.xml
├── k8s/
│ ├── deployment.yaml
│ └── service.yaml
└── README.md

⚙ CI/CD Pipeline #

Code Push → Developer commits and pushes code to GitHub.

Jenkins Build → Jenkins checks out the latest code.

Maven Compile → Maven compiles and packages the application.

Docker Image → Docker builds a container image.

Docker Hub → The image is pushed to Docker Hub.

Kubernetes Deploy → Kubernetes (Kind) deploys the latest container.

Health Probes → Readiness and liveness probes monitor application health.

Rolling Updates → Rolling updates ensure zero/minimal downtime.


🚀 Features #

 
Spring Boot REST API
Maven Build Automation
Jenkins Declarative Pipeline
Docker Image Creation
Docker Hub Integration
Kubernetes Deployment
Rolling Updates
Rollback Support
Self-Healing Pods
Readiness Probe
Liveness Probe
Resource Requests and Limits.



🛠  # Prerequisites / Tools #


Tool	Version / Notes
Java	17+
Maven	Latest
Git	Any modern version
Docker Desktop	Required
Kubernetes	Kind / Minikube
kubectl	CLI tool
Jenkins	CI/CD
<h2 align="center">🏗️ End-to-End DevOps Architecture</h2>

<p align="center">
  <img src="images/architecture.png" width="1000">
</p>









