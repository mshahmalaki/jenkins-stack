# Jenkins Stack
Setup [jenkins-stack-docker](https://github.com/mshahmalaki/jenkins-stack-docker) with Vagrant & Ansible

### Clone repository with submodule
```
git clone --recurse-submodules https://github.com/mshahmalaki/jenkins-stack.git
```

### Create virtual environment for install Ansible package
```
python3 -m venv venv
source venv/bin/activate
pip install -U pip
pip install -r requirements.txt
```
> :warning: **According to Ansible documentation, it is not possible to install Ansible on Microsoft Windows.** Unless you use [this](https://phoenixnap.com/kb/install-ansible-on-windows) document

### Setup
```
# PROVIDER = libvirt, parallels, virtualbox
vagrant up --provision --provider=<PROVIDER>
```

### URLs and Credentials
Assuming the Host IP is 192.168.1.10:

| Service | Protocol | Port | Example | 
|---------|:---------|:------|---------|
| Jenkins | HTTP | 8080 | http://192.168.1.10:8080 |
| Gitea | HTTP | 3000 | http://192.168.1.10:3000 |
| Gitea | SSH | 2233 |  |
| Registry Web UI | HTTP | 80 | http://192.168.1.10 |
| Registry | HTTPS | 443 | https://192.168.1.10 |
| MinIO | HTTP | 9001 | http://192.168.1.10:9001 |
> MinIO Username & Password: **minioadmin**

### Login
```
vagrant ssh
```