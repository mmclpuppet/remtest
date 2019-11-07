---
author: Eamonn Smith <eamonn.smith@puppet.com\>
---

# Upload modules

To help fix vulnerabilities on nodes, upload modules published on the Puppet Forge. The module must contain a task.

Modules are self-contained bundles of code and data. Each module manages a specific task in your infrastructure, such as installing and configuring a piece of software. For more information, see [Module fundamentals](https://puppet.com/docs/puppet/latest/modules_fundamentals.html).

1.  Download a module from the [Forge](https://forge.puppet.com/).

2.  On the sidebar, click **Manage tasks**, and then click **Add tasks**.

3.  Click **Upload a module**, choose the module you just downloaded from the Forge.

    **Important:** The name of your module needs to follow the default download format.

4.  Click **Add details**.

5.  Click **Save task**.

    The **Settings** page appears, and your tasks from the module is now available and is listed in the tasks table.

    **Important:** Your module can’t exceed 1Mb in size.


**Parent topic:**[Remediating vulnerabilities](remediating_vulnerabilities.md)

**Related information**  


[Run tasks](running_tasks_on_discovered_nodes.md#)

