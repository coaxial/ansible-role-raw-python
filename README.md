raw-python Ansible role
=========

[![Build Status](https://travis-ci.org/coaxial/ansible-role-raw-python.svg?branch=master)](https://travis-ci.org/coaxial/ansible-role-raw-python)

This is a role to bootstrap Ansible by installing Python with a raw command. It
is only useful on hosts that don't have any python2 installed by default.

Requirements
------------

None.

Role Variables
--------------

name | purpose | possible values
---|---|---
`rawpython__os_family` | select the right install command | `Debian` (for Debian/Ubuntu)
`rawpython__pkg_name` | Override the Python package name for your system (not usually necessary)

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers
      gather_facts: false  # necessary because it can't collect facts without
      # python. The role collects facts after installing Python so they'll be
      # available throughout the rest of the tasks/roles.
      vars:
        rawpython__os_family: Debian  # Can't use ansible facts because of the
        # gather_facts: false above
      roles:
         - coaxial.raw-python
         - ...

License
-------

GPLv3

Author Information
------------------

Coaxial<[64b.it](https://64b.it)>
