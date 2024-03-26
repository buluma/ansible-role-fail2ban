# Ansible role [fail2ban](https://galaxy.ansible.com/ui/standalone/roles/buluma/fail2ban/documentation)

Install and configure fail2ban on your system.

|GitHub|Version|Issues|Pull Requests|Downloads|
|------|-------|------|-------------|---------|
|[![github](https://github.com/buluma/ansible-role-fail2ban/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-fail2ban/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-fail2ban.svg)](https://github.com/buluma/ansible-role-fail2ban/releases/)|[![Issues](https://img.shields.io/github/issues/buluma/ansible-role-fail2ban.svg)](https://github.com/buluma/ansible-role-fail2ban/issues/)|[![PullRequests](https://img.shields.io/github/issues-pr-closed-raw/buluma/ansible-role-fail2ban.svg)](https://github.com/buluma/ansible-role-fail2ban/pulls/)|[![Ansible Role](https://img.shields.io/ansible/role/d/buluma/fail2ban)](https://galaxy.ansible.com/ui/standalone/roles/buluma/fail2ban/documentation)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/buluma/ansible-role-fail2ban/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  become: true
  gather_facts: true

  roles:
    - role: buluma.fail2ban
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/buluma/ansible-role-fail2ban/blob/master/molecule/default/prepare.yml):

```yaml
---
- name: Prepare
  hosts: all
  gather_facts: false
  become: true

  roles:
    - role: buluma.bootstrap
    - role: buluma.epel
```

Also see a [full explanation and example](https://buluma.github.io/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/buluma/ansible-role-fail2ban/blob/master/defaults/main.yml):

```yaml
---
# defaults file for fail2ban

fail2ban_loglevel: INFO
fail2ban_logtarget: /var/log/fail2ban.log

fail2ban_ignoreself: "true"
fail2ban_ignoreips: "127.0.0.1/8 ::1"

# In seconds
fail2ban_bantime: 600
fail2ban_findtime: 600

fail2ban_maxretry: 5
fail2ban_destemail: root@localhost
fail2ban_sender: root@{{ ansible_fqdn }}

fail2ban_configuration: []
#  - option: loglevel
#    value: "INFO"
#    section: Definition

fail2ban_jail_configuration: []
#  - option: ignoreself
#    value: "true"
#    section: DEFAULT

# Path to directory containing filters to copy in filter.d
# fail2ban_filterd_path:
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-fail2ban/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | Version |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Ansible Molecule](https://github.com/buluma/ansible-role-bootstrap/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-bootstrap.svg)](https://github.com/shadowwalker/ansible-role-bootstrap)|
|[buluma.epel](https://galaxy.ansible.com/buluma/epel)|[![Ansible Molecule](https://github.com/buluma/ansible-role-epel/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-epel/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-epel.svg)](https://github.com/shadowwalker/ansible-role-epel)|

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-fail2ban/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|[Amazon](https://hub.docker.com/r/buluma/amazonlinux)|Candidate|
|[EL](https://hub.docker.com/r/buluma/enterpriselinux)|8|
|[Debian](https://hub.docker.com/r/buluma/debian)|all|
|[Fedora](https://hub.docker.com/r/buluma/fedora)|all|
|[Ubuntu](https://hub.docker.com/r/buluma/ubuntu)|all|

The minimum version of Ansible required is 2.12, tests have been done to:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them in [GitHub](https://github.com/buluma/ansible-role-fail2ban/issues)

## [Changelog](#changelog)

[Role History](https://github.com/buluma/ansible-role-fail2ban/blob/master/CHANGELOG.md)

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-fail2ban/blob/master/LICENSE)

## [Author Information](#author-information)

[Shadow Walker](https://buluma.github.io/)
