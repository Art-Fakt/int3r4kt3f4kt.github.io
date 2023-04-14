---
description: |
  Certipy is an offensive tool for enumerating and abusing Active Directory Certificate Services (AD CS). The req command is useful for requesting, retrieving, and renewing certificates. Which is useful for exploiting serveral certifacte templating vulnerabilities like ESC1, ESC2, etc.

  Command Reference:
  ```
  User: John@corp.local

  Password: Passw0rd

  Target user: Jane

  domain: corp.local

  ```
command: |
  certipy shadow auto -username John@corp.local -p Passw0rd -account Jane

code: |
    In short, the Shadow Credentials attack is performed by adding a new "Key Credential" to the target account. The Key Credential can then be used with the PKINIT Kerberos extension for authentication.

    Certipy's `shadow` command has an `auto` action, which will add a new Key Credential to the target account, authenticate with the Key Credential to retrieve the NT hash and a TGT for the target, and finally restore the old Key Credential attribute.
    
    This action is useful if you just want the NT hash or TGT for further authentication. It is possibly to manually add, authenticate, and delete the Key Credential, if desired. See the usage or [blog post](https://research.ifcr.dk/34d1c26f0dc6) for more information.

items:
  - Username
  - Password
services:
  - LDAP
  - ADCS
OS:
  - Windows
  - Linux
attack_types:
  - Exploitation
references:
  - https://github.com/ly4k/Certipy
---








