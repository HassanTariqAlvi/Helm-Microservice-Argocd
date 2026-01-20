helm install argocd argo/argo-cd -n argocd --create-namespace -f argocd-values.yaml


kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d