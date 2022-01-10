rhpds-create-aws-sandbox
=========

An Ansible role to automate the creation of an AWS sandbox account through RHPDS.

Requirements
------------

An RHPDS account.

Role Variables
--------------

- `cfme_username`: Your RHPDS username.
- `cfme_password`: Your RHPDS Password.
- `service_catalog_id`: The ID of the Service Catalogue with the offering (RH Employee: Contact role authors for ID)
- `service_template_id`: The ID of the offering template (RH Employee: Contact role authors for ID)
- `allow_duplicate_sandboxes`: The default is `false` (not all accounts can set to true).
- `aws_sandbox_usage`: The default is `Training - Ad-hoc or exploratory`.

`cfme_username` and `cfme_password` can be provided via a Tower Custom Credential.

Example Playbook
----------------

```yaml
---
- name: Order a new AWS Sandbox Env through RHPDS
  hosts: localhost
  roles:
  - rhpds-create-aws-sandbox
```


License
-------

BSD

Author Information
------------------
 - Raed Soliman 
 - Nicolas Leiva 
