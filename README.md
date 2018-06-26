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
| `harbor_version` | `1.5.1` | Harbor version to install |
| `harbor_version_major` | `1.5.0` | Harbor major version to install, needed for download url |
| `harbor_installer_type` | `offline` | Harbor normally provides two installers, `online` would be sufficient. However, packaging of `online` sometimes lags the release date by multiple weeks, so we default to `offline` to be sure. |
| `harbor_job_workers` | `10` | How many job workers to use? |
| `harbor_auth_type` | `db_auth` | Which auth type to use (`db_auth` or `ldap_auth`) |
| `harbor_ldap_url` | `ldaps://ldap.example.org` | LDAP server URL |
| `harbor_ldap_need_searchdn` | `False` | Do we need a special search user? |
| `harbor_ldap_search_dn` | `uid=searchuser,ou=people,dc=example,dc=org` | DN of the search user |
| `harbor_ldap_search_password` | `"Super$ecret` | Passwort of the search user |
| `harbor_ldap_base_dn` | `ou=people,dc=example,dc=org` | Base DN for users |
| `harbor_ldap_filter` | `(objectClass=person)` | Filter (e.g. object class) for users |
| `harbor_ldap_userid_attribute` | `uid` | Which attribute contains the user id? |
| `harbor_ldap_timeout` | `5` | LDAP query timeout |
| `harbor_ldap_verify_certificate` | `True` | When using LDAPS, validate the certificate? |
| `harbor_ldap_group_base_dn` | `ou=group,dc=example,dc=org` | Base DN of groups|
| `harbor_ldap_group_filter` | `objectclass=group` | Filter (e.g. object class) for groups |
| `harbor_ldap_groupid_attribute` | `cn` | Which attribut contains the group id? |

## License
Apache 2.0, except for the patch in `files`, which follows upstream licensing.
