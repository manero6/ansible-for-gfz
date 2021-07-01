---
title: Ansible for GFZ
author: Federico Togni
date: "31.05.2021"
theme:
---

# Overview

- The way to automatisation
  - on Spot
  - Remote Desktop Management
  - Remote Management
  - Configuration Management Software
- Ansible
  - example inventory
  - example ad hoc
  - example playbook
- Package Manager
  - Linux example
  - Chocolatey for Windows
  - Homebrew for macOS
- Vagrant
  - why Vagrant?
  - how-to Vagrant
- Ansible Tower/AWX

# The Way to Automatisation

# The Way to Automatisation
## On Site

- go there and execute the tasks

# The Way to Automatisation
## Remote Desktop Management
## for example ScreenConnect
- set up a connection (Server-Client)
- execute the tasks as if I were there, thanks to the remote session

# The Way to Automatisation
## Remote Management
## SSH
- ssh USER @ HOST
  - sudo apt update && sudo apt upgrade
- ssh USER @ HOST 'sudo apt update && sudo apt upgrade'

# The Way to Automatisation
## Remote Management
## WinRM
- Enter-PSSession -ComputerName HOST -Credential USER
  - Get-ChildItem C:\\
- Invoke-Command -ComputerName HOST -credential USER -ScriptBlock { Get-ChildItem C:\\ }

# The Way to Automatisation
## Configuration Management Software
### Server-Client Software (aka Server-Agent)
#### for Example OPSI

- go to OPSI-server
  - select the tasks
  - select the end-devices
- send the tasks to the specified end-devices (to OPSI-client)
- OPSI-client executes the tasks and reports back

# The Way to Automatisation
## Configuration Management Software
### Clientless Software (aka Agentless)
#### Ansible

- run ansible and specify
  - what tasks
  - what end-devices
- ansible reach the end-devices
- the end-devices execute the tasks
- Ansible checks the results and reports back


# Ansible

# Ansible
## Inventory
- a file (INI format by default) that describes Hosts and Groups in Ansible.

### Example inventory

```ini
[section180]
192.168.121.181
192.168.121.182

[section190]
192.168.121.191
192.168.121.192

[all:vars]
ansible_user=username
ansible_password=password
ansible_connection=winrm
```

# Ansible
## Example playbook

```yaml
- hosts: all
  
  tasks:

  - name: Shutting down
    win_command:
      shutdown /s /t 60 /c "Shutting down your device"
```

# Ansible
## Example ad hoc

`ansible -f20 all -i inventory -m win_command 'shutdown /s /t 60 /c "Shutting down your device"'`

# Package Manager

# Package Manager
## Linux Example
### APT - Debian/Ubuntu
- `sudo apt install firefox`

### DNF - Fedeora/CentOS/RedHat
- `sudo dnf install firefox`

### ZYPPER - OpenSUSE
- `sudo zypper install firefox`

### PACMAN - ArchLinux/Manjaro
- `sudo pacman -S firefox`

# Package Manager
## Windows and macOS
### Chocolatey - Windows
- `choco install firefox`

### Homebrew - macOS
- `brew install firefox`

# Vagrant

# Vagrant
## why Vagrant?

- Vagrant automates the deployment and configuration of virtual machines
  - declare the VM details in a file (Vagrantfile)
  - automatically deploy Windows 10 VMs with just one command
    - `vagrant up`
  - automatically set up and run Ansible on the created VMs as part of the VM deployment

## why peru/windows10 Vagrant Box?

- recent images (monthly updates)
- WinRM already activated
- VirtualBox + libvirt compatibility

# Vagrant
## how-to Vagrant

- change directory to where a Vagrantfile is
  - `cd /path/to/Vagrantfile`
- create a VM (with provisioning, if present in the Vagrantfile)
  - `vagrant up`
- stop the VM
  - `vagrant halt`
- remove the VM
  - `vagrant destroy`
- create a VM (with no provisioning)
  - `vagrant up --no-provision`
- provision an already created vm
  - `vagrant up --provision`
  - `vagrant provision`

# Ansible Tower

# Ansible Tower
## Ansible Tower

- https://www.ansible.com/products/tower

## AWX
- Open-Source development Version of Ansible Tower
- https://github.com/ansible/awx
