# network_config Role

## Description
This role renames the active network interface to net0 and displays information about the renamed interface.

## Usage
Include this role in your playbook.

## Example
```yaml
- hosts: servers
  roles:
    - network_config
