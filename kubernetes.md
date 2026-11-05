# Kubernetes Deployment Using Minikube

## Objective

To deploy my previous full-stack application (Flask frontend and Express backend) in a local Kubernetes cluster using Minikube.

## Technologies Used

- Docker
- Kubernetes
- Minikube
- kubectl
- Flask
- Express.js
- YAML
- Linux

## Project Overview

In this assignment, I deployed my Flask frontend and Express backend applications on a local Kubernetes cluster using Minikube.

I created separate Docker images for both applications and prepared Kubernetes Deployment and Service YAML files. After applying the configuration files, I verified that the pods and services were running successfully.

## Tasks Performed

### 1. Application Containerization

I created separate Dockerfiles for both applications.

- Created a Dockerfile for the Flask frontend.
- Created a Dockerfile for the Express backend.
- Installed the required dependencies.
- Built Docker images for both applications.

Example commands:

```bash
docker build -t flask-frontend:latest ./frontend

docker build -t express-backend:latest ./backend
```

### 2. Start Minikube

I started the local Kubernetes cluster using Minikube.

```bash
minikube start
```

Checked Minikube status:

```bash
minikube status
```

Checked Kubernetes nodes:

```bash
kubectl get nodes
```

### 3. Kubernetes Configuration Files

I created separate Deployment and Service YAML files for both applications.

**Frontend:**
- frontend-deployment.yaml
- frontend-service.yaml

**Backend:**
- backend-deployment.yaml
- backend-service.yaml

The Deployment files define the container images, replicas, labels, and container ports.

The Service files expose the applications and provide stable network communication with the pods.

### 4. Apply Kubernetes Manifests

I applied the Kubernetes YAML files using kubectl.

```bash
kubectl apply -f frontend-deployment.yaml

kubectl apply -f frontend-service.yaml

kubectl apply -f backend-deployment.yaml

kubectl apply -f backend-service.yaml
```

### 5. Verify Kubernetes Resources

After applying the configuration files, I checked the status of the Kubernetes resources.

Check pods:

```bash
kubectl get pods
```

Check deployments:

```bash
kubectl get deployments
```

Check services:

```bash
kubectl get services
```

Check all resources:

```bash
kubectl get all
```

### 6. Access the Application

I accessed the frontend application through the Minikube Service.

```bash
minikube service <frontend-service-name>
```

For a NodePort service, I can also retrieve its URL using:

```bash
minikube service <frontend-service-name> --url
```

I opened the frontend in the browser and tested the application and its backend communication.

## Useful Troubleshooting Commands

Describe a pod:

```bash
kubectl describe pod <pod-name>
```

Check pod logs:

```bash
kubectl logs <pod-name>
```

Check Kubernetes events:

```bash
kubectl get events
```

Check Minikube status:

```bash
minikube status
```

## What I Learned

1. How to containerize Flask and Express applications using Docker.
2. How to start and manage a local Kubernetes cluster using Minikube.
3. How to create Kubernetes Deployment and Service YAML files.
4. How to deploy multiple application components in Kubernetes.
5. How to manage pods, deployments, and services using kubectl.
6. How to verify and access applications running inside a Kubernetes cluster.

## Conclusion

I successfully deployed my Flask frontend and Express backend applications in a local Kubernetes cluster using Minikube.

Through this assignment, I learned the basic Kubernetes deployment process, Docker image management, Kubernetes YAML configuration, and application verification using kubectl.

This assignment helped me understand how containerized full-stack applications can be deployed and managed using Kubernetes.