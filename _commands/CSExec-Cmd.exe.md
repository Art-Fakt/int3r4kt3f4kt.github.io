---
description: |
  An alternative to PSexec.py from impacket . This will give you an interactive shell on the Windows host.

  Command Reference:

  	Target: PC01.test.local

  	Domain: test.local

  	Username: j.doe

  	Password: 'Passw0rd!'
command: |
  csexec.py test.local/j.doe:'Passw0rd!'@PC01.test.local --install-service --codec cp866
code: |

    1.Cross-compiles a C# service binary with Mono.
    2.Uploads the binary from [1] with random name (can be adjusted with -rbn/--remote-binary-name) to the remote target at %SystemRoot%.
    3.Creates a new service with random name (can be adjusted with --service-name) pointing to the binary from [1].
    4.Starts the service from [2].

    Command execution is done via Process.Start, command prompt is cmd.exe.

items:
  - Password
  - Username
services:
  - SMB
OS:
  - Linux
  - Windows
attack_types:
  - Exploitation
  - Injection
  - Bypass
references:
  - No Ref
---
