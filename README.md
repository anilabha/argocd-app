## For raw yaml manifest like deployment, service and route

1. deployment.yaml
2. route.yaml
3. service.yaml

- The directory needs to mentioned in ArgoCD application:
```
yamls/
```
- ArgoCD application:
```
project: default
source:
  repoURL: 'https://github.com/anilabhabaral/argocd-app.git'
  path: yamls
  targetRevision: HEAD
destination:
  server: 'https://kubernetes.default.svc'
  namespace: test-helm-abaral
syncPolicy:
  automated:
    prune: true
    selfHeal: true
```

## Helm Chart
- For Helm chart use this directory in ArgoCD application:
```
helloworld-helm-chart
```

- ArgoCD application:
```
project: default
source:
  repoURL: 'https://github.com/anilabhabaral/argocd-app.git'
  path: helloworld-helm-chart
  targetRevision: HEAD
destination:
  server: 'https://kubernetes.default.svc'
  namespace: test-helm-abaral
syncPolicy:
  automated:
    prune: true
    selfHeal: true
```