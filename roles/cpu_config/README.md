# cpu_config Role

## Description
This role disables C-state for all CPUs and switches the CPU operation to performance mode.

AWS not all EC2 allowed, https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/processor_state_control.html
AWS/KVM not allowed power modules, only baremetal

## Usage
Include this role in your playbook.

## Example
```yaml
- hosts: servers
  roles:
    - cpu_config