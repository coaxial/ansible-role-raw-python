raw-python Ansible role
=========

This is a role to bootstrap Ansible by installing Python with a raw command. It
is only useful on hosts that don't have any python2 installed (i.e. Ubuntu)

Requirements
------------

None.

Role Variables
--------------

None.

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers
      gather_facts: false  # necessary because it can't collect facts without
        # python. The role collects facts after installing Python so they'll
        # be available throughout the rest of the tasks/roles.
      roles:
         - coaxial.raw-python

License
-------

GPLv3

Author Information
------------------

Coaxial<[64b.it](https://64b.it)>
