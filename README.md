Role Name
=========

A role to setup collection of Netflow data to dump files.

Supported collectors:
- pmacct
- nfdump
- flow-tools

Requirements
------------

None.

Role Variables
--------------

* `netflow_dumper_conf_dir`: (Default: /opt/netflow-dumper/conf) Where to store persistent conf files for services
* `netflow_dumper_rotate_interval`: (Default: 900) How often to rotate netflow dump files
* `netflow_dumper_listen_port`: (Default: unset) Listening address
* `netflow_dumper_listen_address`: (Default: unset) Listening port
* `netflow_dumper_instances`: (Default: []) Collector instances, a host may have many. See defaults.yaml for examples.

Pmacct:
* `netflow_dumper_pmacct_filename`: (Default: "file-%Y%m%d-%H%M%S.txt") Default dump file's basename
* `netflow_dumper_pmacct_subdir_hierarchy`: (Default: "%Y/%m/%d") Default subdirectory hierarchy 

Ndfump:
* `netflow_dumper_nfdump_subdir_hierarchy`: (Default: 1) See 'man nfcapd'

Flow-Tools:
* `netflow_dumper_flow_tools_compression`: (Default: 1) See 'man flow-capture' (-z)
* `netflow_dumper_flow_tools_expire_size`: (Default: unset) See 'man flow-capture' (-E)


Dependencies
------------

None.

Example Playbook
----------------

Example inventory:

```yaml
all:
  hosts:
    example.com:
      netflow_dumper_instances:
        - flows_dir: "{{ inventory_hostname }}"
	  collector: pmacct
	  listen_port: 2055
	  rotate_interval: 900
	  
```    

Example playbook:

```yaml
- hosts: servers
  roles:
    - role: netflow-dumper
```

License
-------

CC0