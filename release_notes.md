---
author: Claire Cadman <claire.cadman@puppet.com\>
---

# Release notes

New features, enhancements, resolved issues, and known issues for Puppet Remediate 1.x release series.

## Version 1.0.1

Released 1 August 2019.

This is the initial release of Remediate.

Known issues:

-   **Unable to install Remediate on Debian8 with the default kernel module.** Upgrade to Kernal 4.9 and install Remediate again.

-   **NET Scan discovered resources being shown as cloud instances.** If you discover a vmpooler box via a netscan provider it will be counted as a top cloud instance by region.

-   **Due to inconsistent DNS lookups, tasks fail to run on discovered hosts**. When discovered hosts are running on the same domain, an inconsistent DNS lookup between discovering hosts and running tasks on discovered hosts results in tasks failing.

-   **In a multi-network environment, the first discovery run might not identify the IP or hostname**. Wait for the second discovery run, which happens automatically after four hours.


