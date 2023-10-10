---
title: "Interface"
description: "Provides information about the network interface namespace in the TrueNAS CLI. Includes command syntax and common commands."
weight: 30
aliases:
draft: false
tags:
- scaleclinetwork
book: SCALECLIReference
---

{{< toc >}}


{{< include file="/_includes/CLIGuideWIP.md" >}}

## Interface Commands

The **interface** namespace has 24 commands based on functions found in the SCALE API and web UI. 
These commands return interface and options by type (bridge, VLAN, etc.), allow you to add or manage settings, get interface and IP address information, and commit or roll back network changes for interfaces on the system. 
Options can vary by the type of system and license applied (i.e., an HA system). 

You can enter commands from the main CLI prompt or from a **network** namespace prompt.

### Interfaces

This section covers assigning an IP address to a network interface.

Enter `network interface`.

If you do not already know the interface you want to configure, enter `query` to display a list of all physical network interfaces.

![TrueNASCLInetworkinterfacequery](/images/SCALE/CLI/TrueNASCLInetworkinterfacequery.png "Network Interface Query")

To edit the interface, enter `update interfacename aliases=["ipaddress/subnetmask"] ipv4_dhcp=false`

The CLI displays the message: "You have pending network interface changes. Please run 'network interface commit' to apply them."

Enter `commit` to apply the changes, then enter `checkin` to make them permanent. 

![TrueNASCLIupdateinterfacealiases](/images/SCALE/CLI/TrueNASCLIupdateinterfacealiases.png "Update Interface Aliases")

Enter `query` to make sure the TrueNAS applies the changes successfully.

Enter `..` to exit `interface` and go up one level to the `network` menu.


{{< taglist tag="scaleclinetwork" categories="SCALE/GettingStarted,SCALETutorials,SCALEUIReference,SCALECLIReference,References,Solutions" limit="5" title="Related CLI Network Articles" >}}
