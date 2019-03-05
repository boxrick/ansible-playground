#Ansible Playground
=========

This is a really simple example repo to get started with Ansible syntax and modules.
### Requirements

* Ansible ```pip install ansible```
* Vagrant https://www.vagrantup.com/downloads.html
* Docker https://www.docker.com/get-started

### Modules reference

https://docs.ansible.com/ansible/latest/modules/modules_by_category.html

### Usage
Some examples of usage:

* ```vagrant up --provider docker centos6```
* ```vagrant up --provider docker centos7```
* ```vagrant up --provider docker bionic```
* ```vagrant up --provider docker xenial```

* ```vagrant provision centos6```
* ```vagrant provision centos7```
* ```vagrant provision bionic```
* ```vagrant provision xenial```

* ```vagrant destroy -f; vagrant up .....```
