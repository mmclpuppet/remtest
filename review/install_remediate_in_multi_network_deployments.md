---
author: Claire Cadman <claire.cadman@puppet.com\>
---

# Install Remediate in multi-network deployments

Puppet Remediate connects to security providers to discover hosts with vulnerabilities. To take action and fix the vulnerabilities, the system needs to connect directly to the hosts. If the host you want to fix is deployed in different network segments that are not directly accessible from where you installed Remediate, you can setup a multi-network deployment.

In a multi-network deployment, an edge service is deployed inside each network segment. Remediate instructs the edge to connect to the hosts when executing tasks, and then leverages Docker swarm to deploy an edge service on each swarm worker. Workers must have direct connectivity to the manager ⁠— the main node where you installed Remediate. For more information on workers and managers, see the [Docker documentation](https://docs.docker.com/engine/swarm/how-swarm-mode-works/nodes/).

For more information on installing Remediate on nodes that are not connected to the internet, see instructions on how to **Install Remediate on offline nodes**.

1.  Set up a Docker swarm environment.

    1.  On the node you want to be the manager, run:

        ```
        docker swarm init
        ```

    2.  To add a manager to the swarm, run the following command and follow the instructions:

        ```
        docker swarm join-token manager
        ```

2.  Using the key output from the above command as the token, run the following command on each of the workers:

    ```
    docker swarm join --token 
    ```

    This command adds a worker to each network segment.

3.  On the manager node, follow the normal installation instructions for Remediate. The swarm automatically deploys the edge on the workers.

4.  After the installation is complete, verify the expected number of edges is running with the following command:

    ```
    docker service ps remediate_remote-edge 
    ```


**Parent topic:**[Installing Remediate](installing_remediate.md)

**Related information**  


[Install Remediate on offline nodes](installing_remediate_on_offline_nodes.md)

