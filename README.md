
# About this playbook

This Ansible playbook performs the following actions:

1. Encrypting the second disk in the system (disk without root partition). Partition name specified in the [inventory.yml](inventory.yml).
1. Disabling C-state for all available CPUs.
1. Switching CPU operation from power-saving mode to more productive mode.
1. Renaming the active network interface to "net0". 

# To run Ansible playbook

1. You must have [Ansible installed](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) ;)
1. Must have sudo root equivalent privileges on target hosts in [inventory.yml](inventory.yml)
1. Put correct ssh pubkey with filename "test_vm.pem" in current directory (filename & path specify in "ansible_ssh_private_key_file" variable in [inventory.yml](inventory.yml)).
1. Role [renaming_network_interface](./roles/renaming_network_interface/) using [mrlesmithjr.netplan role](https://galaxy.ansible.com/ui/standalone/roles/mrlesmithjr/netplan/)
   For install this role you must run
```shell
ansible-galaxy install -r requirements.yml
```
BEFORE next steps.
1. Use the command:
```shell
ansible-playbook -i inventory.yml run.yml
```
for run all roles 

or

```shell
 ansible-playbook -i inventory.yml run.yml --tags <role_name>

```
for run only specific role.

# Release Notes

v0.2 2025.01.14
  1. Used [mrlesmithjr.netplan role](https://galaxy.ansible.com/ui/standalone/roles/mrlesmithjr/netplan/) for renaming_network_interface role
  1. Used [community.crypto.luks_device module](https://docs.ansible.com/ansible/latest/collections/community/crypto/luks_device_module.html) for disk_encrypting role
  1. Added switching_cpu_mode role
  1. Lint playbook via ansible-lint and made fixes according ansible-lint results
     
v0.1 2024.12.31
  Initial Release
