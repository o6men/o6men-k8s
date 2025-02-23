Create "database-secret.yaml":
apiVersion: v1
kind: Secret
metadata:
  name: db-secret
type: Opaque
data:
  POSTGRES_USER: (64base)
  POSTGRES_PASSWORD: (64base)
  POSTGRES_DB: (64base)

Create "backend-secret.yaml":
apiVersion: v1
kind: Secret
metadata:
  name: backend-secret
type: Opaque
data:
  BOT_TOKEN: (base64)
  SECRET: (base64)

Run: curl -sfL https://get.k3s.io | sh -
Run: kubectl apply -f https://github.com/cert-manager/cert-manager/releases/download/v1.17.0/cert-manager.yaml
Run: kubectl apply -f ./