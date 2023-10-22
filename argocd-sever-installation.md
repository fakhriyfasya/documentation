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

   go to check **service** named **argocd-server**
   ```
   kubectl -n argocd get svc argocd-server -o yaml
   ```
   this yaml file from service argocd-server

   ![image](https://github.com/fakhriyfasya/documentation/assets/67684999/07e40b3a-a531-4865-8a5f-49d7f2083f53)

   **in kubernetes, there is 3 ways service type to access :**
   1. ClusterIP
      
   2. NodePort
      
   3. LoadBalancer
  
   in this case i use service type **LoadBalancer** to access argocd

4. the default username for login argocd is **admin**

   to get the argocd password, we have to check to the Argocd-initial-admin-secret

   go to check **secret** named **Argocd-initial-admin-secret**

   ```
   kubectl -n argocd get secret argocd-initial-admin-secret -o yaml
   ```
   
   this yaml file from argocd-initial-admin-secret

   ![image](https://github.com/fakhriyfasya/documentation/assets/67684999/788138de-2ac5-4083-bdc2-be9fe3690585)

   go to https://www.base64decode.org/ to decode your password argocd

4. Login argocd from Web UI

   ![image](https://github.com/fakhriyfasya/documentation/assets/67684999/09e19fd4-a4ef-4170-8643-450891fb898e)


# -END-

