---
description: |
  Certipy is an offensive tool for enumerating and abusing Active Directory Certificate Services (AD CS). The find command is useful for enumerating AD CS certificate templates, certificate authorities and other configurations.

  Command Reference:
  ```
  PFX: administrator_dc.pfx

  DC Server: 172.16.126.128
  ```
command: |
  certipy auth -pfx administrator_dc.pfx -dc-ip 172.16.126.128
code: |
    ESC1 is when a certificate template permits Client Authentication and allows the enrollee to supply an arbitrary Subject Alternative Name (SAN).

    For ESC1, It is also possible to specify only a UPN or a DNS. In the case where both a UPN and DNS are specified, 
    the `auth` command will ask you which identity to authenticate as.
items:
  - PFX
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