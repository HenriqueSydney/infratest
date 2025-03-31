### Como instalar o NGINX Ingress com Helm

## Baixar e atualizar o HELM com o MinIO
```powershell
helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm repo update
```

## Baixar o values para personalização
```powershell
helm show values ingress-nginx/ingress-nginx > values.yaml
```

# Documentação dos values possíveis e outras configurações:
https://artifacthub.io/packages/helm/ingress-nginx/ingress-nginx

## Baixar o template atualizado com os valores personalizados
```powershell
helm template ingress-nginx ingress-nginx/ingress-nginx --namespace ingress -f values.yaml > ingress-nginx.yaml
```

## Aplicar
```powershell
kubectl apply -f ./ingress/
```

