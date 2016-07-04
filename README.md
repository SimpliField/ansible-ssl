SSL
=========

Setup ssl certificates

Requirements
------------

Need ansible 2+

Role Variables
--------------

```yaml
ssl_common_name: "myCert"
ssl_path: "/etc/ssl/myCert"
ssl_path_owner: "www"
ssl_path_group: "www"
ssl_privkey_data: |
  -----BEGIN PRIVATE KEY-----
  …
  -----END PRIVATE KEY-----
ssl_cert_data: |
  -----BEGIN CERTIFICATE-----
  …
  -----END CERTIFICATE-----
ssl_generate_dh_param: false
ssl_dhparam_size: "2048"
```

Dependencies
------------

- [SimpliField.packages](https://galaxy.ansible.com/SimpliField/packages/)
- [SimpliField.path](https://galaxy.ansible.com/SimpliField/path/)

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
  - role: username.rolename
    ssl_common_name: MyCert
    ssl_path_owner: root
    ssl_path_group: root
```

License
-------

BSD
