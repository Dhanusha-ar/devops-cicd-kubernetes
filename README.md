# devops-cicd-kubernetes
# DevOps CI/CD Pipeline with Jenkins, Docker, and Kubernetes

## Overview

This project demonstrates a complete DevOps CI/CD workflow using Jenkins, Docker, and Kubernetes.

The pipeline automatically builds a Docker image from application code, pushes it to a container registry, and deploys the application to a Kubernetes cluster.

## Technologies Used

Jenkins
Docker
Kubernetes
Python Flask
GitHub

## Architecture

Developer Push → GitHub  
↓  
Jenkins Pipeline  
↓  
Docker Build  
↓  
Push to Docker Registry  
↓  
Deploy to Kubernetes  

## Deployment Steps

1. Build Docker Image

docker build -t flask-app .

2. Deploy to Kubernetes

kubectl apply -f kubernetes/

3. Access Application

kubectl get svc
