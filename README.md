## Project Overview

Deploying Node.js Hello-World Applications with Ansible.

---

## Setup the Enviroment

* Environment used is Ubuntu16 in cloud9.
* AWS account with IAM role created.
* A testing ec2 instance with the tag of Project:demoinstances.

### Install Ansible in Ubuntu or [Refer: Other Operating system](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)

* `pip install --user ansible`

## To Run Ansible

### To Add hosts to the Inventory file

```
aws ec2 describe-instances --query 'Reservations[*].Instances[*].PublicIpAddress' --filters "Name=tag:Project,Values=demoinstances" --output text >> inventory
```

### Run Ansible

```
ansible-playbook main-remote.yml -i inventory --private-key PATH_TO_KEY/remoteinstances.pem
``` 

