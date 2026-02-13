helm install argocd argo/argo-cd -n argocd --create-namespace -f argocd-values.yaml


kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d

git@github.com:HassanTariqAlvi/Helm-Microservice-Argocd.git



helm install my-issuer . --namespace cert-manager --create-namespace  --wait



helm install traefik . --namespace traefik --create-namespace  --wait