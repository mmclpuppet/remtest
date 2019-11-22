---
author: Eamonn Smith <eamonn.smith@puppet.com\>
---

# Remediating vulnerabilities

To help fix vulnerabilities, run ad hoc tasks on target Linux and Windows nodes to install Puppet agents, manage packages or system services, or to execute shell commands. Upload your scripts to be converted into tasks, or upload a Puppet module containing a task.

-   **[Upload scripts](uploading_scripts.md)**  
Uploaded Linux and Windows scripts are converted into tasks to run on vulnerable nodes and help fix vulnerabilities. To decrease task maintenance, combine scripts into one task that runs on both operating systems.
-   **[Upload modules](uploading_modules.md)**  
To help fix vulnerabilities on nodes, upload modules published on the Puppet Forge. The module must contain a task.
-   **[Run tasks](running_tasks_on_discovered_nodes.md#)**  
Run ad hoc tasks on target nodes to upgrade packages, restart services, execute shell commands, or perform any other type of single-action executions on your nodes.

