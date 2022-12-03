**Role hashivault**
===================

This is a ansible role to install a Hashicorp Vault server with integrated storage in an standalone server.  
For more information od this product visit https://www.vaultproject.io

*Requirements*
--------------

This role need the unzip package, if not installed in your OS, the role will install it.  
The recommended server features for lab are:

  - 2 CPUs
  - 8 GB of Memory
  - 100 GB of storge

*Role Variables*
----------------

This is a list of required and optinal variables and parameters for this role:

| **Parameter**                  | **Description**            | **Type** |     **Default**     |**Required**|
|--------------------------------|----------------------------|----------|:-------------------:|:----------:|
| hashivault__install_dir        | dir to install             |  string  | /opt/vault          |     no     |
| hashivault__config_dir         | dir to configure           |  string  | /etc/vault.d        |     no     |
| hashivault__version            | version of the server      |  number  | 1.12.1              |     yes    |
| hashivault__user               | service user               |  string  | vault               |     no     |
| hashivault__group              | service group              |  string  | vault               |     no     |
| hashivault__server_fqdn        | Name in fqdn               |  string  | vault.example.local |     yes    |
| hashivault__init_key_shares    | total keys seal            |  number  | 5                   |     no     |
| hashivault__init_key_threshold | keys for unseal            |  number  | 3                   |     no     |

*Dependencies*
--------------

There are no dependencies.

*Example Playbook*
------------------

This is an example of use role with optionals and required parameters:

```yaml
    - hosts: vault
      roles:
        - hashivault
      vars:
        hashivault__version: 1.12.1
        hashivault__server_fqdn: vault.example.local
```

*License*
---------

MIT

*Author Information*
--------------------

- Fernando Hernández San Felipe (ironwolphern@outlook.com)

