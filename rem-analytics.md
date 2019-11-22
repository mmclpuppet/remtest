---
author: Michael McLoughlin
---

# Analytics data collection

Puppet Remediate automatically collects data about how you use the product. If you want to opt out of providing this data, you can do so, either during or after installing.

## What data does Remediate collect?

When Puppet Remediate starts, and restarts, it collects the following information:

-   Browser name and version.
-   Device type.
-   Form submission events, but not form input data.
-   Anonymized IP address
-   Geographic data inferred by the anonymized IP address.
-   JavaScript exceptions.
-   Link, button, and form element clicks.
-   Operating system and version.
-   Page views.
-   Session durations and session details including:
    -   number and title of screens viewed
    -   screens arrived at
    -   exit screens

## How does Puppet use the data?

The data we collect is one of many methods we use for learning about our customers. For example, understanding how you navigate through the web interface can help us optimize the navigation so that you can complete your work faster. And, learning what kinds of data sources are used, helps us to prioritize new functionality like increasing how many resources we can discover for those sources.

## Opt out of before installing

Remediate does not collect any analytics data during the installation process. However, if you want to disable data collection before you start Remediate for the first time, run the following Docker Compose command from the folder where your `docker-compose.yml` file is located:

```
docker-compose run remediate config set-override analytics false
```

## Opt out after installing

If you have already installed Remediate, and want to disable data collection, run the following Docker Compose command from the folder where your `docker-compose.yml` file is located:

```
docker-compose run remediate config set-override analytics false
```

Restart Remediate to complete the update:

```
docker-compose run remediate restart
```

**Parent topic:**[Installing Remediate](installing_remediate.md)

