# Ansible for GFZ

Showcasing a few simple Ansible playbooks.

Using Vagrant to automate the tedious and time-consuming tasks.

## How-To
### Vagrant
#### create a VM and execute Ansible Tasks
`vagrant up`

#### only create a VM
`vagrant up --no-provision`

#### execute Ansible Tasks on an already created VM
`vagrant up --provision`

#### destroy a VM
`vagrant destroy`

---

## VMs
### Vagrant Boxes
#### Windows
- [x] Peru's Windows 10 image
  - <https://app.vagrantup.com/peru/boxes/windows-10-enterprise-x64-eval>
  - LibVirt + VirtualBox
- [ ] Microsoft's Windows 10 for Edge
  - <https://app.vagrantup.com/Microsoft/boxes/EdgeOnWindows10>
  - VirtualBox

#### Linux
TODO

#### macOS
TODO (unlikely...)

### QEMU/KVM/LibVirt
#### macOS
- https://github.com/kholia/OSX-KVM
