# Registry
Install VMWare Harbor using Docker Compose. Tested on Debian 9.

## Note

## Description
This role sets up Harbor with Notary and Clair. Authentication is done against LDAP, default permissions are fairly restrictive.

## Configuration
| Name | Default value | Description |
| ---- | ------------- | ----------- |
| `harbor_host` | `registry.example.org` | FQDN of the registry |
| `notary_host` | `notary.example.org` | FQDN of notary |
| `harbor_mysql_root_pwd` | `False` | Root password of Harbor's MySQL database |
| `harbor_postgres_clair_pwd` | `False` | Root password of Clair's Postgres database |
| `harbor_default_admin_pwd` | `False` | Admin passwort of Harbor which is set during installation |
| `harbor_selfreg` | `off` | Allow self-registration in Harbor |
| `harbor_project_creation` | `adminonly` | Allow project creation for this usergroup |
| `harbor_version` | `1.4.0-rc1` | Harbor version to install |
| `harbor_version_to_nginx` | (see `default/main.tml`) | Mapping of Harbor version to Harbor nginx pod version |

## License
Apache 2.0, except for the patches in `files`, which follow upstream licensing.
