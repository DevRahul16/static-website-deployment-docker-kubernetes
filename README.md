# static-website-deployment-docker-kubernetes

## Static Website Deployment using Docker and Kubernetes

### Project Overview
This project demonstrates how to **deploy a static website** using **Docker** and **Kubernetes**.
It showcases the complete workflow from **Git version control**, **Docker image creation**, **DockerHub integration**, and **Kubernetes deployment** using a simple Nginx-based web server.

### Repository Layout
```
static-website-deployment-docker-kubernetes/
│
├── index.html
├── about.html
├── membership.html
├── contact.html
│
├── Dockerfile
├── dep.yaml
│
├── diagrams/
│   ├── project-flowchart.png
│   └── architecture-diagram.png
│
├── docs/
│   ├── commands.md
│   └── setup-guide.md
│
└── README.md
```

### Flow Diagram
![](diagrams/project-flowchart.png)

### Tech Stack
- Git
- Docker
- DockerHub
- Kubernetes (Docker Desktop)
- Nginx

## Steps to Deploy

### 1. Create and Push Website Files to GitHub
```bash
git init
git add .
git commit -m "Initial static website commit"
git branch -M main
git remote add origin https://github.com/devrahul16/static-website-deployment-docker-kubernetes.git
git push -u origin main
```

### 2. Clone Repository
```bash
git clone https://github.com/devrahul16/static-website-deployment-docker-kubernetes.git
cd static-website-deployment-docker-kubernetes
```

### 3. Build Docker Image
```bash
docker build -t devrahul16/myweb:v1 .
```

### 4. Push Docker Image to DockerHub
```bash
docker push devrahul16/myweb:v1
```

### 5. Deploy on Kubernetes
```bash
kubectl apply -f dep.yaml
kubectl get pods
kubectl get svc
```

Open http://127.0.0.1:30080/ to view the site (if using Docker Desktop Kubernetes or similar local cluster).

## Future Enhancements
- Add CI/CD pipeline (GitHub Actions) to build and push the image automatically.
- Use a Helm chart for templated deployments.
- Add Ingress with TLS for production-like routing.
- Add readiness/liveness probes and resource requests/limits.
- Scale replicas and demonstrate rolling updates.

## Author
Rahul Kumar
