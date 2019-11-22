---
author: Eamonn Smith <eamonn.smith@puppet.com\>
---

# Viewing resource details

Puppet Remediate groups attributes associated with each discovered resource into a number of different facets to give you even more insights. A facet represents a set of related attributes, each one independently maintained, that describe a certain aspect of a discovered node.

**Parent topic:**[Discovering and managing resources](inspecting_and_managing_resources.md)

## Node attributes

Puppet Remediate considers each node as a network accessible resource, whether it's physical or virtual, and discovers attributes that define the host's state and properties.

### Amazon Web Services

Discover EC2 instances running on your AWS account, including instance attributes, packages, and containers.

|Attribute|Facet::attribute|Description|
|---------|----------------|-----------|
|AMI Name|`aws_ec2Instance::name`|The name of the Amazon Machine Image \(AMI\).|
|Availability zone|`aws_ec2Instance::Placement_AvailabilityZone`|The availability zone of the instance.|
|Creation Date|`aws_ec2Instance::CreationDate`|The date and time the resource was created.|
|Description|`aws_ec2Instance::Description`|The description of the image.|
|Image type|`aws_ec2Instance::imageType`|The type of image:-   `machine`

-   `kernel`

-   `ramdisk`


|
|Instance type|`aws_ec2Instance::InstanceType`|The instance type.|
|Key name|`aws_ec2Instance::KeyName`|The name of the key pair.|
|Launch time|`aws_ec2Instance::LaunchTime`|The date and time the resource was launched.|
|Name|`host::name`|The name of the host.|
|Operating system|`computeHost::os`|The operating system running on the instance.|
|OS version|`computeHost::osVersion`|The version of the operating system running on the instance.|
|Owner ID|`aws_ec2Instance::OwnerId`|The account ID of the image owner.|
|Private DNS Name|`aws_ec2Instance::PrivateDnsName`|The private DNS name.|
|Private IP address|`aws_ec2Instance::PrivateIpAddress`|The private IP version 4 address.|
|Public DNS Name|`aws_ec2Instance::PublicDnsName`|Fully qualified public DNS hostname.|
|Public IP address|`aws_ec2Instance::PublicIpAddress`|The public IP version 4 address.|
|Region|`cloudResource::region`|The region where the instance exists.|
|Security groups|`aws_ec2Instance::SecurityGroups`|The security group associated with the instance.|
|State|`aws_ec2Instance::Monitoring_State`|Indicates whether monitoring is enabled:-   `disabled`

-   `disabling`

-   `enabled`

-   `pending`


|
|Status|`cloudResource_status`|The current status of the instance.|
|State transition reason|`aws_ec2Instance::StateTransitionReason`|Describes the state change.|
|Subnet ID|`aws_ec2Instance::SubnetId`|The ID of the subnet.|
|Tags|`tags::name``tags::value`

|The tag assigned to the AWS resource.|
|Uptime|`computeHost::uptime`|The uptime for the instance, in seconds.|
|VM Image|`vm::image`|The image identification number.|
|VM key name|`vm::keyName`|The unique identifier for the file in storage.|
|VM virtualization type|`vm::virtualizationType`|The virtualization type:-   `pv`

-   `hvm`


|
|VPC ID|`aws_ec2Instance::VpcId`|The identification for the Virtual Private Cloud \(VPC\).|

### Microsoft Azure

Discover compute instances running on your Azure account, including instance attributes, packages, and containers.

|Attribute|Facet::attribute|Description|
|---------|----------------|-----------|
|Created at|`azure_computeInstance::Created`|The date and time the resource was created.|
|Data disks|`azure_computeInstance::DataDisks`|The parameters used to add the data disk to the virtual machine.|
|ID|`azure_computeInstance::ID`|The resource ID.|
|Image|`azure_computeInstance::Image`|The virtual machine image.|
|Instance type|`azure_computeInstance::InstanceType`|The type of instance.|
|IP address|`host::privateIPv4`|The private IP version 4 address.|
|Key name|`azure_computeInstance::KeyName`|The keypair name.|
|Last scan| |The Last scan of the host represented by the data platform timestamp in UTC.|
|Location|`azure_computeInstance::Location`|The location of the resource.|
|MAC address|`azure_computeInstance::MacAddress`|The MAC address assigned to the resource.|
|Name|`host::name`|The name of the host.|
|Operating system|`computeHost::os`|The operating system running on the host.|
|OS disk|`azure_computeInstance::OSDisk`|The name of the operating system used by the virtual machine.|
|OS version|`computeHost::osVersion`|The version of the operating system running on the host.|
|Puppet version|`computeHost::puppetVersion`|The version of Puppet installed.|
|Resource group|`azure_computeInstance::ResourceGroup`|The name of the resource group.|
|Size|`azure_computeInstance::VMSize`|The size type of the virtual machine.|
|Status|`azure_computeInstance::Status`|The status of the virtual machine.|
|Subscription ID|`azure_computeInstance::SubscriptionID`|The subscription ID.|
|Tags|`azure_computeInstance::Tags`|A list of tags relevant to the content of the image.|
|Uptime|`computeHost::Uptime`|The uptime for the host, in seconds.|

### OpenStack

Discover hosts running on your OpenStack account, including host attributes, packages, and containers.

|Attribute|Facet::attribute|Description|
|---------|----------------|-----------|
|Server ID|`os_compute::ServerID`|The UUID of the server.|
|Name|`host::hostname`| |
|IP address|`host::privateIPv4`|The private IP version 4 address.|
|Operating system|`computeHost::os`|The operating system running on the host.|
|OS version|`computeHost::osVersion`|The version of the operating system running on the host.|
|Uptime|`computeHost::uptime`|The uptime for the host, in seconds.|
|Last scan| |The Last scan of the host represented by the data platform timestamp in UTC.|
|Puppet version|`computeHost::puppetVersio`n|The version of Puppet installed.|
|Created on|`os_compute::ServerCreated`|The date and time the resource was created.|
|Server Name|`os_compute::ServerName`|The server name.|
|Flavor|`os_compute::FlavorName`|The display name of the flavor.|
|Image name|`os_compute::ImageName`|The display name of the image.|
|Status|`os_compute::ServerStatus`|The current server state.|
|Security groups|`os_compute::security_groups`|The security group names.|
|VCPUs|`os_compute::vcpus`|The number of virtual CPUs in use.|
|RAM \(MB\)|`os_compute::ram`|The RAM \(MB\) on the virtual machine.|
|Disk \(GB\)|`os_compute::disk`|The disk size \(GB\) on the virtual machine.|
|Key name|`os_compute::key_name`|The keypair name.|
|IP addresses|`os_compute::ServerAddresses`|The IP addresses assigned to the virtual machine.|
|Metadata|`os_compute::ServerMetadata`|Custom server metadata at server launch time.|

### Google Cloud Platform

Discover compute engine instances running on your GCP account, including instance attributes, packages, and containers.

|Attribute|Description|
|---------|-----------|
|`createTime`|The date and time the resource was created.|
|`hostname`|The name of the host.|
|`id`|The ID of the instance.|
|`image`|The image identification number used by your cloud source.|
|`name`|The resource name.|
|`os`|The operating system running on the host.|
|`osKernel`|The type of kernel running in the operating system: `Linux` or `Windows`.|
|`osVersion`|The version of the operating system running on the host.|
|`preemptible`|Indicates whether it is an instance that can be temporarily interrupted: `true` or `false`.|
|`privateIPv4`|The private IP version 4 address.|
|`provider`|The name of the cloud provider: `Google Cloud Platform`.|
|`publicIPv4`|The IP version 4 address.|
|`puppetInstalled`|The indicator on whether Puppet is installed.|
|`puppetVersion`|The version of Puppet installed.|
|`region`|The region where the host exists.|
|`status`|The current status of the host.|
|`tags`|The tags, containing metadata, assigned to the instance.|
|`uptime`|The uptime for the host, in seconds.|

### VMware vSphere

Discover ESXi nodes running on your VMware vSphere account, including node attributes, packages, and containers.

|Field|Facet::attribute|Description|
|-----|----------------|-----------|
|Annotation|`vmware_computeInstance::Config_Annotation`|Description for the virtual machine.|
|Disk|`vmware_computeInstance::Disk`|Guest information about disks; used space and total space available.|
|Fault tolerance state|`vmware_computeInstance::Runtime_FaultToleranceState`|Defines a set of states for a fault tolerant virtual machine:-   `disabled`

-   `enabled`

-   `needSecondary`

-   `notConfigured`

-   `running`

-   `starting`


|
|Guest full name|`vmware_computeInstance::GuestFullName`|The full name of the guest operating system for the virtual machine.|
|Guest hostname|`vmware_computeInstance::HostName`|The FDQN of the guest host.|
|Guest heartbeat status|`vmware_computeInstance::QuickStats`|The current status of the guest operating system:-   `gray` - VMware tools not installed or running.

-   `red` - No heartbeat.

-   `yellow` - Intermittent heartbeat.

-   `green` - Guest operating system responding normally.


|
|Guest state|`vmware_computeInstance::GuestState`|Operation mode of the guest operating system:-   `running`

-   `shuttingdown`

-   `resetting`

-   `standby`

-   `notrunning`

-   `unknown`


|
|ID|`vmware_computeInstance::ID`|The guest operating system identifier.|
|IP address|`host::privateIPv4`|The private IP version 4 address.|
|IP stack|`vmware_computeInstance::IpStack`|Guest information about the IP networking stack:-   `DomainName`

-   `IpAddress`


|
|Last scan| |The last scan of the host represented by the data platform timestamp in UTC.|
|Max memory usage \(MB\)|`vmware_computeInstance::Runtime_MaxMemoryUsage`|The maximum memory usage based on the memory configuration of the virtual machine, as well as limits configured on the virtual machine, or any parent resource pool.|
|Memory size \(MB\)|`vmware_computeInstance::Config_MemorySizeMB`|The memory size of the virtual machine, in megabytes.|
|Name|`host::name`|The name of the host.|
|Net|`vmware_computeInstance::Net`|Guest information about network adapters:-   `Network`

-   `MacAddress`

-   `IpAddress`


|
|Number of CPU's|`vmware_computeInstance::Config_NumCpu`|The number of processors in the virtual machine.|
|Number of virtual disks|`vmware_computeInstance::Config``_NumVirtualDisks`|The number of virtual disks attached to the virtual machine.|
|Operating system|`computeHost::os`|The operating system running on the host.|
|OS version|`computeHost::osVersion`|The version of the operating system running on the host.|
|Overall status|`vmware_computeInstance::OverallStatus`|The overall alarm status on this host.|
|Power state|`vmware_computeInstance::Runtime_PowerState`|Defines a set of states for a virtual machine:-   `poweredOff`

-   `poweredOn`

-   `suspended`


|
|Tools running status|`vmware_computeInstance::ToolsRunningStatus`|The current running status of VMware tools in the guest operating system.|
|Tools version|`vmware_computeInstance::ToolsVersion`|The VMware tools version.|
|Uptime|`computeHost::uptime`|The uptime for the instance, in seconds.|

### Network nodes

Discover nodes running on your network, including node attributes, packages, and containers.

|Attribute|Description|
|---------|-----------|
|`dnsName`|The private DNS name.|
|`hostname`|The name of the host.|
|`name`|The resource name.|
|`os`|The operating system running on the host.|
|`osKernel`|The type of kernel running in the operating system: `Linux` or `Windows`.|
|`osVersion`|The version of the operating system running on the host.|
|`privateIPv4`|The private IP version 4 address.|
|`privateIPv6`|The private IP version 6 address.|
|`publicDnsName`|Fully qualified public DNS hostname.|
|`publicIPv4`|The IP version 4 address.|
|`puppetInstalled`|The indicator on whether Puppet is installed.|
|`puppetVersion`|The version of Puppet installed.|
|`uptime`|The uptime for the host, in seconds.|

## Package attributes

Discover various types of information about a package instance, its attributes, along with a list of hosts and containers it's installed on.

Discover attributes that describe the characteristics of the package. The UI queries the data platform to discover the `name`, `version`, and `packageManager` attributes.

|Attribute|Description|
|---------|-----------|
|`name`|The package name.|
|`version`|The package version.|
|`packageManager`|The name of the package manager: -   `apk`

-   `Chocolatey`

-   `dpkg`

-   `rpm`

-   `msi`


|

## Container attributes

Discover various types of information about a container image, its attributes, packages in use, and its label information.

Discover attributes that describe the characteristics of the container. The UI queries the data platform for the discovered `container` facet.

|Attribute|Description|
|---------|-----------|
|`name`|The container name for processes running inside the container.|
|`dockerAPIVersion`|The version of the Docker Engine API.|
|`dockerMinAPIVersion`|The minimum version of the Docker Engine API.|
|`dockerVersion`|The version of Docker.|
|`id`|The Docker container ID for processes running inside the container.|
|`imageName`|The Docker image name for processes running inside the container.|

Discover the container label names and values:

-   **Label** - the label name, derived from the `name` attribute.

-   **Value** - the label value, derived from the `value` attribute.


