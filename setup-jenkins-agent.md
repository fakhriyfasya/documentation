# Setup Nodes/Jenkins Agent as worker

**Steps:**

In this case username agent linux is **jenkins-agent**

In order to connect an SSH agent with the user **jenkins-agent** , follow these steps:

On the agent machine:

### 1.	Log in to the agent machine as **jenkins-agent**:
```
sudo su jenkins-agent
```

### 2.	Create private and public SSH keys. 

The following command creates the private key jenkins_agent_rsa and the public key jenkins_agent_rsa.pub. 

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

and i use **linux docker java** as name of label

for usage choose **use this node as much as possible**

![image](https://github.com/fakhriyfasya/documentation/assets/67684999/55be6220-e30f-4586-97d8-8556cdebeafa)

### 10. set the Host value to the ip address of the agent, and press the Add button for Credentials:
in section **Launch Method** choose **Launch agent via SSH**

fill the **Host** section to **<ip_address_the_jenkins_agent>** 

clik **Add** for setting your **credential**

![image](https://github.com/fakhriyfasya/documentation/assets/67684999/2fa803a8-0c89-4055-8536-e15466b8407b)

## 11.  Add Jenkins Credentials for Jenkins Agent

click the **Domain** button and choose **Global Credentials** 

click the **kind** button and choose **SSH Username with private key**

Input your **ID**

**Description** is optional

Input the same **username** as **SSH key's username**

Enter your **Private Key**

fill the **passphase** if you set your passphase on SSH key

click **Add** 

![image](https://github.com/fakhriyfasya/documentation/assets/67684999/81e77cad-90c5-4bcf-b54e-295e72af14be)

## 12.  setting **Host Key Verification Strategy** and **Availability**

in section **Host Key Verification Strategy**, choose **Manualy trusted key Verification Strategy**

and **check** the **Require manual verification of initial connection**

in section **Availability**, choose **Keep this agent online as much as possible** and **save**

![image](https://github.com/fakhriyfasya/documentation/assets/67684999/cd084c1a-f05b-4b4d-b6f7-b1b20382eb5f)

## 13.  Check log the new Nodes

after all the Node configurations are saved, the new nodes you have just created will appear.

![image](https://github.com/fakhriyfasya/documentation/assets/67684999/107cb9ee-a17d-41ff-aeea-ca9b9c4f728f)

if there is no crossmark on the new node, it means the node is online and the connection is working.

for make sure the new nodes online and connected to jenkins Server, we have to check the log nodes

click the new nodes, in this case my new nodes is **jenkins-agent**

click **log** to check log the new nodes.

![image](https://github.com/fakhriyfasya/documentation/assets/67684999/52349a45-42fb-46dc-ac96-2152e1b4bf05)

If the **agent successfully connected and online**, it's mean the nodes ready to for running job.

## - END - 
