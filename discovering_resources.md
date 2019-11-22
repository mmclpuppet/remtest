---
author: Eamonn Smith <eamonn.smith@puppet.com\>
---

# Discovering resources

Discover node resources running on your infrastructure source account. Add your node credentials and discover node attributes, the system services, the users and groups belonging to each node, along with packages, tags, and containers.

## What resources can I discover?

Depending on the level of credentials you enter, this table lists the depth of resources that you can discover.

|Sources and credentials|Discovered resources|
|-----------------------|--------------------|
|-   Infrastructure source.


|-   Nodes, including node attributes.


|
|-   Infrastructure source.

-   SSH or WinRM credentials.


|-   Nodes, including node attributes.

-   Services

-   Users

-   Groups

-   Tags

-   Packages, including package attributes.

-   Container images, including container attributes.


|

## Nodes

A number of nodes summary pages give you information about node instances across your entire infrastructure, and each page queries the data platform for specific attributes belonging to each node. For more information on nodes, see [Node attributes](viewing_resource_details.md#).

**Tip:** Click a card to drill down and view the detailed list.

|Node summary page|Description|
|-----------------|-----------|
|Nodes|Click the Nodes dashboard card to see a list of on-premises and cloud nodes running on your infrastructure.|
|Packages|The total number of packages installed on discovered hosts.|
|Inaccessible nodes|The total number of discovered nodes running on your infrastructure that could not be accessed due to entering invalid credentials or due to configuration issues.|
|AWS nodes|Click the AWS nodes dashboard card to see a list of EC2 instances running on your AWS account.|
|VMware nodes|The total number of nodes running on your VMware vSphere account.|
|OpenStack nodes|The total number of nodes running on your OpenStack account.|
|Microsoft Azure nodes|The total number of nodes running on your Microsoft Azure account.|
|Google Cloud Platform nodes|The total number of nodes running on your GCP account.|
|Nodes with Puppet|The percentage and total number of discovered nodes with or without Puppet installed, as well as unknown hosts.|
|Uptime less than 24 hours|The percentage and total number of nodes with an uptime with less than, or greater than, 24 hours.|
|Top operating systems|The top six operating systems installed on discovered hosts.|
|Linux distributions|The percentage and total number of Linux nodes categorized by the distribution installed.|
|Windows versions|The percentage and total number of Windows nodes categorized by the version of Windows installed.|
|Top cloud instances by region|The top six cloud instances categorized by region.|
|Top containers by image|The top six container images used by running containers.|

## Packages

Click the Packages dashboard card to see a list of packages in use across your infrastructure by name, version, and manager, as well as the number of instances of each package. For more information about packages, see [Package attributes](viewing_resource_details.md#).

## Containers

Click the Containers, or the Top containers by image, dashboard card to see a list of container instances running on your infrastructure. For more information about containers, see [Container attributes](viewing_resource_details.md#).

**Parent topic:**[Discovering and managing resources](inspecting_and_managing_resources.md)

