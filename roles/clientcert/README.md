# rhjhunt.opensslca.clientcert

Create private and public keys for a client.

## Role Variables

`clientcert_hostname` : Host name of client.
`clientcert_country` : Country 2 character abbreviation.
`clientcert_email` : Email for certificate.
`clientcert_state_or_province` : State or Provice for certificate.
`clientcert_org` : Organization for certificate.
`clientcert_state` : If `present` creates certificate, if `absent` removes certificate.
`clientcert_eku` : List of extended key usage options.

## Example Playbook

Create a private key and public certificate for a server.

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
        clientcert_eku: ['serverAuth', 'clientAuth']
```
