# HOW TO CONFIGURE WEBHOOK TRIGGER FROM GITHUB TO JENKINS

**Step :**

**1. Create New Pipeline on Jenkins**

1.1 Click **new item** in dashbord Jenkins

![image](https://github.com/fakhriyfasya/documentation/assets/67684999/af5a2a56-8b8c-44f4-99f6-07f0172bd6cd)
              
1.2 **Enter an item name** or enter the project name
              
1.3 choose **Pipeline**
              
1.4 Click **OK**

![image](https://github.com/fakhriyfasya/documentation/assets/67684999/add680a8-d651-45a0-963e-4f928b3b2aba)
      
**2. Configure project**

2.1 In section **General**, **Check Github project** and copy your repository URL

2.2 In Section **Build triggers**, **Check GitHub hook trigger for GITScm polling**

![image](https://github.com/fakhriyfasya/documentation/assets/67684999/3e160faf-6c1b-4a78-8452-18c11fd7f07b)

2.3 Go to section **Pipeline**

2.4 Choose **Pipeline script from SCM** in section Definition

2.5 Choose **Git** as method SCM

2.6 Copy your **Repository URL**. same like Project URL in section General

2.7 You have to add and choose the **credential** if your repository is private. In this case my repository is public.

2.8 Go to **Branch spesifier**,

Fill the branch where your jenkinsfile is located. 

if it is in the branch main, enter **(*/main)**. and 

if your branch is master, enter **(*/master)**

2.9 Fill the **Script Path**, 

If the location of the **Jenkinsfile** is in a folder, you must include the name of the folder in the Script Path

ex : /var/Jenkinsfile

2.10 **Save**

![image](https://github.com/fakhriyfasya/documentation/assets/67684999/40ef4d4d-be17-4c20-a947-bd6de92e544a)
