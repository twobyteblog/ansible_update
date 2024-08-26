# Ansible Role: OS Updates

Ansible role which updates the host's operating system. This role supports CentOS, Fedora, Debian and Windows operating systems.

## Requirements

This role requires root access to the host system. Specify it globally, or add it to your playbook (example below).

```
- hosts: hosts
  roles:
    - role: ansible_update
      become: yes
```

## Installation

To use this role, clone the respository into the directory containing your other Ansible roles.

```
git clone https://github.com/inundationca/ansible_update.git
```

Add it to a new or existing playbook with the following play.

- 'serial' indicates that only 6 hosts will be updated at one time.
- 'max_fail_percentage' indicates that if more than 49% of the hosts fail to update, Ansible will stop.

```
- name: Performing update on host(s)
  hosts: all
  max_fail_percentage: 49
  serial: 6
  roles:
    - role: ansible_update
```



