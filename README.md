Role Name
=========

A role to setup collection of Netflow data to dump files.

Supported collectors:
- pmacct
- nfdump

Requirements
------------

None.

Role Variables
--------------

TODO

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

None.

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
    - role: netflow-dumper
```

License
-------

CC0