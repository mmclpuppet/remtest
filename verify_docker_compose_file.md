---
author: Claire Cadman <claire.cadman@puppet.com\>
---

# Verify Docker Compose file

With each Puppet Remediate release, a digital signature is created using the private key portion of an asymmetric key. You can manually validate the signature using the public key portion of the same asymmetric key. 

1.  Download the [signature](https://storage.googleapis.com/remediate/stable/latest/signature) file and the [public key](https://storage.googleapis.com/remediate/puppet-remediate-signing-key.pub) to the same directory as your `docker-compose.yml` and license file.

    **Note:** For instructions on downloading the `docker-compose.yml` and license files, see the instructions on how to **Install Remediate on online nodes**.

2.  Run the following command:

    ```
    openssl dgst -sha256 -verify puppet-remediate-signing-key.pub -signature signature docker-compose.yml
    ```

    If the signature is valid, you will get the following response:

    ```
    Verified Ok
    ```


**Parent topic:**[Installing Remediate](installing_remediate.md)

**Related information**  


[Install Remediate on online nodes](install_remediate.md)

[Install Remediate on offline nodes](installing_remediate_on_offline_nodes.md)

