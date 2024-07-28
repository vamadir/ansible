# NFS Client Role

## Overview

This Ansible role configures an NFS client. It installs the required packages on the client side, mounts the network NFS resource using a systemd unit, and provides an automount option for the unit. The role supports both Ubuntu and AlmaLinux.

## Structure

- **defaults/main.yml**: Default variables for the role.
- **handlers/main.yml**: Handlers to reload systemd and restart the NFS mount service.
- **tasks/main.yml**: Main tasks for setting up the NFS client.
- **templates/nfs-mount.service.j2**: Template for the systemd mount unit file.
- **meta/main.yml**: Role dependencies and metadata.

## Variables

- **nfs_server**: NFS server hostname or IP address.
- **nfs_mount_point**: Mount point on the client.
- **nfs_export**: Export path on the NFS server.

### Example

```yaml
nfs_server: "nfs.example.com"
nfs_mount_point: "/mnt/nfs"
nfs_export: "/srv/nfs/data"

### Example playbook 

```yaml
- name: Configure NFS Client
  hosts: nfs_client
  become: yes
  roles:
    - role: nfs_client

### Example Inventory File

```yaml
all:
  children:
    nfs_client_group:
      hosts:
        nfs-client1:
          ansible_host: 192.168.1.20
        nfs-client2:
          ansible_host: 192.168.1.21
  vars:
    ansible_user: your_ssh_user