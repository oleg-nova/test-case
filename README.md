
# About this playbook

This Ansible playbook performs the following actions:

1. Encrypting the second disk in the system (disk without root partition). Partition name specified in the [inventory.yml](inventory.yml).
1. Disabling C-state for all available CPUs.
1. Renaming the active network interface to "net0". 

# To run Ansible playbook

1. You must have [Ansible installed](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) ;)
1. Must have sudo root equivalent privileges on target hosts in [inventory.yml](inventory.yml)
1. Put correct ssh pubkey with filename "test_vm.pem" in current directory (filename & path specify in "ansible_ssh_private_key_file" variable in [inventory.yml](inventory.yml)).
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