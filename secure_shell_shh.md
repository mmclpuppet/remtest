---
author: Eamonn Smith <eamonn.smith@puppet.com\>
---

# Secure Shell \(SSH\)

The two types of SSH authentication are username and password, using negotiated encryption, and private key files, using asymmetric encryption.

**Tip:** As a dual-factor authentication with nodes, it's recommended to use SSH private key files and to include a username and passphrase for each file. Using an SSH private key file, rather than an SSH username and password, is considered more secure against potential compromises on remote nodes because the password is not sent over the network.

When using SSH authentication to discover resources running on Linux nodes, there are a number of prerequisites:

-   To install the Puppet agent on nodes, your SSH credentials must be for the root account.

-   To discover containers on nodes, your SSH credentials must be for the root account or an account that is a member of the Docker group.


**Parent topic:**[Adding node credentials](adding_node_credentials.md)

## Add SSH private key files

Upload an SSH private key file to discover resources, and to run tasks on your Linux hosts.

1.  On the sidebar, click **Manage credentials**.

2.  Click **Add credentials** and then click **SSH private key file**.

3.  Click **Browse**, select your files, and then click **Open**.

4.  Click **Configure keys**.

5.  In the **Name** field enter a unique and descriptive name.

6.  Assign an individual scope, or both, to the credential:

    -   **Discover resources on nodes**: This credential scope is valid only for discovering resources on your Linux nodes.
    -   **Remediate vulnerabilities**: This credential is valid only for running tasks on your Linux nodes. When this individual scope is selected, no attempts are made to discover resources.
        -   **Escalate privileges to root**: When required to run tasks on nodes, sudo escalate `non-root` account privileges to `root`. Privilege escalation occurs if the first attempt to run a task fails when using `non-root` privileges.

7.  In the **Username** field, enter your SSH username.

8.  In the **Passphrase** field, enter your SSH passphrase, or leave it blank if your key is not encrypted.

9.  Click **Add keys**.


## Add SSH username and password

Add an SSH username and password to discover resources, and to run tasks on your Linux hosts.

1.  On the sidebar, click **Manage credentials**.

2.  Click **Add credentials** and then click **SSH credential**.

3.  In the **Name** field, enter a unique and descriptive name.

4.  Assign an individual scope, or both, to the credential:

    -   **Discover resources on nodes**: This credential scope is valid only for discovering resources on your Linux nodes.
    -   **Remediate vulnerabilities**: This credential is valid only for running tasks on your Linux nodes. When this individual scope is selected, no attempts are made to discover resources.
        -   **Escalate privileges to root**: When required to run tasks on nodes, sudo escalate `non-root` account privileges to `root`. Privilege escalation occurs if the first attempt to run a task fails when using `non-root` privileges.

5.  In the **Username** field, enter your SSH username.

6.  In the **Password** field, enter your SSH password, and then click **Add credential**.


