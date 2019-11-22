---
author: Eamonn Smith <eamonn.smith@puppet.com\>
---

# Installing Puppet agents

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

