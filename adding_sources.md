---
author: Eamonn Smith <eamonn.smith@puppet.com\>
---

# Add sources

Add your vulnerability scanner to detect and fix vulnerabilities across your infrastructure. To discover nodes, packages, and containers running on your entire infrastructure, add multiple infrastructure sources.

1.  On the sidebar, click **Manage sources**.

2.  Click **Add sources**, and then select a source:

    -   Vulnerability scanner:
        -   Qualys

        -   Rapid7

        -   Tenable

    -   Infrastructure source:
        -   Amazon Web Services

        -   Google Cloud Platform

        -   Microsoft Azure

        -   OpenStack

        -   VMware vSphere

        -   IP addresses

3.  Enter you authentication credentials for the source \(see below for details.\)

4.  Click **Discover**.

    **Note:** The quantity of data that is contained in your source affects the amount of time it takes for information to be displayed in Remediate. It might take several hours for content to be displayed if your source uses a very large data set.


**Related information**  


[Prioritizing vulnerabilities](prioritizing_vulnerabilities.md)

[Discovering and managing resources](inspecting_and_managing_resources.md)

## Vulnerability scanners

Puppet Remediate integrates with Tenable, Qualys and Rapid7.

**Note:** Ask your security team for the permissions to import vulnerability scan data.

### Qualys

Add the details for your Qualys Vulnerability Manager account.

|Parameter|Description|
|---------|-----------|
|Name|A unique and descriptive name to identify this vulnerability scanner.|
|API server URL|The HTTPS URL and port number to the platform where your Qualys account is located.|
|Username|Your Qualys username to authenticate with.|
|Password|Your Qualys password to authenticate with.|

### Rapid7

Add the details for your Rapid7 Nexpose \(on-prem\) or InsightVM \(cloud\) account.

|Parameter|Description|
|---------|-----------|
|Name|A unique and descriptive name to identify this vulnerability scanner.|
|InsightVM URL|The HTTPS URL and port number to your InsightVM or Nexpose instance.|
|Username|Your Rapid7 username to authenticate with.|
|Password|Your Rapid7 password to authenticate with.|
|Enable SSL certification verification|To verify the signature on the SSL certificate returned by Rapid7 using your CA cert, select this option. Save your CA cert in the `puppet-remediate/data/vr/ca_certs` directory.|

### Tenable

Add the details for your Tenable.io \(cloud\) account.

|Parameter|Description|
|---------|-----------|
|Name|A unique and descriptive name to identify this vulnerability scanner.|
|Access key|Your Tenable.io access key to authenticate with the Tenable API. For more information about generating an access key, see the [Tenable.io documentation](https://docs.tenable.com/cloud/Content/Settings/GenerateAPIKey.htm).|
|Secret key|Your Tenable.io secret key to authenticate with the Tenable API. For more information about generating a secret key, see the [Tenable.io documentation](https://docs.tenable.com/cloud/Content/Settings/GenerateAPIKey.htm).|

## Infrastructure sources

Discover node instances on the following infrastructure sources.

### Amazon Web Services \(AWS\)

Add the AWS authentication credentials to discover the EC2 instances running on your AWS account.

|Parameter|Description|
|---------|-----------|
|Name|A unique and descriptive name to identify this source.|
|Access key|The access key ID that you generated in the AWS Management Console.|
|Secret key|The secret access key that corresponds to your access key ID.|

### Google Cloud Platform \(GCP\)

Add the GCP authentication credentials to discover the node instances running on each of your accounts. The client email, the private key, the private key ID, and the project ID values are located in the service account key file \(`.json`\) you saved after generating your GCP credentials in the GCP console.

|Parameter|Description|
|---------|-----------|
|Name|A unique and descriptive name to identify this source.|
|Client email|The service account email associated with your GCP account.|
|Private key|The private key you generated in the GCP console.|
|Private key ID|The private ID that corresponds to your private key.|
|Project ID|The GCP project that corresponds to your service account.|

### Microsoft Azure

Add the Microsoft Azure authentication credentials to discover the node instances on each of your Microsoft Azure accounts.

Make sure to log into the Azure portal and register your application. Name it PuppetRemediate and select the **Web app / API** application type. You must also assign the **Reader** permission to the application.

|Parameter|Description|
|---------|-----------|
|Name|A unique and descriptive name to identify this source.|
|Subscription ID|The subscription ID that identifies your Azure services subscription.|
|Tenant ID|The AAD tenant ID \(also known as the directory ID\).|
|Application ID|The Azure application ID \(also known as the client ID\).|
|Client ID|The client key \(also known as the authentication key\) generated for your application within the AAD.|

### OpenStack

Add the OpenStack authentication credentials to discover the node instances running on each of your OpenStack accounts.

|Parameter|Description|
|---------|-----------|
|Name|A unique and descriptive name to identify this source.|
|Endpoint|The authentication URL for the identity \(Keystone\) service.|
|Username|Your OpenStack username to authenticate with.|
|Password|Your OpenStack password to authenticate with.|
|Domain name|The authentication domain name used to connect to OpenStack.|
|Tenant ID|The tenant ID, also known as the project ID, used for OpenStack.|

### VMware Sphere

Add the VMware vSphere authentication credentials to discover the node instances running on each of your vSphere accounts.

|Parameter|Description|
|---------|-----------|
|Name|A unique and descriptive name to identify this source.|
|vCenter server|The FQDN of the vCenter server.|
|vCenter username|The vSphere username used to authenticate to the vCenter server.|
|vCenter password|The vSphere password required to authenticate to the vCenter server.|

### Network nodes

Discover nodes by specifying an IP address range, a CIDR block, or by uploading a comma-separated IP address list.

|Parameter|Description|
|---------|-----------|
|Name|A unique and descriptive name to identify this source.|
|Type|The IP address input type:-   IP range: Using the From and To fields, enter the IP address range.

-   CIDR: Enter the base IP address and the subnet mask to determine the network portion of the address.

-   CSV: Upload a comma-separated list of:

-   IP addresses.

-   Hyphen-separated IP ranges.

-   CIDR notations.


|

