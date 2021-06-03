# RHPDS Sandbox request

Request a Red Hat Product Demo System (RHPDS) Sandbox

## Running this

`tower_hostname` and `tower_oauthtoken` need to be provided as extra vars or Tower Credentials. Check out [Creating an OAuth 2 token](https://docs.ansible.com/ansible-tower/latest/html/userguide/applications_auth.html#ug-tokens-auth-create).

The Ansible Tower collection (or AWX) namespace needs to be referenced.

```yaml
   hosts: localhost
   collections:
     - ansible.tower
```


## Dependencies

All dependencies are included in the Collection [requirements.yml](collections/requirements.yml) and Role [requirements.yml](roles/requirements.yml) files.