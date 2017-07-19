# Vagrant Box (Centos/7) with Minimal Jenkins Install
This is a minimal setup of Jenkins for demo purposes by Jeremy Nevill and creates:
* Centos 7 virtual machine
* Jenkins installation port mapped to the host on localhost:8080

## Requirements
Mac with vagrant and virtualbox installed.

## Instructions

### 1) Ansible Setup on Mac
Requires default Mac OS python and pip then:
```
sudo easy_install pip
sudo pip install ansible
```

### 2) Install [Ansible Galaxy](https://galaxy.ansible.com) Roles
```
ansible-galaxy install geerlingguy.java -p ./roles/
ansible-galaxy install geerlingguy.jenkins -p ./roles/
```

### 3) Vagrant Up
Start the brand new vagrant centos box from the terminal with:
```
vagrant up
```

Once the machine creation, install of java then Jenkins has finished browse to:

#### [localhost:8080](http://localhost:8080)

---

## Notes

To ssh onto the new vm use:
```
vagrant ssh
```
un: vagrant 
pw: vagrant

The vagrant up automatically runs the playbook agains the virtual machine, to manually run the playbook setup ssh auth then:
```
ansible-playbook jenkins-server.yml -i hosts
```

---

Copyright (c) 2017 Jeremy Nevill
