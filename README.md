# Ansible Playbook for Server Preparation

## Description
This playbook prepares the server by encrypting disks, configuring CPU settings, renaming the network interface, and gathering system information.

## Usage
- Clone the repository
- Update the inventory file with your server details:
```shell
ansible_host
ansible_user
ansible_ssh_private_key_file
disk_name
luks_password

- Run the playbook using the command:

```shell
ansible-playbook -i inventory.yml playbook.yml