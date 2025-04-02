### Organização do MinIO

```plaintext
├── minio/
│   ├── operator/
│   │   ├── minio-operator-manifests.yaml
│   │   ├── minio-operator-values.yaml
│   │   ├── namespace.yaml
│   ├── tanants/
│   │   ├── development/
│   │   │   ├── minio-tenant-values.yaml
│   │   │   ├── minio-tenant-manifests.yaml
│   │   │   ├── ingress.yaml
│   │   ├── staging/
│   │   │   ├── minio-tenant-values.yaml
│   │   │   ├── minio-tenant-manifests.yaml
│   │   │   ├── ingress.yaml
│   │   ├── production/
│   │   │   ├── minio-tenant-values.yaml
│   │   │   ├── minio-tenant-manifests.yaml
│   │   │   ├── ingress.yaml
│   ├── argocd-applications/     # PASTA PARA REFERENCIAR OS ARQUIVOS MANIFEST PARA APLICAÇÃO - INTEGRAÇÃO ARGOCD
│   │   ├── minio-operator.yaml
│   │   ├── minio-tenant-dev.yaml
│   │   ├── minio-tenant-staging.yaml
│   │   ├── minio-tenant-prod-finance.yaml
│   │   ├── minio-tenant-prod-auth.yaml
│   │   ├── minio-tenant-prod-analytics.yaml
```