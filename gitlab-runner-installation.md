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

**4. Go to GitLab Web UI for copy your Group token Runner**
> 1. Clik **search** and choose **view all my group**
> ![image](https://github.com/fakhriyfasya/documentation/assets/67684999/e57f5ab0-763d-4706-8060-3e5495e923be)

> 2. **Choose your group** for using this gitlab runner
> ![image](https://github.com/fakhriyfasya/documentation/assets/67684999/f6f031f2-9b94-4abd-9086-c8564ec56df1)

> 3. Clik **Build** and **Choose Runner**
> ![image](https://github.com/fakhriyfasya/documentation/assets/67684999/419819a1-7a76-4e60-9876-f0fd41ac12b5)

> 4. Clik Runner **Group**, klik **3 dot button** and **copy** your Registration token and paste to your text editor because we need this token for regis to your gitlab runner
> 
> ![image](https://github.com/fakhriyfasya/documentation/assets/67684999/b083f417-b587-4f54-aa9f-cf603262bb9c)

   
**5. Registration gitlab-runner**
   
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

> Note : docker:dind = container image for build, run and push docker container using Dockerfile
> you can choose other docker image for default docker image in this gitlab runner. exp : ubuntu, nginx and node


6. .gitlab-ci.yml for using 

