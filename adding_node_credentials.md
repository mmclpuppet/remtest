---
author: Eamonn Smith <eamonn.smith@puppet.com\>
---

# Adding node credentials

Add credentials to authenticate with nodes and fix vulnerabilities or gain insights into discovered resources. Each credential is encrypted and stored securely in the vault.

The two authentication methods are Secure Shell \(SSH\) authentication with Linux nodes on port 22, and Windows Remote Management \(WinRM\) authentication with Windows nodes on ports 5986 and 5985.

CAUTION:

Using each node credential you provide, Remediate attempts to authenticate with each discovered node until a successful authentication is achieved. This process repeats every four hours, using previously successful credentials first. Depending on the configuration of your network management and security sensors, Remediate activities might trigger alerts or an active response.

-   **[Secure Shell \(SSH\)](secure_shell_shh.md#)**  
The two types of SSH authentication are username and password, using negotiated encryption, and private key files, using asymmetric encryption.
-   **[Windows Remote Management \(WinRM\)](windows_remote_management_winrm.md#)**  
To authenticate with Windows nodes, Puppet Remediate uses NTLM authentication over HTTPS on port 5986. When enabled, Remediate falls back to using NTLM authentication over HTTP on port 5985, if the default authentication fails.

