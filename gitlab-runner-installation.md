## Installation Spesific Gitlab-Runner using Docker

**Steps :**

**1. Install OS for Gitlab-Runner**

> Note : in this case, i using Ubuntu 22.04 for OS gitlab-runner


**2. Install Docker, because we using docker as a runner**
   
> Install dependency for installation docker & install docker
```
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg
```

```
# Add the repository to Apt sources:
echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

```
sudo apt-get install docker-ce docker-ce-cli -y containerd.io docker-buildx-plugin docker-compose-plugin
```


**3. Install gitlab-runner**

> Add the official GitLab repository for Ubuntu/Debian
   
```
curl -L "https://packages.gitlab.com/install/repositories/runner/gitlab-runner/script.deb.sh" | sudo bash
```
> Install the latest version of GitLab Runner for Ubuntu/Debian
   
```
sudo apt-get install gitlab-runner
```


**4. Registration gitlab-runner**
   
``` 
sudo gitlab-runner register
```
```
Enter the GitLab instance URL (for example, https://gitlab.com/):
https://gitlab.com/

Enter the registration token:
<Registration your group token runner>

Enter a description for the runner:
[<Default Nama Runner>]: <Your Runner Name>

Enter tags for the runner (comma-separated):
<Your Tag Runner (opsional)>

Enter optional maintenance note for the runner:
<Catatan tambahan Runner kamu (opsional)>

Enter an executor: custom, docker, parallels, shell, docker+machine, docker-ssh+machine, instance, docker-ssh, ssh, virtualbox, kubernetes:
docker

Enter the default Docker image (for example, ruby:2.7):
docker:dind
```

5. 


