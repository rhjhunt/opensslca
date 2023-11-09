============================
rhjhunt.opensslca.clientcert
============================

Version added: 1.0.0

.. contents::
    :local:
    :depth: 1

Synopsis
--------

- Create a private key, Certificate Signing Request (CSR) and certificate.

Parameters
----------

+----------------------------------+---------------+-----------------------------------------+
| Parameter                        |  Defaults     | Description                             |
+==================================+===============+=========================================+
| **clientcert_hostname**          |               | Host name of client.                     |
+----------------------------------+---------------+-----------------------------------------+
| **clientcert_country**           |               | Country 2 character abbreviation.       |
+----------------------------------+---------------+-----------------------------------------+
| **clientcert_email**             |               | Email for certificate.                  |
+----------------------------------+---------------+-----------------------------------------+
| **clientcert_state_or_province** |               | State or Provice for certificate.       |
+----------------------------------+---------------+-----------------------------------------+
| **clientcert_org**               |               | Organization for certificate.           |
+----------------------------------+---------------+-----------------------------------------+
| **clientcert_state**             | present       | If **present** certificate is created.  |
|                                  |               | If **absent** certificate is removed.   |
+----------------------------------+---------------+-----------------------------------------+

Examples
--------

.. code-block:: yaml

    - name: Certificate Authority
      hosts: rootca
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

Authors
~~~~~~~

- Jacob Hunt (@rhjhunt)
