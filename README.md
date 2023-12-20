# sonarqube-iac

Sonarqube for Gitlab Infrastructure As Code using vm.


### Prerequisites
ansible 2.16.1+
```
cd sonarqube-iac
rm -fr ~/.ansible/roles/rv-common || echo .
sleep 2
ansible-galaxy install -r roles/requirements.yml
```
***No need for this on Ansible Tower but needed on Ansible CLI***

### Requirements
- centos8/stream with sudo access
- internet access
- dns server, if none, use /etc/hosts

_If firewalled, you need these binaries, 
unfortunately you have to do it, 
please add it and create a pull request,_
```
- epel-release
- java 11
- maven
```

### Instructions

On <home>/.bashrc of ansible, add,
```
export ansible_user=xxx
export ansible_password=xxx
```
Make sure ansible_user have sudo access on the target vm.

Run the ansible in cli,
```
ansible-playbook -i inventory/linux.ini deploy.yml -v
```

***The version or tag is defined on the variable of group_vars/all.***</br>
***The docker I haven't started it yet but if you can please create a pull request.***</br>
