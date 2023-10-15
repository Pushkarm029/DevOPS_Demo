## Devops Demo Repo

### Run NextJS app

```bash
nextjs-service
```

### Using Docker

```bash
docker compose up
```

### Using minikube

```bash
minikube start

kubectl apply -f manifests/deployment.yml

kubectl apply -f manifests/services.yml

kubectl get all

minikube service --url nextjs-service

# then open the output url in browser to access cluster locally

# To scale up containers
kubectl scale deployment.apps/nextjs-app --replicas=10
```