# DevOps Interview Task – Full Stack App Deployment

## Scenario  
I am deploying a full-stack web application with:
- React (frontend)
- Node.js + Express (backend)
- PostgreSQL (database)

The goal is to containerize the app using Docker, connect the services with docker-compose, and deploy to a cloud platform (AWS EC2 used here).

--------------------------

##  Part A – Docker & Deployment

###  Objective
- Containerize each component of the app
- Connect React, Node.js, and PostgreSQL using 'docker-compose'
- Deploy the setup on a cloud server (AWS EC2 in this case)

-----------------------------

##  Tech Stack

| Layer     | Tech                         |
|-----------|------------------------------|
| Frontend  | React                        |
| Backend   | Node.js + Express            |
| Database  | PostgreSQL                   |
| Orchestration | Docker + Docker Compose |
| Cloud     | AWS EC2 (Ubuntu 22.04)       |


---------------------------

##  Project Structure
devops-fullstack-deployment-challenge/
├── frontend/
│ ├── Dockerfile
│ └── (React app files)
├── backend/
│ ├── Dockerfile
│ ├── index.js
│ ├── package.json
│ └── package-lock.json
├── docker-compose.yml
└── README.md

---

## 🧱 Docker Setup

### 🔹 Frontend Dockerfile
- Located inside `frontend/`
- Uses `node:18-alpine` to build the React app
- Final output is served using `nginx`

### 🔹 Backend Dockerfile
- Located inside `backend/`
- Uses `node:18-alpine` to run Express server
- Exposes port `5000`

### 🔹 docker-compose.yml
- Defines three services: `frontend`, `backend`, `postgres`
- Handles networking and volumes
- Exposes ports:
  - `3000` → Frontend
  - `5000` → Backend
  - `5432` → PostgreSQL (internal)

---

## ⚙️ Deployment Steps

1. Launch an AWS EC2 instance (Ubuntu 22.04)
2. Install Docker and Docker Compose
3. Clone this repository: git clone https://github.com/Yathendraindra/devops-fullstack-deployment-challenge.git
4. Build and run the containers:
sudo docker-compose up --build -d
5. http://<your-ec2-ip>:3000 → React frontend && http://<your-ec2-ip>:5000 → Node backend

## Validation

- ✔️ Frontend running at `http://<EC2-IP>:3000`
- ✔️ Backend API available at `http://<EC2-IP>:5000`
- ✔️ PostgreSQL connected internally via Docker network



   



