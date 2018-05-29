ansible-sysward
===============

This role for Ansible will install and configure the [SysWard](https://sysward.com/) Agent on your system.

Requirements
------------

In order to use this role, you will need the following things:

- Ansible version 2.4 or higher
- A valid SysWard API key

Role Variables
--------------

The role has just one variable:

- `sysward_api_key` - This variable holds your SysWard API key.
It can be found on your [SysWard profile](https://sysward.com/profile).
Make sure to set/include this variable in your playbook or host/group vars files.
We recommend to store this key in an Ansible Vault file.

Dependencies
------------

This role currently has no dependencies.

Example Playbook
----------------

After you installed the role using the command `ansible-galaxy install treehouse.sysward`,
you can start using it in your playbook(s).

We recommend that you store your SysWard API key in an Ansible Vault file for security reasons.
If you've done so, your playbook could look something like this.

    - hosts: servers
      become: yes
      become_user: root

      pre_tasks:
        - name: Include Ansible Vault file
          include_vars: secrets.yml 

      roles:
        - { role: treehouse.sysward }

If you do not want to use an Ansible Vault file, you can also set the `sysward_api_key` variable
directly in your role definition, as shown below.

    - hosts: servers
      become: yes
      become_user: root

      roles:
         - { role: treehouse.sysward, sysward_api_key: APIKEY }

License
-------

This role is licensed under the MIT license. Also see the LICENSE file for the full license.

Author Information
------------------

This role is created and maintained by [TreeHouse B.V.](https://www.treehouse.nl/) from Rotterdam, The Netherlands.
We are an internet agency with a main focus on real estate and recruitment websites.
