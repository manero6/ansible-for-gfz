# Example 4
Same as example 1 but with 3 VMs and no provisioning, Ansible must be run manually.

## Create the VMs
`vagrant up`

## Run Ansible
`ansible-playbook -i inventory playbook.yml`
