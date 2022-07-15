# [repository_elrepo](#repository_elrepo)

|GitHub|GitLab|
|------|------|
|[![github](https://github.com/mullholland/ansible-role-repository_elrepo/workflows/Ansible%20Molecule/badge.svg)](https://github.com/mullholland/ansible-role-repository_elrepo/actions)|[![gitlab](https://gitlab.com/mullholland/ansible-role-repository_elrepo/badges/main/pipeline.svg)](https://gitlab.com/mullholland/ansible-role-repository_elrepo)|

description

## [Role Variables](#role-variables)

These variables are set in `defaults/main.yml`:
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
  CentOS:
    "7": "https://www.elrepo.org/elrepo-release-7.el7.elrepo.noarch.rpm"
    "8": "https://www.elrepo.org/elrepo-release-8.el8.elrepo.noarch.rpm"
  Rocky:
    "8": "https://www.elrepo.org/elrepo-release-8.el8.elrepo.noarch.rpm"
  AlmaLinux:
    "8": "https://www.elrepo.org/elrepo-release-8.el8.elrepo.noarch.rpm"
  Amazon:
    "2": "https://www.elrepo.org/elrepo-release-7.el7.elrepo.noarch.rpm"

repository_elrepo_version: "{{ repository_elrepo_version_map[ansible_distribution][ansible_distribution_major_version] }}"
```


## [Example Playbook](#example-playbook)

This example is taken from `molecule/default/converge.yml` and is tested on each push, pull request and release.
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





## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/mullholland):

-   [centos7](https://hub.docker.com/r/mullholland/docker-molecule-centos7)
-   [centos-stream8](https://hub.docker.com/r/mullholland/docker-molecule-centos-stream8)
-   [ubi8](https://hub.docker.com/r/mullholland/docker-molecule-ubi8)
-   [rockylinux8](https://hub.docker.com/r/mullholland/docker-molecule-rockylinux8)
-   [almalinux8](https://hub.docker.com/r/mullholland/docker-molecule-almalinux8)

The minimum version of Ansible required is 2.10, tests have been done to:

-   The previous versions.
-   The current version.



## [Exceptions](#exceptions)

Some variations of the build matrix do not work. These are the variations and reasons why the build won't work:

| variation                 | reason                 |
|---------------------------|------------------------|
| Ubuntu* | repo only supports RedHat/CentOS Server |
| Debian* | repo only supports RedHat/CentOS Server |
| Fedora* | repo only supports RedHat/CentOS Server |
| centos-stream9 | repo not supported |
| amazonlinux | repo not supported |


If you find issues, please register them in [GitHub](https://github.com/mullholland/ansible-role-repository_elrepo/issues)

## [License](#license)

MIT


## [Author Information](#author-information)

[Mullholland](https://github.com/mullholland)

## [Special Thanks](#special-thanks)

Template inspired by [Robert de Bock](https://github.com/robertdebock)
