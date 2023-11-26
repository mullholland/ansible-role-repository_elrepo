# [Ansible role repository_elrepo](#repository_elrepo)

Add the elrepo to your system

|GitHub|Downloads|Version|
|------|---------|-------|
|[![github](https://github.com/mullholland/ansible-role-repository_elrepo/actions/workflows/molecule.yml/badge.svg)](https://github.com/mullholland/ansible-role-repository_elrepo/actions/workflows/molecule.yml)|[![downloads](https://img.shields.io/ansible/role/d/)](https://galaxy.ansible.com/mullholland/repository_elrepo)|[![Version](https://img.shields.io/github/release/mullholland/ansible-role-repository_elrepo.svg)](https://github.com/mullholland/ansible-role-repository_elrepo/releases/)|
## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/mullholland/ansible-role-repository_elrepo/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  become: true
  gather_facts: true
  # vars:
  #   example_var: "value"
  roles:
    - role: "mullholland.repository_elrepo"
```



## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/mullholland/ansible-role-repository_elrepo/blob/master/defaults/main.yml):

```yaml
---
# Install the ELRepo
# https://elrepo.org/tiki/HomePage

# ELRepo public key
repository_elrepo_key_url: " https://www.elrepo.org/RPM-GPG-KEY-elrepo.org"

# ELRepo install packages
repository_elrepo_version_map:
  RedHat:
    "7": "https://www.elrepo.org/elrepo-release-7.el7.elrepo.noarch.rpm"
    "8": "https://www.elrepo.org/elrepo-release-8.el8.elrepo.noarch.rpm"
    "9": "https://www.elrepo.org/elrepo-release-9.el9.elrepo.noarch.rpm"
  CentOS:
    "7": "https://www.elrepo.org/elrepo-release-7.el7.elrepo.noarch.rpm"
    "8": "https://www.elrepo.org/elrepo-release-8.el8.elrepo.noarch.rpm"
    "9": "https://www.elrepo.org/elrepo-release-9.el9.elrepo.noarch.rpm"
  Rocky:
    "8": "https://www.elrepo.org/elrepo-release-8.el8.elrepo.noarch.rpm"
    "9": "https://www.elrepo.org/elrepo-release-9.el9.elrepo.noarch.rpm"
  AlmaLinux:
    "8": "https://www.elrepo.org/elrepo-release-8.el8.elrepo.noarch.rpm"
    "9": "https://www.elrepo.org/elrepo-release-9.el9.elrepo.noarch.rpm"

repository_elrepo_version: "{{ repository_elrepo_version_map[ansible_distribution][ansible_distribution_major_version] }}"
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/mullholland/ansible-role-repository_elrepo/blob/master/requirements.txt).


## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://mullholland.net) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/mullholland/ansible-role-repository_elrepo/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/mullholland):

|container|tags|
|---------|----|
|[EL](https://hub.docker.com/r/mullholland/enterpriselinux)|all|

The minimum version of Ansible required is 2.10, tests have been done to:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them in [GitHub](https://github.com/mullholland/ansible-role-repository_elrepo/issues).

## [License](#license)

[MIT](https://github.com/mullholland/ansible-role-repository_elrepo/blob/master/LICENSE).

## [Author Information](#author-information)

[Mullholland](https://mullholland.net)
