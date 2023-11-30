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
argocd admin initial-password -n argocd
kubectl get secret argocd-initial-admin-secret -n argocd -o jsonpath="{.data.password}" | base64 -d; echo

kubectl apply -n argocd -f argocd-secret.yaml
```

Nginx Controller
```bash
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.1.3/deploy/static/provider/cloud/deploy.yaml
kubectl -n ingress-nginx --address 0.0.0.0 port-forward svc/ingress-nginx-controller 80
```

Web App
```bash
kubectl port-forward -n myapp svc/my-service 8081:5000
# https://tcc-01.th1.proen.cloud/predict
```