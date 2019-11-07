---
author: Claire Cadman <claire.cadman@puppet.com\>
---

# Troubleshooting

Use this section to troubleshoot issues with your Puppet Remediate installation.

## Forgotten password

We do not currently support resetting individual passwords. If you forget the admin password, you must reset the entire system and re-enter any provider and credential information. To reset, run the following command:

```
docker-compose run remediate reset
```

## How to generate and send logs to support

To generate service logs, create a tarball by running the mayday command:

```
docker-compose run remediate mayday
```

The tarball contains debug information which the Puppet support team uses for troubleshooting. You can send this to support via a Zendesk ticket or email.

## For general help

For a list of helpful CLI commands, run the following:

```
docker-compose run remediate --help
```

