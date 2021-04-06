# Ansible Role: MOTD (Message Of The Day)

[![CI](https://github.com/lucab85/ansible-role-motd/actions/workflows/ci.yml/badge.svg)](https://github.com/lucab85/ansible-role-motd/actions/workflows/ci.yml)

Install and configure the MOTD (Message Of The Day) on Fedora/Centos/RHEL7/8, Debian/Ubuntu and Amazon target.


## Requirements

No special requirements; note that this role requires root access, so either run it in a playbook with a global `become: yes`, or invoke the role in your playbook like:

    - hosts: all
      roles:
        - role: lucab85.ansible_role_motd
          become: yes

## Role Variables

Available variables are listed along with default values in [defaults/main.yml](defaults/main.yml) file.


## Dependencies

None.

## Example Playbook

    - hosts: all
      become: yes
      roles:
        - lucab85.ansible_role_motd

Customize variables in `vars/main.yml`

		motd_info: |
		  FQDN: {{ ansible_facts.fqdn }}
		  Distribution: {{ ansible_facts.distribution }} {{ ansible_facts.distribution_version }} {{ ansible_facts.distribution_release }}
		  CPUs: {{ ansible_facts.processor_vcpus }}
		  RAM: {{ (ansible_facts.memtotal_mb / 1000) | round(1) }}GB

## License

MIT / BSD

## Author Information

This role was created in 2021 by [Luca Berton](https://www.lucaberton.it/).
