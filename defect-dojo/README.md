### Como instalar o ArGoCD com Helm

## Baixar e atualizar o HELM com o MinIO
```powershell
helm repo add defectdojo https://raw.githubusercontent.com/DefectDojo/django-DefectDojo/helm-charts
helm repo update
```

## Baixar o values para personalização
```powershell
helm show values grafana/grafana > values.yaml
```

# Documentação :
https://github.com/DefectDojo/django-DefectDojo/blob/dev/readme-docs/KUBERNETES.md

## Baixar o template atualizado com os valores personalizados
```powershell
helm template my-grafana grafana/grafana --namespace monitoring -f values.yaml > grafana.yaml
```

## Aplicar
```powershell
kubectl apply -f ./grafana/
```
