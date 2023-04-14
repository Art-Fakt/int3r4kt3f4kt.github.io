---
description: |
  Certipy is an offensive tool for enumerating and abusing Active Directory Certificate Services (AD CS). The find command is useful for enumerating AD CS certificate templates, certificate authorities and other configurations.

  Command Reference:
  ```
  PFX: administrator.pfx

  DC Server: 172.16.126.128
  ```
command: |
  certipy auth -pfx administrator.pfx -dc-ip 172.16.126.128
code: |
    By default, Certipy will try to extract the username and domain from the certificate (`-pfx`) for authentication via Kerberos.
    The NT hash and the credential cache (TGT) can be used for further authentication with other tools. If you're in a domain context on a Windows machine, you can use `-ptt` to inject the TGT into your current session.

    If the example above doesn't work in your case, you can specify the required parameters manually, such as the KDC IP, username, and domain. This can sometimes happen if the certificate doesn't contain information about the user (such as Shadow Credentials) or if the domain name cannot be resolved via DNS.

items:
  - PFX
services:
  - ADCS
  - LDAP
OS:
  - Windows
  - Linux
attack_types:
  - Enumeration
  - Authentication
references:
  - https://github.com/ly4k/Certipy
---
