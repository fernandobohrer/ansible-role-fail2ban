# Ansible Role: fail2ban

An opinionated Ansible role that deploys and configures [Fail2Ban][01] to protect your machines' [OpenSSH][02] service.

## 🚀 Motivation

From Fail2Ban's [GitHub repository][01]:

*Fail2Ban scans log files like `/var/log/auth.log` and bans IP addresses conducting too many failed login attempts. It does this by updating system firewall rules to reject new connections from those IP addresses, for a configurable amount of time.*

This role deploys [Fail2Ban][01] and its dependencies and configures the solution to protect your machines' [OpenSSH][02] service.

## 📑 Role Variables

Check [here][03].

## 🧰 Dependencies

None.

## ⚡ Quick start

An example of how integrate this role to an Ansible playbook can be found here:

```yml
---
- name: Deploy fail2ban
  hosts: all
  become: true
  gather_facts: true
  roles:
    - fernandobohrer.fail2ban
```

## 📋 Usage

To get the status associated with the `sshd` jail:

```bash
sudo fail2ban-client status sshd
```

To unban an IP address:

```bash
sudo fail2ban-client set sshd unbanip 203.0.113.1
```

## ⚙️ Compatibility

This role was tested on and is confirmed to work with the following Linux distributions:

- `Debian 12`
- `Ubuntu 22.04`
- `Ubuntu 24.04`

Details can be found in the [Molecule][04] scenarios available in the `molecule` folder.

## ⚠️ Warning

This Ansible role was tested on the above mentioned Linux distributions considering their default configuration. Your environment might have a different configuration or requirements which might conflict with the options that this role uses.

With the above in mind, it is **imperative** that you familiarize yourself with what this role does and test it on non-production machines **before** applying it to machines in a production environment.

## 📝 License

This project is licensed under the terms of the [MIT license][05].

[01]: https://github.com/fail2ban/fail2ban
[02]: https://www.openssh.com/
[03]: defaults/main.yml
[04]: https://github.com/fernandobohrer/ansible-molecule-scenarios
[05]: /LICENSE
