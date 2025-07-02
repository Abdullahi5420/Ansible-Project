# Ansible Project: Connect Ubuntu Controller to Red Hat VM

## Overview

This project demonstrates how to use **Ansible** on Ubuntu to connect to a **Red Hat VM** via SSH and run automation tasks.

##  Setup

- **Controller**: Ubuntu with Ansible installed
- **Target**: Red Hat Server running in VMware

## ⚙Inventory File (hosts.ini)

ini
[redhat]
192.168.100.66 ansible_user=ali ansible_ssh_pass=Ali@12345

## Playbook (test.yml)
- name: Test connection to Red Hat VM
  hosts: redhat
  gather_facts: yes
  tasks:
    - name: Show OS name
      debug:
        var: ansible_distribution
## How to Run
ansible-playbook -i hosts.ini test.yml --ask-become-pass
