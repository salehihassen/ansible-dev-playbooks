# Dev Setup Ansible Playbooks

## Pre-reqs

Ansible installed on the Control node. Managed nodes are linux machines with SSH enabled.

## Setup

- Add managed nodes to [inventory/hosts.yml](./inventory/hosts.yml)
- Add hostvars to [/inventory/host_vars/](./inventory/host_vars/)

## Roles

### Editors

Install editors of choice: vs code, cursor, vim, neovim, and/or zed

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


Dec 23 2025 - automate setting up x11 forwarding support for one of my personal servers
```
ansible-playbook -i inventory/hosts.yml playbooks/site.yml --ask-become-pass --tags x11
```
