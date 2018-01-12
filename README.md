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
# Your csr/.key file
ssl_privkey_data: |
  -----BEGIN PRIVATE KEY-----
  …
  -----END PRIVATE KEY-----
# Your crt
ssl_cert_data: |
  -----BEGIN CERTIFICATE-----
  …
  -----END CERTIFICATE-----
# Intermediate crt (The second part of the pem file)
ssl_intermediate_cert_data: |
  -----BEGIN CERTIFICATE-----
  …
  -----END CERTIFICATE-----
ssl_generate_dh_param: false
ssl_dhparam_size: "2048"
```

Dependencies
------------

- [GROG.package](https://galaxy.ansible.com/GROG/package/)
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
