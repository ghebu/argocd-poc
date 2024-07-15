## Helm install 
Upstream repo: https://github.com/argoproj/argo-helm/tree/main/charts/argo-cd

```
kubectl create ns argocd-main
helm install my-release argo/argo-cd
kubectl apply -f main-argocd-application.yaml -n argocd-main
```


## Helm install argocd-customer


If this is the 2nd argocd installation in the cluster then the CRDs installation needs to be set to false. Either from the Helm install CLI or from the values file. 


```
cd helm/charts/argo-cd
helm dep up
helm install argocd-customer  .  -n argocd-customer --set crds.install=false
```

The folder argocd-app-of-apps was added, which has the main ArgoCD Application which points to additional ArgoCD CRDs from the argocd-sandbox repository
