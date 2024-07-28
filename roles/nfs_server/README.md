# NFS Server Role

## Overview

This Ansible role configures an NFS server. It installs the necessary NFS server packages, adjusts minimal configuration settings, starts the NFS daemon upon initial setup, or restarts it in case of any changes to the configuration of an already running NFS server. The role supports both Ubuntu and AlmaLinux.

## Structure

- **defaults/main.yml**: Default variables for the role.
- **handlers/main.yml**: Handlers to restart the NFS service.
- **tasks/main.yml**: Main tasks for setting up the NFS server.
- **templates/exports.j2**: Template for the NFS exports configuration.
- **meta/main.yml**: Role dependencies and metadata.

## Variables

- **nfs_exports**: List of exports to be configured in `/etc/exports`.

### Example nfs_exports

```yaml
nfs_exports:
  - "/srv/nfs/data *(rw,sync,no_root_squash)"

### Example playbook 

```yaml
- name: Configure NFS Server
  hosts: nfs_server
  become: yes
  roles:
    - role: nfs_server

### Example Inventory File

```yaml
all:
  children:
    nfs_server_group:
      hosts:
        nfs-server1:
          ansible_host: 192.168.1.10
  vars:
    ansible_user: your_ssh_user