---
author: Michael McLoughlin <michael.mcloughlin@puppet.com\>
---

# Install Remediate on offline nodes

If any of your swarm nodes are offline \(do not have external connectivity\), you must manually import the Remediate images in order to install the product.

Prior to installing Remediate on any offline nodes, check that you have carried out the following prerequisite tasks:

-   Make sure you meet the system requirements for installing and running Remediate, and that you have received your [license](https://licenses.puppet.com/).
-   Install Remediate on a node with external connectivity. See the instructions that explain how to **Install Remediate on an online node** for more information. You will import the Remediate images exported from this node into the nodes that do not have internet connectivity.
-   Ensure that Docker and Docker Compose are installed on the nodes where you want to install the Remediate images. If you are installing Docker Compose on Windows, ensure that you create a new Windows environment variable called `COMPOSE_CONVERT_WINDOWS_PATHS` and set it to `1`. This enables path conversion from Windows-style to Unix-style in volume definitions.
-   Ensure that your license and the Remediate [Docker Compose file](https://storage.googleapis.com/remediate/stable/latest/docker-compose.yml) are added to the nodes where you want to install the Remediate images.

To install Remediate on nodes that do not have network connectivity:

1.  On a node where you have Remediate already installed, export the Remediate images as a tar file:

    ```
    $ docker-compose run remediate export
    ```

    A file named `remediate.tar.gz` is added to the folder where your Docker Compose file is stored.

2.  On the node where you want to install Remediate, initialize a swarm by running the following command:

    ```
    docker swarm init
    ```

3.  Copy the `remediate.tar.gz` file to the folder on the offline node where your Docker Compose file is located, and import it by using the command below:

    ```
    $ docker-compose run remediate import --filename ./remediate.tar.gz
    ```

4.  Use the following command ⁠to start Remediate \(replacing `your-license.json` with your own license\):

    ```
    docker-compose run remediate start --license-file your-license.json
    ```

5.  To check that the containers have started running, run this command:

    ```
    docker ps
    ```

    The list of running containers:

    ```
    CONTAINER ID        IMAGE                                             COMMAND                  CREATED             STATUS                   PORTS                NAMES
    36139cda23ca        gcr.io/puppet-discovery/pdp-go:<version>          "/app/entrypoint.sh"     3 minutes ago       Up 3 minutes (healthy)   8082/tcp, 8087/tcp   remediate_gopdp.1.w035aad0ifvu0ynaimxy64lcq
    43709401f394        gcr.io/puppet-discovery/pd-storage:<version>      "storageEntryPoint.s…"   3 minutes ago       Up 3 minutes (healthy)   5432/tcp             remediate_storage.1.omv1rrd3rwhnwo3ngurgtcnxk
    551b061acc98        gcr.io/puppet-discovery/licensing-api:<version>   "/entrypoint.sh"         3 minutes ago       Up 3 minutes (healthy)                        remediate_licensing.1.kdoj7s492el77rdpc2rza3fx7
    43a3568e6b5a        vault:1.1.2                                       "docker-entrypoint.s…"   3 minutes ago       Up 3 minutes (healthy)   8200/tcp             remediate_vault.1.k0jgyxxi45ldn4pqadhgvjf0o
    11b90d8564ef        gcr.io/puppet-discovery/identity:<version>        "/opt/jboss/tools/do…"   3 minutes ago       Up 3 minutes (healthy)   8080/tcp, 8443/tcp   remediate_identity.1.b1wkt4kx4ps107949k14ctsqx
    1235fd27cbdc        gcr.io/puppet-discovery/frontdoor:<version>       "nginx -g 'daemon of…"   3 minutes ago       Up 3 minutes (healthy)   80/tcp               remediate_frontdoor.1.oib8jsr7u4z6wqxvjz02mxcxz
    a3a641af5269        gcr.io/puppet-discovery/pdp-proxy:<version>       "/pdp-proxy-svc"         3 minutes ago       Up 3 minutes (healthy)   9200/tcp             remediate_export.1.uin509pnc2zb4pf3rdjr1so0x
    c60250b8a2eb        gcr.io/puppet-discovery/node-ui:<version>         "/usr/src/app/entryp…"   3 minutes ago       Up 3 minutes (healthy)                        remediate_ui.1.3u0tewgou7t4hz2c46nn4mydo
    f9af99dc9ca7        gcr.io/puppet-discovery/edge:<version>            "/edge-svc"              3 minutes ago       Up 3 minutes             9997/tcp             remediate_edge.1.koacwnjoce2tabwcbi73619fu
    149485b54fec        gcr.io/puppet-discovery/controller:<version>      "/controller-svc"        4 minutes ago       Up 4 minutes (healthy)   9999/tcp             remediate_controller.1.mww2fm9up4lmeisjorul89hr4
    f9f1ab4a029d        gcr.io/puppet-discovery/vr:<version>              "/vr-svc"                4 minutes ago       Up 4 minutes (healthy)                        remediate_vr.1.yjlliup91g4mac1bklvvw2nqq
    ```

6.  To access Remediate on a local workstation, the URL is `[https://localhost:8443](https://localhost:8443/)`, or port `8443` on the host where you installed Remediate.

7.  Read and accept the software license agreement.

8.  Sign in to Remediate.

    For default usernames and passwords, see **Managing user access**.


**Parent topic:**[Installing Remediate](installing_remediate.md)

**Related information**  


[System requirements](system_requirements.md)

[Install Remediate on online nodes](install_remediate.md)

[Managing user access](managing_user_access.md#)

