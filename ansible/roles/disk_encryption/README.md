# disk_encryption Role



## Description
This role encrypts the specified disk and the partition next to the root partition using LUKS.

## Variables
- `disk_name`: Name of the disk to encrypt (e.g., sdb).
- `luks_password`: Password for encrypt disk

## Usage
Include this role in your playbook

## Example
```yaml
- hosts: servers
  roles:
    - role: disk_encryption

## Specify variables
Specify the `disk_name` and `luks_password`  in inventory.

all:
  children:
    ubuntu:
      hosts:
        server-1:
          ansible_host: 
          ansible_user: 
          ansible_ssh_private_key_file: 
          disk_name: xvdb
          luks_password: password
