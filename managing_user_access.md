---
author: Eamonn Smith <eamonn.smith@puppet.com\>
---

# Managing user access

Use role-based access control \(RBAC\) in Puppet Remediate to ensure that each user has the access and permissions appropriate to their role on the team.

The "role" in role-based access control refers to a system of user roles, and each role contains permissions which define what a user can or can't do within Remediate. There are two default user roles: Administrator and Viewer.

|Role|Username|Default password|Permissions|
|----|--------|----------------|-----------|
|Administrator|admin|@Admin|-   Add and remove sources and credentials.

-   Upload scripts and modules.

-   Run tasks.

-   View dashboards.

-   View all node, package, container listing and details pages.


|
|Viewer|viewer|@Admin|-   View dashboards.

-   View all node, package, container listing and details pages.


|

To change the default passwords, run the following commands:

```
docker-compose run remediate set-admin-password
```

```
docker-compose run remediate set-viewer-password
```

## Discovery events

The Recent events page provides the following information about each discovery run which, by default, occurs every 4 hours.

|Event detail|Description|
|------------|-----------|
|Total jobs|Total number of jobs relating to the discovery event. Each discovery event has two jobs:-   Discover the node.

-   Discover resources on the node.


|
|Failed|Total number of failed jobs.|
|Status|The event status.|
|Started|Date and time the discovery run started.|
|Status|The job status: -   Succeeded

-   Failed

-   Pending

-   Running


|
|Source|Your configured source: vulnerability scanner or infrastructure source.|
|Job details|The number of facets discovered. Each facet represents a set of related attributes, each one independently maintained, that describe a certain aspect of a discovered resource; node, package, or container.|
|Completion time|The time the discovery run completed.|

## Tasks events

The Task event page provides the following information about the task that was ran on nodes.

|Event detail|Description|
|------------|-----------|
|Total jobs|Total number of jobs relating to the task event. Each task event has two jobs:-   Run task on node.

-   Discover resources on the node.


|
|Failed|Total number of failed jobs.|
|Status|The event status.|
|Started|Date and time the event started.|
|Status|The job status: -   Succeeded

-   Failed

-   Pending

-   Running


|
|Source|Your configured source: vulnerability scanner or infrastructure source.|
|Job details|The command output from running the task and the number of facets discovered. Each facet represents a set of related attributes, each one independently maintained, that describe a certain aspect of a discovered resource; node, package, or container.|
|Completion time|The time the task completed.|

