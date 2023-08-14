[![CI](https://github.com/de-it-krachten/ansible-role-cron/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-cron/actions?query=workflow%3ACI)


# ansible-role-cron

Installs & manages cron



## Dependencies

#### Roles
None

#### Collections
- community.general

## Platforms

Supported platforms

- Red Hat Enterprise Linux 7<sup>1</sup>
- Red Hat Enterprise Linux 8<sup>1</sup>
- Red Hat Enterprise Linux 9<sup>1</sup>
- CentOS 7
- RockyLinux 8
- RockyLinux 9
- OracleLinux 8
- OracleLinux 9
- AlmaLinux 8
- AlmaLinux 9
- SUSE Linux Enterprise 15<sup>1</sup>
- openSUSE Leap 15
- Debian 10 (Buster)<sup>1</sup>
- Debian 11 (Bullseye)
- Debian 12 (Bookworm)
- Ubuntu 20.04 LTS
- Ubuntu 22.04 LTS
- Fedora 37
- Fedora 38

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

### defaults/family-Debian.yml
<pre><code>
# List of required OS packages
cron_packages:
  - cron

# Service name
cron_service: cron
</pre></code>

### defaults/family-Suse.yml
<pre><code>
# List of required OS packages
cron_packages:
  - cronie

# Service name
cron_service: cron
</pre></code>

### defaults/family-RedHat.yml
<pre><code>
# List of required OS packages
cron_packages:
  - cronie

# Service name
cron_service: crond
</pre></code>




## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'cron'
  hosts: all
  become: "yes"
  tasks:
    - name: Include role 'cron'
      ansible.builtin.include_role:
        name: cron
</pre></code>
