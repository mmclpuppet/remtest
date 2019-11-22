---
author: Michael McLoughlin <michael.mcloughlin@puppet.com\>
---

# Uninstall Remediate

You can uninstall Puppet Remediate easily with a couple of commands.

To uninstall Remediate:

1.  Stop and remove the running Remediate containers and any associated volumes by issuing the following command from the folder where your `docker-compose.yml` file is located:

    ```
    docker-compose run remediate reset
    ```

2.  To delete the Remediate containers on your system, use the following Docker command:

    ```
    docker system prune --filter label=com.docker.compose.service=remediate
    ```


**Parent topic:**[Installing Remediate](installing_remediate.md)

