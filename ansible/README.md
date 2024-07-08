# Ansible Playbook for Server Preparation

## Description
This playbook prepares the server by encrypting disks, configuring CPU settings, renaming the network interface, and gathering system information.

## Usage
- Clone the repository and navigate to the `ansible-playbooks` directory.
- Update the inventory file with your server details.
- Run the playbook using the command:

```shell
ansible-playbook -i inventory.yml playbook.yml