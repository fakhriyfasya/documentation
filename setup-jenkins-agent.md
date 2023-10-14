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


