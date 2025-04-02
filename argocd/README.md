### Como instalar o ArGoCD com Helm

## Baixar e atualizar o HELM com o MinIO
```powershell
helm repo add argo https://argoproj.github.io/argo-helm
helm repo update
```

## Baixar o values para personalização
```powershell
helm show values argo/argo-cd > values.yaml
```

# Documentação dos values possíveis:
https://artifacthub.io/packages/helm/argo/argo-cd

## Baixar o template atualizado com os valores personalizados
```powershell
helm template argocd argo/argo-cd --namespace argocd -f values.yaml > argocd.yaml
```

## Aplicar
```powershell
kubectl apply -f ./argocd/namespace.yaml
kubectl apply -f ./argocd/argocd.yaml

```

## PortFoward, enquanto não instalado o Ingress
```powershell
kubectl port-forward svc/argocd-server -n argocd 8080:443
```

## Recuperar a senha de administrador
```powershell
kubectl get secret argocd-initial-admin-secret -n argocd -o jsonpath="{.data.password}" | base64 --decode
```

