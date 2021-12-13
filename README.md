# Slurm Ansible Basics

## About

[Learning Ansible with Slurm](https://edu.slurm.io/courses/ansible-basics)

[Source Code for project](https://github.com/Slurmio/ansible_base.git)

Stack:
- Vagrant - Vbox
- LEMP
- HTML/CSS
- Ansible

## How it works:

- Vagrant - Deploy to local machines - Ansible-node and LEMP-server
- LEMP - Linux, Nginx, MySQL, PHP on LEMP-server
- HTML/CSS - static files
- Ansible - installed on Ansible-node and play some books to install web

## How to use:
```bash
vagrant init
vagrant up
vagrant status

vagrant ssh controlnode
sudo apt install -y ansible
ansible-playbook playbook.yml -i hosts.ini
```


