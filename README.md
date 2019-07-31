Ansible Role: NFS Server
=========

Ansible role to install and configure NFS server.

Through a simple list, you can indicate the directories to share, their NFS options, and the network that have access to them.

Easy use of IPv6 addresses, brackets are added automatically when necessary using the `ipwrap` filter.

Requirements
------------

#### Ansible version:
Ansible \>= 2.7

#### Python libraries:
- `netaddr` to use IP address filter.
- `jmespath` to use JSON query filter.


Role Variables
--------------

```yaml
exports:    # Full list of directories to export

  - path: /var/helloWorld  # Complete path to the first directory to share
    parameters: rw,secure,sync,no_subtree_check,no_root_squash  # NFS sharing options
    network: 192.168.0.0/255.255.255.0 	# Network allowed to access to this directory

  - path: /var/foo
    parameters: rw,secure,sync
    network: 192.168.88.0/255.255.255.0

  - path: /var/shared
    parameters: rw,secure,sync
    network: 200:20:1::/64
```

Dependencies
------------

It doesn't depend on other roles.

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
    - role: ansible-role-nfs-server
      exports:
        - path: /var/shared
          parameters: rw,secure,sync
          network: 200:20:1::/64
```

License
-------

(c) Universidad de la República (UdelaR), Red de Unidades Informáticas de la UdelaR en el Interior.
licenced under GPL-v3

Author Information
------------------

[@santiagomr](https://github.com/santiagomr)
[@UdelaRInterior](https://github.com/UdelaRInterior)
https://proyectos.interior.edu.uy/
