---
author: Eamonn Smith <eamonn.smith@puppet.com\>
---

# Install Remediate on online nodes

Install Puppet Remediate on a Linux or Windows machine that is connected to the internet.

Make sure you meet the system requirements for installing and running Remediate, and that you have received your [license](https://licenses.puppet.com/).

1.  Install and run Docker on the node where you want to install Remediate.

    1.  Download Docker for your operating system:

        -   Linux: [Docker CE](https://docs.docker.com/install/#supported-platforms) 17.04.0-ce or higher, or [Docker EE](https://docs.docker.com/install/linux/docker-ee/centos/) 17.06.1 or higher.

        -   Windows: [Docker for Windows](https://docs.docker.com/docker-for-windows/install/).

    2.  Download [Docker Compose](https://docs.docker.com/compose/install/).

        **Note:** If installing Docker Compose on Windows, create a new environment variable called `COMPOSE_CONVERT_WINDOWS_PATHS` and set it to `1`. By doing this, you enable path conversion from Windows-style to Unix-style in volume definitions. For more information, see the [Docker Compose documentation](https://docs.docker.com/compose/reference/envvars/).

    3.  Initialize a swarm by running the following command:

        ```
        docker swarm init
        ```

2.  Download the Remediate [Docker Compose file](https://storage.googleapis.com/remediate/stable/latest/docker-compose.yml) to the same directory as your license.

    **Note:** If you want to manually validate the signature, see **Verify Docker Compose file** for more information.

3.  Run the following command ⁠\(replacing `your-license.json` with your own license\):

    ```
    docker-compose run remediate start --license-file your-license.json
    ```

    The container images are pulled from the Google Cloud Registry.

4.  To check that all the images have downloaded and that the containers have started running, run the following command:

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

5.  To access Remediate on a local workstation, the URL is `[https://localhost:8443](https://localhost:8443/)`, or port `8443` on the host where you installed Remediate.

6.  Read and accept the software license agreement.

7.  Sign in to Remediate.

    For default usernames and passwords, see **Managing user access**.


**Parent topic:**[Installing Remediate](installing_remediate.md)

**Related information**  


[System requirements](system_requirements.md)

[Install Remediate on offline nodes](installing_remediate_on_offline_nodes.md)

[Verify Docker Compose file](verify_docker_compose_file.md)

[Managing user access](managing_user_access.md#)

