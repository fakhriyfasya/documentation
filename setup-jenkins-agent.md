# Setup Jenkins Agent as worker job

**Steps:**

In this case username agent linux is **jenkins-agent**

In order to connect an SSH agent with the user **jenkins-agent** , follow these steps:

On the agent machine:

# 1.	Log in to the agent machine as **jenkins-agent**:
```
sudo su jenkins-agent
```

# 2.	Create private and public SSH keys. 

The following command creates the private key jenkinsAgent_rsa and the public key jenkinsAgent_rsa.pub. 

It is recommended to store your keys under ~/.ssh/ so we move to that directory before creating the key pair.
```
cd ~/.ssh/ && ssh-keygen -t rsa -m PEM -C "jenkins-agent" -f "jenkins_agent_rsa"
```

Note : To increase security, a passphrase is advisable to associate it to your Private Key


