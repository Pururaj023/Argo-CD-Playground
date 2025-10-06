# Argo-CD-Playground

## Dployed on minikube 

Start The minikube Container
```
minikube start memory=4096 --driver=docker 

```

## Install Argo-CD on minikube

Create a Namespace for Argo CD

```
kubectl create namespace argocd

```
Install Argo-CD

```
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

Access the Agro CD ui using 

```
minikube service argocd-server -n argocd

```

Argo CD --> Username = Admin

Argo CD --> Password

```
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
```

Configure the AgroCD to use the repo 
1. Add the repo link 
2. add the path Wisecow-k8s

## ArgoCD will automaticly delpoy the application on minikube cluster 

## Access the wisecow application  

```
minikube service wisecow-svc -n wisecow
```

## Access the minikube dashboard

```
minikube dashboard
```