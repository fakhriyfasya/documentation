# Deploy Application in kubernetes using ArgoCD WEB UI

**Steps :**

1. Login to argocd WEB UI

2. in left side, click **Settings** to configure **Projects** and **Repositories**

   ![image](https://github.com/fakhriyfasya/documentation/assets/67684999/e1ec0766-6700-4355-88d7-67e840ebd632)

3. First, configure or setup Projects

   Click **Project**, and than Click **NEW PROJECTS**

   Fill the **Project Name** and **Desciption**

   After fill the section General, click **Create**

   ![image](https://github.com/fakhriyfasya/documentation/assets/67684999/85a82208-b2fc-4f20-954f-3c741c77bf9f)

4. After Create New Project, will pop up setup project page

   we just setup the project in tab **SUMMARY**

   configure your **SOURCE REPOSITORIES** AND **DESTINATION**

   ![image](https://github.com/fakhriyfasya/documentation/assets/67684999/85a8f226-f0f1-45f2-beb1-b3eede4baa19)

   ```
   Fill section **SOURCE REPOSITORIES** with your git repository where you save kubernetes manifest yaml

   Click **EDIT**, and click **ADD SOURCE**

   **Notes : in this case i use my github repository**

   After that, click **SAVE**

   ![image](https://github.com/fakhriyfasya/documentation/assets/67684999/08868a09-dc90-4ed2-8ba1-ab5dfe21bd1c)
   ```

   NEXT, configure your **DESTINATION**

   

   
