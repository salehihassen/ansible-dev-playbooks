# Dev Setup Ansible Playbooks



## Instances I used this


Dec 23 2025 - automate setting up x11 forwarding support for one of my personal servers
```
ansible-playbook -i inventory/hosts.yml playbooks/site.yml --ask-become-pass --tags x11
```
