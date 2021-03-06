## Mastering Ansible Repo orginal author: James Spruin, https://github.com/spurin/masteringansible

Repository for course content for Packt Mastering Ansible Course
URL: https://www.safaribooksonline.com/library/view/mastering-ansible/9781788629515/

Revised to use at team skill session @ IBM.
____

## Install Ansible
- Using CentOS 7 or RHEL 7
```
# wget http://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
# rpm -ivh epel-release-latest-7.noarch.rpm
# yum install ansible
```
- Other OS [Other OS](http://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installing-the-control-machine)

## Download playbooks
```
# yum install git
# git clone https://github.com/insankim/masteringansible.git
```
____

## Playbooks to be used at session
0. Make sure the controller node can ssh to target nodes using a ssh key
```
# ssh-keygen //  when there is no previous key
# ssh-copy-id <host>

```
1. 01-05-03 Validating Ansible Installation
```
ansible all -m ping
ansible all -i -m ping
ansible centos -m ping
ansible ubuntu -m ping
```

2. 02-01-11 Ansible Inventories
```
# ansible all -m ping -o
# ansible linux -m ping -e 'ansible_port=22'
```

3. 02-05-17 Ansible Playbooks, Variables
```
# ansible-playbook variables_playbook.yml
# ansible-playbook variables_playbook.yml -e '{"extra_vars_key": "extra vars value in json"}'
# ansible-playbook variables_playbook.yml -e '{extra_vars_key: extra vars value in yaml}'
# ansible-playbook variables_playbook.yml -e @extra_vars_file.yml
# ansible-playbook variables_playbook.yml -e @extra_vars_file.json

# ansible
```

4. 02-06-06 Ansible Playbooks, Facts
```
# anible-playbook facts_playbook.yml
```

5. 02-08-10 Ansible Playbooks, Creating and Executing
```
# ansible-playbook nginx_playbook.yml
```

6. 03-03 Register and when
``` 
# ansible-playbook register_when_playbook.yml
```

7. 04-03-06 Structuring Ansible Playbooks, Using Roles
```
# ansible-playbook nginx_awsomeweb_plybook.yml
```
