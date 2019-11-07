---
author: Eamonn Smith <eamonn.smith@puppet.com\>
---

# Run tasks

Run ad hoc tasks on target nodes to upgrade packages, restart services, execute shell commands, or perform any other type of single-action executions on your nodes.

Tasks are similar to scripts, but they are kept in modules and can have metadata. For more information, see [Bolt tasks](https://puppet.com/docs/puppet/latest/puppet_tasks.html).

When selecting to run a task from either a details or listing page, some of the selected nodes might not be eligible to run the task on. An eligible node must be accessible using the SSH or WinRM credentials you added, or if running the install Puppet agent task, an eligible node doesn't have the agent installed.

1.  On the sidebar, click **Run tasks**, and select the task:

    -   Install Puppet agent.
    -   Run a shell command.
    -   Manage package.
    -   Manage service.
2.  Enter the values for the task parameters \(see below\).

3.  Click **Select nodes**.

4.  Select the nodes to run the task on, and click **Select credentials**.

5.  Select the credentials for accessing the hosts, and click **Review task summary**.

6.  Review the tasks details, your credentials, the list of target nodes, and click **Run task**.

    **Tip:** To view the status of the task run, on the left hand pane, click **Recent events**.


**Parent topic:**[Remediating vulnerabilities](remediating_vulnerabilities.md)

## Installing Puppet agents

Install a Puppet Enterprise agent to regularly pull configuration catalogs from a Puppet master, and apply them to your target Linux or Windows nodes. The agent maintains the node configuration you want.

|Parameter|Description|
|---------|-----------|
|`cacert_content`|The master CA certificate content \(optional\). If not specified, the master's identity is not verified during the agent installation.|
|`certname`|The unique certificate name for the Puppet agent \(optional\).|
|`custom_attribute`|The custom attribute setting added to `puppet.conf` and included in the `custom_attributes` section of `csr_attributes.yaml`. **Important:** Values must be entered as an array.

|
|`dns_alt_names`|The alternative DNS names for generating the agent certificate.|
|`environment`|The environment to install with the Puppet agent \(optional\).|
|`extension_request`|The extension attribute setting added to `puppet.conf` and included in the `extension_requests` section of `csr_attributes.yaml`. **Important:** Values must be entered as an array.

|
|`master`|The required hostname for the Puppet master. The FQDN must be fully resolvable by the node on which you're installing the agent.|

## Running shell commands

Execute an arbitrary shell command on discovered nodes without installing an agent.

|Parameter|Description|
|---------|-----------|
|`command`|The command to execute on the target nodes. Linux example:

```
echo "Hello, World ${USER}" > /hello.txt
```

Windows example:

```
echo "Hello, World $env:UserName" > C:\hello.txt

```

To execute commands, Windows tasks use the command prompt. To run PowerShell commands, you must invoke PowerShell. For example:

```
powershell Get-Process
```

|
|`failonfail`|By default, the task fails when the command returns a non-zero. To disable this default setting, select the **checkbox**.|
|`interleave`|By default, content from `stdout` and `stderr` is interleaved. To disable this default setting, select the **checkbox**.|

## Managing packages

Install, upgrade, or uninstall packages on discovered nodes without installing an agent.

**Remember:** To run the manage package task on target hosts, the following package management systems are required:

-   APT or YUM for Linux hosts.

-   Chocolatey for Windows hosts.


|Parameter|Description|
|---------|-----------|
|`action`|The action to be applied to the package:-   **install** the package. To install a specific version of the package, specify the value in the `version` parameter. If installing the package for the first time, the package repository on each target node must have the package stored.


-   **uninstall** the package. To uninstall a specific version of the package, specify the value in the `version` parameter.

-   **upgrade** the version of the package. This is particularly useful for upgrading vulnerable packages to secure versions. To upgrade to a specific version, choose **install**, and specify the value in the `version` parameter.


|
|`name`|The name of the package.|
|`provider`|The name of the provider to use for managing or inspecting the package.|
|`version`|The version, and if applicable, the release value of the package. A version number range or a semver pattern are not permitted. For example, to install the `bash-4.1.2-29.el6.x86_64.rpm` package, enter 4.1.2-29.el6. **Tip:** To install or upgrade to the latest version of a package, leave the `version` parameter blank.

|

## Managing system services

Execute an arbitrary shell command on discovered hosts without installing an agent.

|Parameter|Description|
|---------|-----------|
|`action`|The action to be applied to the service:-   **stop** the service.

-   **start** the service.

-   **restart** the service.

-   **enable** the service.

-   **disable** the service.

-   View the current **status** of the service \(Windows only\).


|
|`name`|The name of the service.|
|`provider`|The name of the provider to use for managing or inspecting the service.|

