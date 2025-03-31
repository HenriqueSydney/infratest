### Como instalar o ArGoCD com Helm

## Baixar e atualizar o HELM com o MinIO
```powershell
helm repo add grafana https://grafana.github.io/helm-charts
helm repo update
```

## Baixar o values para personalização
```powershell
helm show values grafana/grafana > values.yaml
```

# Documentação :
https://grafana.com/docs/grafana/latest/setup-grafana/installation/helm/

## Baixar o template atualizado com os valores personalizados
```powershell
helm template my-grafana grafana/grafana --namespace monitoring -f values.yaml > grafana.yaml
```

## Aplicar
```powershell
kubectl apply -f ./grafana/
```
