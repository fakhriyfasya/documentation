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

![image](https://github.com/fakhriyfasya/documentation/assets/67684999/c0074a5f-201f-4c1c-9dcd-061d8032f909)

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

ex : var/Jenkinsfile

2.10 **Save**

![image](https://github.com/fakhriyfasya/documentation/assets/67684999/3aa30ef1-214a-4684-ad4c-8ec9dab4dae9)

**3. Setting Webhook in Github repository**

3.1 Go to **Setting** in Project Repository on Github

3.2 Click **Webhooks**

![image](https://github.com/fakhriyfasya/documentation/assets/67684999/e9468e80-63fb-4ab1-88a4-bad3267faed0)

3.3 Click **Add Webhook**

![image](https://github.com/fakhriyfasya/documentation/assets/67684999/c6825e97-5176-484d-8577-e8c6226fa482)

3.4 Fill **Payload URL** with format **http://<your_jenkins_url>/github-webhook/**

3.5 For **Which events would you like to trigger this webhook?** , in this case i choose **Send me everything**

3.6 Check **Active** and Click **Add Webhook**

![image](https://github.com/fakhriyfasya/documentation/assets/67684999/686e895e-6d84-4d7d-9137-e9eae6a69f90)

3.7 Check connection **webhook**, Clik Link webhook

![image](https://github.com/fakhriyfasya/documentation/assets/67684999/4c101439-647a-4158-ad56-be8a004f54c4)

3.8 Clik **Recent Deliveries** for check the connection and activity

![image](https://github.com/fakhriyfasya/documentation/assets/67684999/158ae0a1-2c34-49d1-8fe4-6538cc30bf1a)

# - END -




