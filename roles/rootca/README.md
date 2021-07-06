# rhjhunt.opensslca.rootca

Create Certificate Authority.

## Role Variables

`rootca_password` : Password for private key.
`rootca_country` : Country 2 character abbreviation.
`rootca_email` : Email for certificate.
`rootca_state_or_province` : State or Provice for certificate.
`rootca_org` : Organization for certificate.
`rootca_state` : If `present` certificate is created, if `absent` certificate is removed.

## Example Playbook

Create a private key and public certificate for a server.

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