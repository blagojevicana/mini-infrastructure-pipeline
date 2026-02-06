# mini-cloud-service

## Overview
This project demonstrates a **containerized Python API deployed on Kubernetes**, with **NGINX load balancing** and automated **CI/CD** using GitHub Actions. It showcases DevOps and backend skills such as Docker, Kubernetes, infrastructure automation and continuous deployment.

## Features
- Python Flask API
- Docker containerization
- Kubernetes deployment
- NGINX reverse proxy & load balancing
- GitHub Actions CI/CD pipeline for automated build & deployment

## How to Run Locally

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
