## Installation ArgoCD using manifest yaml

**Steps :**

1. Create namespace **argocd**
   ```
   kubectl create namespace argocd
   ```

2. Install ArgoCD using manifest yaml
   ```
   kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
   ```

3. the default username for login argocd is **admin**

   to get the argocd password, we have to check to the Argocd-initial-admin-secret

   go to check secret named Argocd-initial-admin-secret

   ```
   kubectl -n argocd get secret argocd-initial-admin-secret -o json
   ```
   
   this yaml file from argocd-initial-admin-secret
   ```
   {
    "apiVersion": "v1",
    "data": {
        "password": "UUduNTJiRDh3dFltUjF3OA=="
    },
    "kind": "Secret",
    "metadata": {
        "creationTimestamp": "2023-10-06T07:30:45Z",
        "name": "argocd-initial-admin-secret",
        "namespace": "argocd",
        "resourceVersion": "19833",
        "uid": "071203d8-eaa9-4b53-8c83-303f4d43db6b"
    },
    "type": "Opaque"
}
```

go to https://www.base64decode.org/ to decode your password argocd


