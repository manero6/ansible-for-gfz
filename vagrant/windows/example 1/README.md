# Example 1
Playbook's tasks:
- change hostname
  - in use after a reboot
- create admins and users
    - with different group policies
  - "remove" default admin
    - not possible with Ansible's `win_user` module
    - not possible with a PS script
    - it's possible with PS to rename the default admin, activate it and set a password
- change keyboard layout to de_DE
  - logout required
- software installation with Chocolatey
- windows updates
  - reboot if needed
- Office 2019 standard installation
