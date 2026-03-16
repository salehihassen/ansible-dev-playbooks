# Dev Setup Ansible Playbooks

## Pre-reqs

Ansible installed on the Control node. Managed nodes are linux machines with SSH enabled.

## Setup - Local

- Clone this repo on the target machine
- Install Ansible on the target machine
  ```
  sudo apt-add-repository ppa:ansible/ansible && sudo apt install ansible
  ```
- Run the ansible playbook.
  ```
  ansible-playbook -i 'localhost,' -c local -K playbooks/site.yml   -e 'roles_to_run=[editors]'
  ```

## Setup - Remote

- Install OpenSSH server on the target machine
  ```
  sudo apt install openssh-server
  ```
- Add managed nodes to [inventory/hosts.yml](./inventory/hosts.yml)
- Add hostvars to [/inventory/host_vars/](./inventory/host_vars/)

## Roles

### Editors

Install stock editors of choice: vs code, cursor, vim, neovim, and/or zed

Example:
```
ansible-playbook -i 'localhost,' -c local -K playbooks/site.yml \
  -e 'roles_to_run=[editors]'
```

### C Dev setup

Install C development environment: gcc, clang, make, gdb, valgrind, bear, etc..

### Git setup

Install Git and Git LFS.

### Tmux setup

Install Tmux with preferred config.

### X11 setup

Enable X11 forwarding for remote access to GUIs.

## Appendix
### Instances I used this

Mar 16 2026 - install UV python on my laptop, a bit overkill but may become a pre-req step to another installs.

March 10-15 2026 - install editors I'm interested in on my laptop.

Dec 23 2025 - automate setting up x11 forwarding support for one of my personal servers
```
ansible-playbook -i inventory/hosts.yml playbooks/site.yml --ask-become-pass --tags x11
```
