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


### Setup
```
# PROVIDER = libvirt, parallels, virtualbox
vagrant up --provision --provider=<PROVIDER>
```

### URLs and Credentials
Assuming the Host IP is 192.168.1.10:
- Jenkins: http://192.168.1.10:8080 <br/>
- Gitea: http://192.168.1.10:3000 <br/>
- Gitea (SSH): ssh://192.168.1.10:2233 <br/>
- MinIO: http://192.168.1.10:9001 <br/>
  - MinIO Username & Password: **minioadmin**

### Login
```
vagrant ssh
```