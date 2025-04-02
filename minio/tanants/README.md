### Como instalar o MinIO Tanants com GitOps

## Baixar e atualizar o HELM com o MinIO
```powershell
helm repo add minio-operator https://operator.min.io
```

## Baixar o values para personalização
```powershell
helm show values minio-operator/tenant > minio-tenant-values.yaml
```

# Documentação dos values possíveis:
https://min.io/docs/minio/kubernetes/upstream/operations/install-deploy-manage/deploy-minio-tenant-helm.html

## Baixar o template atualizado com os valores personalizados
- Em um arquivo único:
```powershell
helm template \
  --namespace minio-tanant-dev \
  operator minio-operator/tenant \
  -f minio-tenant-values.yaml > minio-tenant-manifests.yaml
```

- Em arquivos múltiplos
```powershell
helm template \
  --namespace minio-operator \
  operator minio-operator/operator \
  -f minio-operator-values.yaml \
  --output-dir minio-operator-templates
```

