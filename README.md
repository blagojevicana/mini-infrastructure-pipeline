# mini-cloud-service

## Overview
This project demonstrates a **containerized Python API deployed on Kubernetes**, with **NGINX load balancing** and automated **CI/CD** using GitHub Actions. It showcases DevOps and backend skills such as Docker, Kubernetes, infrastructure automation and continuous deployment.

## Features
- Python Flask API
- Docker containerization
- Kubernetes deployment
- NGINX reverse proxy & load balancing
- GitHub Actions CI/CD pipeline for automated build & deployment

**NGINX** distributes traffic between multiple Flask app instances running in **Kubernetes pods**.  
The app is **containerized using Docker** and the image is built & pushed automatically via **GitHub Actions**.

## GitHub Actions CI/CD

- Automatically builds and pushes Docker image on every push to `main` branch.
- Uses **Docker Hub secrets** for non-interactive login:
  - `DOCKER_USERNAME`
  - `DOCKER_PASSWORD`
- Workflow path: `.github/workflows/ci-cd.yaml`

> Kubernetes deployment is **run locally**.


## Local Setup & Deployment

### Prerequisites
- Docker
- Minikube or other local Kubernetes
- kubectl
- NGINX

### Steps

1. **Build Docker image:**
```bash
docker build -t mini-cloud-service:latest .
```
2. **Start local Kubernetes (minikube):**
```bash
minikube start
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
```
3. **Start NGINX:**
```bash
sudo nginx -c $(pwd)/nginx/nginx.conf
```
4. **Access the service:**
```bash
http://localhost:8080
```
