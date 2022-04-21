# Ansible roles for installing and configuring some applications

## Requirements

```bash
~$> ansible --version
ansible [core 2.12.4]
```

os: `Debian 11, CentOS 8`


## Roles
- **base**: install required packages, configuring iptables, etc
- **sshd**: configuring ssh
- **nginx**: installing and configuring nginx
- **php-fpm**: installing and configuring php-fpm

## Variables
Available variables are defined in `var` or `defaults` directories at role path. Host specific variables can be defined in `inventory` file.

## Playbook example

```
- name: PHP Application Server Setup
  hosts: all
  become: yes

  roles:
    - base
    - sshd
    - nginx
    - php-fpm
```

This role installs and configure PHP application server