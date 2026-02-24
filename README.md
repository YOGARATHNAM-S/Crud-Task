# MEAN Stack CRUD Application

A full-stack **Tutorial Management** app built with MongoDB, Express, Angular 15, and Node.js — containerized with Docker and deployed on AWS EC2 with CI/CD.

---

## Demo

![Demo](public/Completion.gif)

---

## Architecture

![Architecture](public/architecture.png)

---

## Tech Stack

| Layer      | Technology             |
|------------|------------------------|
| Frontend   | Angular 15             |
| Backend    | Node.js + Express      |
| Database   | MongoDB                |
| Proxy      | Nginx (reverse proxy)  |
| Container  | Docker + Docker Compose|
| CI/CD      | GitHub Actions         |
| Hosting    | AWS EC2 (Ubuntu)       |

---

## Features

- Create, Read, Update, Delete tutorials
- Search tutorials by title
- Toggle published status
- Fully containerized deployment
- Automated CI/CD pipeline

---

## Folder Structure

```
├── .github/workflows/deploy.yml   # CI/CD pipeline
├── backend/
│   ├── Dockerfile
│   ├── server.js                  # Express entry point
│   └── app/                       # Config, controllers, models, routes
├── frontend/
│   ├── Dockerfile                 # Multi-stage (Angular build + Nginx)
│   ├── nginx.conf                 # Reverse proxy config
│   └── src/app/                   # Components, models, services
├── docker-compose.yml             # Orchestrates all services
└── public/                        # Architecture diagram & demo GIF
```

---

## Getting Started

### Prerequisites

- Docker & Docker Compose
- Git

### Run Locally

```bash
git clone https://github.com/<your-username>/crud-task.git
cd crud-task
docker compose up -d
```

Open **http://localhost** in a browser.

---

## Deployment

The app is deployed on an **AWS EC2 Ubuntu** instance. GitHub Actions automatically builds Docker images, pushes them to Docker Hub, and deploys via SSH on every push to `main`.

### CI/CD Pipeline

```
git push → Build Images → Push to Docker Hub → SSH Deploy to EC2
```

### Required GitHub Secrets

| Secret            | Description               |
|-------------------|---------------------------|
| `DOCKERHUB_TOKEN` | Docker Hub access token   |
| `DEPLOY_HOST`     | EC2 public IP             |
| `DEPLOY_USER`     | SSH user (e.g. `ubuntu`)  |
| `DEPLOY_SSH_KEY`  | Private SSH key (.pem)    |

---

## Docker Images

- `yoga2002/backend:latest`
- `yoga2002/frontend:latest`

---

## License

This project is for educational/demonstration purposes.
