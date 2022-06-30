[![CI](https://github.com/de-it-krachten/ansible-role-cron/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-cron/actions?query=workflow%3ACI)


# ansible-role-cron

Installs & manages cron

## Platforms

Supported platforms

- Red Hat Enterprise Linux 7<sup>1</sup>
- Red Hat Enterprise Linux 8<sup>1</sup>
- CentOS 7
- CentOS 8
- RockyLinux 8
- AlmaLinux 8<sup>1</sup>
- Debian 10 (Buster)
- Debian 11 (Bullseye)
- Ubuntu 18.04 LTS
- Ubuntu 20.04 LTS
- Ubuntu 22.04 LTS
- Fedora 35
- Fedora 36

Note:
<sup>1</sup> : no automated testing is performed on these platforms

## Role Variables
### defaults/main.yml
<pre><code>
# list of cron packages (see vars/ for OS specific file)
cron_packages: []

# name of the cron service (see vars/ for OS specific file)
cron_service: cron
</pre></code>

### vars/family-RedHat.yml
<pre><code>
cron_packages:
  - cronie

cron_service: crond
</pre></code>

### vars/family-Debian.yml
<pre><code>
cron_packages:
  - cron

cron_service: cron
</pre></code>



## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'cron'
  hosts: all
  vars:
  tasks:
    - name: Include role 'cron'
      include_role:
        name: cron
</pre></code>
