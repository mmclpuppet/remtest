---
author: Eamonn Smith <eamonn.smith@puppet.com\>
---

# Installing Remediate

-   **[Architecture GH DESKTOP](remediate_architecture.md)**  
Puppet Remediate consists of a number of components and services, each one running as an individual Docker container.
-   **[System requirements](system_requirements.md)**  
Before installing Puppet Remediate, check to ensure your system meets these requirements.
-   **[Install Remediate on online nodes](install_remediate.md)**  
Install Puppet Remediate on a Linux or Windows machine that is connected to the internet.
-   **[Install Remediate on offline nodes](installing_remediate_on_offline_nodes.md)**  
If any of your swarm nodes are offline \(do not have external connectivity\), you must manually import the Remediate images in order to install the product.
-   **[Install Remediate in multi-network deployments](install_remediate_in_multi_network_deployments.md)**  
 Puppet Remediate connects to security providers to discover hosts with vulnerabilities. To take action and fix the vulnerabilities, the system needs to connect directly to the hosts. If the host you want to fix is deployed in different network segments that are not directly accessible from where you installed Remediate, you can setup a multi-network deployment.
-   **[Verify Docker Compose file](verify_docker_compose_file.md)**  
With each Puppet Remediate release, a digital signature is created using the private key portion of an asymmetric key. You can manually validate the signature using the public key portion of the same asymmetric key. 

