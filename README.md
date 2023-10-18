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

### using kyverno - policy engine

```bash
minikube start

helm repo update

helm install kyverno kyverno/kyverno -n kyverno --create-namespace

kubectl get pods -n kyverno

kubectl apply -f kyverno-policies/match_label.yml

kubectl get pods -n kyverno

kubectl apply -f manifests/deployment.yml
# If manifests/deployment.yml have my-app as label policy will fail
```