---
author: Eamonn Smith <eamonn.smith@puppet.com\>
---

# System requirements

Before installing Puppet Remediate, check to ensure your system meets these requirements.

## Supported operating systems

You can install Remediate on the following operating systems.

|Operating System|Versions|Architecture|Prerequisite|
|----------------|--------|------------|------------|
|CentOS|7 or higher|x64|  
                                         [Docker CE](https://docs.docker.com/install/#supported-platforms) 17.06-ce or higher, or [Docker EE](https://docs.docker.com/install/linux/docker-ee/centos/) 17.06-ee or higher.

|
|Red Hat Enterprise Linux|7 or higher|x64|
|Debian|8 or higher|x64|
|Ubuntu|14.04 or higher|x64|
|Windows|10|x64|[Docker](https://docs.docker.com/docker-for-windows/install/) for Windows.

 When you install Remediate on a virtual machine, you must enable nested virtualization. For more information, see the documentation for the hypervisor you are using.

|

## Docker requirements

Both Docker CE and Docker EE editions include the option to run Kubernetes as a single-node cluster on a local machine using [port `8080`](https://kubernetes.io/docs/reference/access-authn-authz/controlling-access/#api-server-ports-and-ips). Remediate requires that no other application use ports `8080` and `8443`. Note that Docker swarm mode requires [additional ports](https://docs.docker.com/engine/swarm/swarm-tutorial/#open-protocols-and-ports-between-the-hosts).

If using Docker for Windows, the virtual machine must be configured with 8 GB of memory.

To prevent running out of storage, [configure log rotation](https://success.docker.com/article/how-to-setup-log-rotation-post-installation) by editing the `log-driver` and `log-opts` parameters within the daemon configuration file that is located here:

-   Linux: `/etc/docker/daemon.json`

-   Windows: `%programdata%\docker\config\daemon.json`


To deploy the Docker Compose file, you need to install [Docker Compose](https://docs.docker.com/compose/install/) version 1.24.1.

## Discoverable operating systems

Discover resources that run on these operating systems.

|Operating system|Versions|Prerequisite|
|----------------|--------|------------|
|Enterprise Linux: -   CentOS

-   Red Hat Enterprise Linux


|5 or higher|For the account Remediate authenticates with, configure bash as the login shell.|
|Debian|7 or higher|
|SUSE Linux Enterprise Server|12|
|Ubuntu|14.04 or higher|
|Windows Server|2012 or higher|WinRM is enabled and PowerShell 3.0 is installed.|

## System configuration

Before installing Remediate, make sure that your network is properly configured, and that the time is correctly set and managed on each server. These are the port requirements for a Remediate installation.

|Port|Description|
|----|-----------|
|-   `443` \(HTTPS\)


|Required to install or update to the latest version of Remediate from: -   storage.googleapis.com

-   gcr.io


|
|-   `8443` \(HTTPS\)


|Required to view the Remediate dashboards.

|
|-   `22`


|Required for SSH authentication on discovered Linux hosts.|
|-   `5986` \(HTTP\)

-   `5985` \(HTTP - fallback\)


|Required for WinRM authentication on discovered Windows hosts.|

## Hardware requirements

Remediate requires:

|Storage|20.0 GB|
|Memory|8.0 GB|
|CPUs|2|

## Supported browsers

The Remediate user interface is supported on the latest versions of the following browsers:

-   Google Chrome

-   Mozilla Firefox

-   Microsoft Edge

-   Apple Safari


**Parent topic:**[Installing Remediate](installing_remediate.md)

