---
author: michael.mcloughlin@puppet.com
---

# Upgrade Remediate

Upgrading to new version of Remediate can be done with a few simple commands.

To upgrade from Remediate 1.0.1 to Remediate 1.1.0:

1.  Run the following command from the folder where your `docker-compose.yml` file is located:

    ```
    docker-compose run remediate stop
    ```

2.  Remove the `oauth_client.json` file:

    ```
    docker secret rm oauth_client.json
    ```

3.  Finally, run the Remediate update command:

    ```
    docker-compose run remediate update
    ```


**Parent topic:**[Installing Remediate](installing_remediate.md)

