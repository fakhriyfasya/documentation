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

3. to access the argocd Web UI, you have to check the service of argo cd

   go to check service named argocd-server
   ```
   kubectl -n argocd get svc argocd-server -o yaml
   ```
   this yaml file from service argocd-server

   ![image](https://github.com/fakhriyfasya/documentation/assets/67684999/07e40b3a-a531-4865-8a5f-49d7f2083f53)

   **there is 3 ways service type to access :**
   1. Cluster IP
      
   2. NodePort
      
   3. LoadBalancer
  
   in this case i use service type **LoadBalancer**

4. the default username for login argocd is **admin**

   to get the argocd password, we have to check to the Argocd-initial-admin-secret

   go to check secret named Argocd-initial-admin-secret

   ```
   kubectl -n argocd get secret argocd-initial-admin-secret -o yaml
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

4. Login argocd from Web UI
   

