# K8s Nginx Deployment

Simple Kubernetes deployment with a custom nginx container.

## Prerequisites

- Docker
- Minikube
- kubectl

## Setup

1. Start Minikube:
```bash
minikube start
```

2. Build the Docker image in Minikube:
```bash
eval $(minikube docker-env)
docker build -t my-nginx-app .
```

3. Deploy to Kubernetes:
```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

4. Access the service:
```bash
minikube service nginx-service
```

## Files

- `Dockerfile` - Builds nginx container with custom HTML
- `index.html` - Custom HTML page
- `deployment.yaml` - Kubernetes deployment (2 replicas)
- `service.yaml` - Kubernetes LoadBalancer service

## Cleanup

```bash
kubectl delete -f service.yaml
kubectl delete -f deployment.yaml
```