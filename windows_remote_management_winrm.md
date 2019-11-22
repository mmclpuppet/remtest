---
author: Eamonn Smith <eamonn.smith@puppet.com\>
---

# Windows Remote Management \(WinRM\)

To authenticate with Windows nodes, Puppet Remediate uses NTLM authentication over HTTPS on port 5986. When enabled, Remediate falls back to using NTLM authentication over HTTP on port 5985, if the default authentication fails.

**Parent topic:**[Adding node credentials](adding_node_credentials.md)

## Add WinRM credentials

1.  On the sidebar, click **Manage credentials**.

2.  Click **WinRM credential**.

3.  In the **Name** field, enter a unique and descriptive name.

4.  Assign an individual scope, or both, to the credential:

    -   **Discover resources on nodes**: This credential scope is valid only for discovering resources on your Windows nodes.
    -   **Remediate vulnerabilities**: This credential is valid only for running tasks on your Windows nodes. When this individual scope is selected, no attempts are made to discover resources.
5.  Select **HTTP fallback** to permit using NTLM authentication over HTTP, if the default NTLM authentication over HTTPS fails.

6.  Click **Add credential**.


