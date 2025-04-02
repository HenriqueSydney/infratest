### Como instalar o MinIO Operator com GitOps

## Baixar e atualizar o HELM com o MinIO
```powershell
helm repo add minio-operator https://operator.min.io
```

## Baixar o values para personalização
```powershell
helm show values minio-operator/operator > minio-operator-values.yaml
```

# Documentação dos values possíveis:
https://min.io/docs/minio/kubernetes/upstream/reference/operator-chart-values.html#minio-operator-chart-values

## Baixar o template atualizado com os valores personalizados
- Em um arquivo único:
```powershell
helm template \
  --namespace minio-operator \
  operator minio-operator/operator \
  -f minio-operator-values.yaml > minio-operator-manifests.yaml
```

- Em arquivos múltiplos
```powershell
helm template \
  --namespace minio-operator \
  operator minio-operator/operator \
  -f minio-operator-values.yaml \
  --output-dir minio-operator-templates
```

