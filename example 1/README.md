# Example 1
Playbook's tasks:
- change hostname
  - in use after a reboot
- create admin and users
  - with different group policies
- remove default admin
  - not working with Ansible's `win_user` module
  - trying with a PS script
- change keyboard layout to de_DE
  - logout required
- software installation with Chocolatey
- windows updates
  - reboot if needed
- Office 2019 standard installation
