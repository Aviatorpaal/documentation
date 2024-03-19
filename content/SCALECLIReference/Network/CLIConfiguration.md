---
title: "Configuration"
description: "Provides information about the network configuration namespace in the TrueNAS CLI. Includes command syntax and common commands."
weight: 10
aliases:
draft: false
tags:
- scaleclinetwork
---

{{< toc >}}


{{< include file="/static/includes/CLIGuideWIP.md" >}}

## Configuration Commands

The **configuration** namespace has three commands that are based on functions found in the SCALE API and web UI. 
These commands return allowed network activity choices, configuration information, and allow you to change global network configuration settings. 
Options can vary by the type of system and license applied (i.e., an HA system). 

You can enter commands from the main CLI prompt or from a **network** namespace prompt.

### Activity_choices Command
The `activity_choices` command returns a list of system activities. 

{{< expand "Using activity_choices Command" "v" >}}
Press <kbd>Enter</kbd> after entering the command to display the list.

From the CLI prompt, enter:

`network configuration activity_choices`

From the network prompt, enter:

`configuration activity_choices`
{{< /expand >}}

### Config Command
The `config` command displays the current system configuration network settings. 

{{< expand "Using config Command" "v" >}}
Press <kbd>Enter</kbd> after entering the command to display the list.

From the CLI prompt, enter:

`network configuration config`

From the network prompt, enter:

`configuration config`
{{< /expand >}}
### Update Command

This section covers configuring the default gateway.

Enter `configuration` (or `network configuration` if you just opened the TrueNAS CLI Shell).

Enter `update ipv4gateway="ipaddress"`

If entered properly, your system networking is now configured.

{{< taglist tag="scaleclinetwork" limit="10" title="Related CLI Network Articles" >}}
