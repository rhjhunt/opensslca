# Ansible Collection - rhjhunt.opensslca

Ansible Collection to create an OpenSSL Certificate Authority and sign client certificates.

## Ansible Version Compatibility

The collection was tested with Ansible versions **>=2.9.10**.

## Requirements

The below Python module requirements are needed on the host that executes this collection.

* Either cryptography >= 1.2.3
* Or pyOpenSSL

## Installing The Collection

You can install the collection with the Ansible Galaxy CLI:

```terminal
ansible-galaxy collection install rhjhunt.opensslca
```

You can also include it in a _requirements.yml_ file and install it with
`ansible-galaxy collection install -r requirements.yml`, using the format:

```yaml
---
collections:
  - name: rhjhunt.opensslca
```

## Included Content

### Roles

Name | Description
--- | ---
[rhjhunt.openssla.rootca](docs/rhjhunt.opensslca.rootca_role.rst) | Create a Root Certificate Authority
[rhjhunt.openssl.clientcert](docs/rhjhunt.opensslca.clientcert_role.rst) | Create and sign client servers with the root CA

## Examples

### Certificate Authority

You can use the following example to create a Certificate Authority.

```yaml
- name: Certificate Authority
  hosts: localhost
  become: yes
  roles:
    - role: rhjhunt.opensslca.rootca
      vars:
        rootca_country: US
        rootca_email: jdoe@example.com
        rootca_state_or_province: CA
        rootca_org: Example Inc.
        rootca_password: changeme
```

### Client Certificate

You can use the following example to create a client certificate and sign the certificate.

```yaml
- name: Certificate Authority
  hosts: localhost
  become: yes
  roles:
    - role: rhjhunt.opensslca.clientcert
      vars:
        clientcert_country: US
        clientcert_email: jdoe@example.com
        clientcert_state_or_province: CA
        clientcert_org: Example Inc.
        rootca_password: changeme
        clientcert_hostname: server.example.com
```
