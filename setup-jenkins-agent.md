# Setup Jenkins Agent as worker job

**Steps:**

In this case username agent linux is **jenkins-agent**

In order to connect an SSH agent with the user **jenkins-agent** , follow these steps:

On the agent machine:

### 1.	Log in to the agent machine as **jenkins-agent**:
```
sudo su jenkins-agent
```

### 2.	Create private and public SSH keys. 

The following command creates the private key jenkinsAgent_rsa and the public key jenkinsAgent_rsa.pub. 

It is recommended to store your keys under ~/.ssh/ so we move to that directory before creating the key pair.
```
cd ~/.ssh/ && ssh-keygen -t rsa -m PEM -C "jenkins-agent" -f "jenkins_agent_rsa"
```

Note : To increase security, a passphrase is advisable to associate it to your Private Key

### 3.	Add the public SSH key to the list of authorized keys on the agent machine
```
cat jenkins_agent_rsa.pub >> ~/.ssh/authorized_keys
```

### 4.	Ensure that the permissions of the ~/.ssh directory is secure, as most ssh daemons will refuse to use keys that have file permissions that are considered insecure:
```
chmod 700 ~/.ssh
```
```
chmod 600 ~/.ssh/authorized_keys ~/.ssh/jenkins_agent_rsa
```

### 5.	Copy the private SSH key (~/.ssh/jenkins_agent_rsa) from the agent machine to your OS clipboard.
```
cat ~/.ssh/jenkins_agent_rsa
```

### 6.  In jenkins, go to *manage Jenkins* and click *nodes*

![image](https://github.com/fakhriyfasya/documentation/assets/67684999/e8a4ede9-ac43-4d93-a503-4b017eeb6ced)

### 7.  Click *New Node* 

### 8.  Fill *node name* choose *type : permanent agent* and click *Create*

![image](https://github.com/fakhriyfasya/documentation/assets/67684999/85364c9a-4f9d-40eb-a552-bcd2fdc4c950)

### 9.	Fill in the Remote root directory with a path the user on the agent is allowed to write to.
in this case,

i set **number of executors** are **2**

note: the max number of executors are 10

my root directory is **/home/jenkins-agent/jenkins_workspace/**

and my i use **linux docker java** as name of label

for usage choose **use this node as much as possible**

![image](https://github.com/fakhriyfasya/documentation/assets/67684999/55be6220-e30f-4586-97d8-8556cdebeafa)

### 10. set the Host value to the ip address of the agent, and press the Add button for Credentials:
in section **Launch Method** choose **Launch agent via SSH**

fill the **Host** section to **<ip_address_the_jenkins_agent>** 

clik **Add** for setting your **credential**

![image](https://github.com/fakhriyfasya/documentation/assets/67684999/2fa803a8-0c89-4055-8536-e15466b8407b)

click the **Domain** button and choose **Global Credential** 

click the **kind** button and choose **SSH Username with private key**

Input your **ID**

Descripstion is optional

Input the same **username** as **SSH key's username**



in section **Host Key Verification Strategy**, choose **Manualy trusted key Verification Strategy**

and **check** the **Require manual verification of initial connection**

in section **Availability**, choose **Keep this agent online as much as possible** and **save**

![image](https://github.com/fakhriyfasya/documentation/assets/67684999/cd084c1a-f05b-4b4d-b6f7-b1b20382eb5f)


