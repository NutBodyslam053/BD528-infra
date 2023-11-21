## For Infra Developer
Install ArgoCD
```bash
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

ArgoCD UI
```bash
kubectl port-forward -n argocd svc/argocd-server 8080:443
```

ArgoCD Secret
```bash
kubectl get secret argocd-initial-admin-secret -n argocd -o jsonpath="{.data.password}" | base64 -d; echo
```

Web App
```bash
kubectl port-forward -n myapp svc/my-service 8081:5000
https://tcc-01.th1.proen.cloud/predict
```