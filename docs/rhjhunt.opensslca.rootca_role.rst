========================
rhjhunt.opensslca.rootca
========================

Version added: 1.0.0

.. contents::
    :local:
    :depth: 1

Synopsis
--------

- Create a Certificate Authority.

Parameters
----------

+----------------------------------+---------------+-----------------------------------------+
| Parameter                        |  Defaults     | Description                             |
+==================================+===============+=========================================+
| **rootca_password**              |               | Password of CA                          |
+----------------------------------+---------------+-----------------------------------------+
| **rootca_country**               |               | Country 2 character abbreviation.       |
+----------------------------------+---------------+-----------------------------------------+
| **rootca_email**                 |               | Email for certificate.                  |
+----------------------------------+---------------+-----------------------------------------+
| **rootca_state_or_province**     |               | State or Provice for certificate.       |
+----------------------------------+---------------+-----------------------------------------+
| **rootca_org**                   |               | Organization for certificate.           |
+----------------------------------+---------------+-----------------------------------------+
| **rootca_state**                 | present       | If **present** certificate is created.  |
|                                  |               | If **absent** certificate is removed.   |
+----------------------------------+---------------+-----------------------------------------+

Examples
--------

.. code-block:: yaml

    - name: Certificate Authority
      hosts: rootca
      become: yes
      roles:
        - role: rhjhunt.opensslca.rootca
          vars:
            rootca_country: US
            rootca_email: jdoe@example.com
            rootca_state_or_province: CA
            rootca_org: Example Inc.
            rootca_password: changeme

Authors
~~~~~~~

- Jacob Hunt (@rhjhunt)