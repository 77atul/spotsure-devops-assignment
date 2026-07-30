# 🚀 Spotsure Biz - DevOps Assignment

> End-to-End Deployment of a Dockerized FastAPI Chat Application on AWS EC2 with GitHub Actions CI/CD

![AWS](https://img.shields.io/badge/AWS-EC2-orange)
![Docker](https://img.shields.io/badge/Docker-Compose-blue)
![GitHub Actions](https://img.shields.io/badge/CI/CD-GitHub_Actions-green)
![Nginx](https://img.shields.io/badge/Nginx-Reverse_Proxy-success)
![Python](https://img.shields.io/badge/Python-3.11-blue)
![FastAPI](https://img.shields.io/badge/FastAPI-WebSocket-009688)

---

# 📖 Project Overview

This project was completed as part of the **Spotsure Biz DevOps Assignment**.

The objective was to identify and fix issues in a deliberately broken Dockerized FastAPI chat application, deploy it on an AWS EC2 instance, and automate deployments using GitHub Actions.

The application consists of:

- FastAPI Backend
- Nginx Reverse Proxy
- Static Frontend
- Docker Compose
- GitHub Actions CI/CD
- AWS EC2 Deployment

---

# 🏗 Architecture
<img width="1536" height="1024" alt="spotsure architecture" src="https://github.com/user-attachments/assets/481d31ff-912a-4484-a539-8984b3ade47b" />


---

# ⚙ Tech Stack

| Category | Technologies |
|----------|--------------|
| Cloud | AWS EC2 |
| CI/CD | GitHub Actions |
| Reverse Proxy | Nginx |
| Backend | FastAPI |
| Frontend | HTML, JavaScript |
| Containerization | Docker |
| Orchestration | Docker Compose |
| Version Control | Git & GitHub |
| Operating System | Ubuntu 24.04 |

---

# 📂 Project Structure

```text
.
├── app/
│   ├── main.py
│   └── requirements.txt
│
├── frontend/
│   └── index.html
│
├── Dockerfile
├── docker-compose.yml
├── nginx.conf
├── README.md
└── .github
    └── workflows
        └── deploy.yml
```

---

# 🔍 Issues Identified

During debugging, the following issues were identified:

| Issue | Root Cause | Solution |
|--------|------------|----------|
| Backend listening on localhost | Containers could not communicate | Changed host to `0.0.0.0` |
| Frontend not served | Volume mount missing | Mounted frontend directory into Nginx |
| Incorrect Nginx proxy | Used `localhost` instead of Docker service | Updated proxy to `backend:8000` |
| WebSocket connection failed | Missing Upgrade headers | Enabled required WebSocket headers |
| CI/CD deployment blocked | SSH restricted to local IP | Updated EC2 Security Group for GitHub Actions |

---

# 🔧 Fixes Implemented

## Docker

- Updated Dockerfile
- Improved container networking
- Rebuilt application image

## Docker Compose

- Fixed frontend volume mapping
- Verified inter-container communication

## Nginx

Configured reverse proxy for FastAPI.

Enabled WebSocket support.

Served static frontend.

## FastAPI

Backend now listens on:

```text
0.0.0.0:8000
```

---

# 🚀 Deployment

The application is deployed on:

- AWS EC2 (Ubuntu 24.04)
- Docker Compose
- Nginx Reverse Proxy

Deployment is fully automated using GitHub Actions.

GitHub Repository:
https://github.com/77atul/spotsure-devops-assignment

Live Application:
http://15.252.70.83

---

# 🔄 CI/CD Pipeline

Every push to the `main` branch automatically:

1. Starts GitHub Actions
2. Connects to EC2 via SSH
3. Pulls the latest code
4. Stops existing containers
5. Rebuilds Docker images
6. Starts updated containers
7. Removes unused Docker images

---

# ▶ Running Locally

Clone the repository

```bash
git clone https://github.com/77atul/spotsure-devops-assignment.git

cd spotsure-devops-assignment
```

Start the application

```bash
docker compose up --build
```

Open:

```
http://localhost
```

---

# 📸 Screenshots

- AWS EC2 Console
- <img width="1913" height="904" alt="Screenshot 2026-07-29 230451" src="https://github.com/user-attachments/assets/6d35def8-fb46-4f1b-b9e7-005ec1741306" />

- Running Containers
- <img width="1918" height="859" alt="Screenshot 2026-07-29 231104" src="https://github.com/user-attachments/assets/2a0127d2-aacd-4d8a-9e38-54222a283d07" />

- GitHub Actions Success
- <img width="1916" height="914" alt="Screenshot 2026-07-29 230836" src="https://github.com/user-attachments/assets/e80d4fba-68bc-4300-ae70-2d8805e34d48" />

- Application running via Public IP
- <img width="1912" height="981" alt="Screenshot 2026-07-29 230724" src="https://github.com/user-attachments/assets/0822a636-adce-4d68-b808-ca7d9c6e282c" />


---

# 📚 Learning Outcomes

This project provided hands-on experience with:

- Docker
- Docker Compose
- Nginx
- FastAPI
- WebSockets
- GitHub Actions
- AWS EC2
- Linux
- Reverse Proxy
- SSH Authentication
- CI/CD Pipelines
- Production Deployment

---

# 👨‍💻 Author

**Atul Yadav**

GitHub: https://github.com/77atul

LinkedIn:
https://www.linkedin.com/in/77atul-yadav

---

# ⭐ Acknowledgement

This project was completed as part of the **Spotsure Biz DevOps Assignment** to demonstrate practical DevOps skills including debugging, containerization, cloud deployment, and continuous deployment.
