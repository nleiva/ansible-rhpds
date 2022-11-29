# RHPDS Sandbox request
[![Ansible Lint](https://github.com/nleiva/ansible-rhpds/actions/workflows/ansible-lint.yml/badge.svg)](https://github.com/nleiva/ansible-rhpds/actions/workflows/ansible-lint.yml)

Playbooks to request a Red Hat Product Demo System (RHPDS) Sandbox and update credentials on Ansible Controller.

## Running this

`controller_hostname` and `controller_oauthtoken` need to be provided as extra vars or Controller Credentials. Check out [Creating an OAuth 2 token](https://docs.ansible.com/automation-controller/4.0.0/html/userguide/applications_auth.html#add-tokens).

The Ansible Controller collection (or AWX) namespace needs to be referenced.

```yaml
  hosts: localhost
  collections:
    - ansible.controller
```

[Connect Private Automation Hub](https://console.redhat.com/ansible/automation-hub/token).

## Dependencies

All dependencies are included in the Collection [requirements.yml](collections/requirements.yml) and Role [requirements.yml](roles/requirements.yml) files.


## Playbooks

### custom_credential.yml

It will create a Custom Credential for Ansible Controller to store all the [inputs to create a Sandbox](https://github.com/sa-ne/rhpds-create-aws-sandbox#role-variables).

### create_sandbox.yml

It creates an RHPDS AWS Sandbox and updates its credentials in Controller. If you don't provide the custom credential as input, you can pass the variables as extra-vars.

```bash
ansible-playbook create_sandbox.yml --extra-vars "cfme_password='' cfme_username='' cfme_url='' service_catalog_id='' service_template_id=''"  -v
```