Role Name
=========

A brief description of the role goes here.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.


#Aws CLI

By default awscli is configured for root and admin users only:
```
awscli_credentials:
  - user: root
    group: root
    path: "/root/.aws"
  - user: admin
    group: admin
    path: "/home/admin/.aws"
```

aws credentials file contains by default only the [default] section. If you need to add more:
```
aws_additonal_credentials:
  - name: fooenv
    access_key: accesskey1
    secret_key: secret1
  - name: blaenv
    access_key: accesskey2
    secret_key: secret2
```

aws configs file contains by default only the [default] section. If you need to add more:
```
aws_additonal_configs:
  - name: default
    configs: {}
  - name: fooenv
    configs:
      region: eu-west-1
```

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
