# RHPDS Sandbox request

Playbooks to request a Red Hat Product Demo System (RHPDS) Sandbox and update credentials on Ansible Tower.

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


## Playbooks

### custom_credential.yml

It will create a Custom Credential for Ansible Tower to store all the [inputs to create a Sandbox](https://github.com/sa-ne/rhpds-create-aws-sandbox#role-variables).

### create_sandbox.yml

It creates a RHPDS AWS Sandbox and updates its credentials in Tower. If you don't provide the custom credential as input, you can pass the variables as extra-vars.

```bash
ansible-playbook create_sandbox.yml --extra-vars "cfme_password='' cfme_username='' cfme_url='' service_catalog_id='' service_template_id=''"  -v
```