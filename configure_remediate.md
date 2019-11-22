---
author: Eamonn Smith <eamonn.smith@puppet.com\>
---

# Configuring Remediate

After installing Puppet Remediate, configure and administer the application by using the command line interface \(CLI\).

## Command line options

The CLI provides additional administrative and troubleshooting options beyond the user interface.

```
docker-compose run remediate [command]
```

|Command|Description|
|-------|-----------|
|config|View and modify the configuration.Usage:

 ```
docker-compose run remediate config [command]
```

 The following commands are used with the config command:

 -   get-compose-file
-   set-override
-   unset-override
-   view

|
|config get-compose-file|Gets the docker compose file.Usage:

 ```
docker-compose run remediate config get-compose-file [flags]
```

 In addition to the available global flags, you can use the following flag with the config get-compose-file command:

 -   --filename string - The filename to output the docker compose file to. \(default: `remediate-docker-compose.yml`\).

|
|config set-override|Set configuration override for Puppet Remediate \(requires restart\).Usage:

 ```
docker-compose run remediate config set-override [key] [value] [flags]
```

 See **Configuration overrides** below for more information about how to use this command.

|
|config unset-override|Unset configuration override for Puppet Remediate \(requires restart\).Usage:

 ```
docker-compose run remediate config unset-override [key] [value] [flags]
```

 See **Configuration overrides** below for more information about how to use this command.

|
|config view|View configuration for Puppet Remediate.Usage:

 ```
docker-compose run remediate config view [flags]
```

|
|export|Export the Remediate images to a tar file.Usage:

 ```
docker-compose run remediate export [flags]
```

|
|generate-docs|Generates the CLI documentation.Markdown files are created at the specified path detailing the CLI commands.

 Usage:

 ```
docker-compose run remediate generate-docs [path] [flags]
```

|
|help|Displays the help commands.Usage:

 ```
docker-compose run remediate help [command] [flags]
```

|
|import|Import the Remediate images from a tar file.Usage:

 ```
docker-compose run remediate import [flags]
```

 In addition to the available global flags, you can use the following flag with the import command:

 -   --config string The config file \(default is `$HOME/.installer.yaml`\) \(default: `.installer.yml`\)

|
|logs|Displays the application service logs.Usage:

 ```
docker-compose run remediate logs [flags]
```

 In addition to the available global flags, you can use the following flags with the logs command:

 -   --service string - Display logs for only this service.
-   --since string - Show logs since timestamp \(e.g. 2013-01-02T13:23:37\) or relative \(e.g. 42m for 42 minutes\) \(default "4h"\).

**Note:** By default the logs command returns logs for the last 8 hours only. Use the --since flag to return logs for a time period different from the default.


|
|mayday|Creates a mayday tarball containing debug information for troubleshooting with the Puppet support team.Usage:

 ```
docker-compose run remediate mayday [flags]
```

 In addition to the available global flags, you can use the following flag with the mayday command:

 -   --since string - Show logs since timestamp \(e.g. 2013-01-02T13:23:37\). You can also use an integer with m or h. For example. 42m for 42 minutes, or 1h for 1 hour. The default is "4h".

|
|reset|Deletes sources, credentials, user passwords, and resets the application to an uninstalled state.Usage:

 ```
docker-compose run remediate reset [flags]
```

 In addition to the available global flags, you can use the following flag with the reset command:

 -   --quietly - Hides the splash screen.

|
|restart|Restarts the application.Usage:

 ```
docker-compose run remediate restart [flags]
```

 In addition to the available global flags, you can use the following flag with the restart command:

 -   --quietly - Hides the splash screen.

|
|set-admin-password|Updates the current admin password.Usage:

 ```
docker-compose run remediate set-admin-password [flags]
```

|
|set-viewer-password|Updates the current viewer password.Usage:

 ```
docker-compose run remediate set-viewer-password [flags]
```

|
|set-license|Sets a new license. Usage:

 ```
docker-compose run remediate set-license [license-file] [flags]
```

 In addition to the available global flags, you can use the following flag with the set-license command:

 -   --quietly - Hides the splash screen.

|
|start|Initializes and starts the application.Usage:

 ```
docker-compose run remediate start [flags]
```

 In addition to the available global flags, you can use the following flags with the start command:

 -   --license-file string - License file \(default is `$PWD/license.json`\)
-   --quietly - Hides the splash screen.

|
|stop|Stops the application.Usage:

 ```
docker-compose run remediate stop [flags]
```

 In addition to the available global flags, you can use the following flag with the stop command:

 -   --quietly - Hides the splash screen.

|
|update|Updates to the latest version. Usage:

 ```
docker-compose run remediate update [flags]
```

 In addition to the available global flags, you can use the following flags with the update command:

 -   --quietly - Hides the splash screen.
-   --version string - Version to update to \(default "latest"\).

 The update command also be used with the list sub-command or with its own local flags.

|
|update list|Shows a list of available versions.Usage:

 ```
docker-compose run remediate update list [flags]
```

|

## Global flags

In addition to the flags that can be used with individual commands, the following flags can be used with all commands:

|Flag|Description|
|----|-----------|
|--config string|Config file \(default is $HOME/.installer.yaml\) \(default ".installer.yml"\)|
|-h, --help|Help for remediate

 Use remediate \[command\] --help to get more information about a command.

|

## Configuration overrides

After installing Remediate, optimize the application for your environment by configuring and tuning settings as needed.

To view the current configuration:

```
docker-compose run remediate config view
```

To override a configuration key:

```
docker-compose run remediate config set-override [key] [value]
```

To reset a configuration key:

```
docker-compose run remediate config unset-override [key] [value]
```

|Key|Description|Default value|
|---|-----------|-------------|
|controller.DiscoveryInterval|The interval between each discovery run.|every 4h|
|controller.loglevel|The logging levels for the controller container.|INFO \(default\)

 DEBUG

 WARN

 ERROR

 FATAL

 PANIC

|
|edge.discoworkers|The maximum number of discovery processes that run in parallel.|512|
|edge.taskworkers|The maximum number of tasks that run in parallel.|32|
|edge.workertimeout|The time out value, in minutes, for each job.|25|
|edge.loglevel|The logging levels for the edge container.|WARN \(default\)

 INFO

 DEBUG

 ERROR

 FATAL

 PANIC

|
|ingress.ipv6enabled|Enable IPv6 on ingress.|true|
|pdp.tll|The interval, in minutes, that checks are made for resources older than the \(time-to-live\) TLL interval.|60|
|pdp.tllWindow|The TLL interval before resources are deleted.|12h|

