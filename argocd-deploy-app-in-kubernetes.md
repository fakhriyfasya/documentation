# Deploy Application in kubernetes using ArgoCD WEB UI

**Steps :**

1. Login to argocd WEB UI
   

2. in left side, click **Settings** to configure **Projects** and **Repositories**

   ![image](https://github.com/fakhriyfasya/documentation/assets/67684999/e1ec0766-6700-4355-88d7-67e840ebd632)
   

3. Configure or setup Projects

   Click **Project**, and than Click **NEW PROJECTS**

   Fill the **Project Name** and **Desciption**

   After fill the section General, click **Create**

   ![image](https://github.com/fakhriyfasya/documentation/assets/67684999/85a82208-b2fc-4f20-954f-3c741c77bf9f)
   

4. After Create New Project, will pop up setup project page

   we just setup the project in tab **SUMMARY**

   configure your **SOURCE REPOSITORIES** AND **DESTINATION**

   ![image](https://github.com/fakhriyfasya/documentation/assets/67684999/85a8f226-f0f1-45f2-beb1-b3eede4baa19)


   Fill section **SOURCE REPOSITORIES** with your git repository where you save kubernetes manifest yaml

   Click **EDIT**, and click **ADD SOURCE**

   **Notes : in this case i use my github repository**

   After that, click **SAVE**

   ![image](https://github.com/fakhriyfasya/documentation/assets/67684999/08868a09-dc90-4ed2-8ba1-ab5dfe21bd1c)


   NEXT, configure your **DESTINATION**

   Click **EDIT**, and click **ADD DESTINATION**

   Fill **Server, Name and Namespace**

   **Notes : in this case, i use same cluster kubernetes with argocd to deploy app and i already create namespace dev**

   After that, click **SAVE**

   ![image](https://github.com/fakhriyfasya/documentation/assets/67684999/ea4368e9-db6a-43f0-9dc5-86a8656d65a7)


5. Now, configure Reposifories

   Click **Settings** and click **Repositories**

   Click **+ CONNECT REPO**

   ![image](https://github.com/fakhriyfasya/documentation/assets/67684999/8a50e633-0a4d-4b99-a7bb-57a271652ca2)

   First, **choose your connection method**

   Second, **choose type to connect repo**

   Third, **Select your Project name**

   Fourth, **Copy your Repository URL and paste to Repository URL**

   ![image](https://github.com/fakhriyfasya/documentation/assets/67684999/8899ed4d-12e3-47f0-8058-a54cd8fff234)

   **Notes :**
   In this case, i use **Via HTTPS for connection method**, **type as git**, **my project is demo-argocd** and **my Repository is https://github.com/fakhriyfasya/kubernetes.git** (Public Repository)
   
   In Section **Choose your connection method**. There is 4 method for connection :
   
   1. Via HTTPS
   2. Via SSH
   3. Via Github App
   4. Via Google Cloud
  
   If you use **Via SSH**, you have to put your **SSH Private key** for authentication.
   
   If you use **Via HTTPS** and your Repository is private, you have to fill username and Generate token in your repository as your password.

   


