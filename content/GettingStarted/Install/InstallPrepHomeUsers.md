---
title: "Preparing for SCALE UI Configuration (Home Users)"
description: "Provides information home users need to complete the SCALE configuration using the SCALE UI."
weight: 7
aliases:
tags:
- scaleinstall
- scalemigrate
---

{{< toc >}}


SCALE users installing and configuring SCALE on their home server should follow the instructions in this article to prepare for their SCALE system deployment.

Support options available to assist you include the TrueNAS community forums, blog, Discord, and tutorials documented in the TrueNAS Documentation Hub.

Home users obtaining network equipment and Internet service access from either an Internet or cable service provider, can contact those support departments for assistance with SMTP and some network configuration addresses such as default gateways or DNS name server addresses.

### Physical Access
When in the same location as the hardware designated for the TrueNAS installation, you can connect a monitor and keyboard to the system to do the initial installation and configuration.
An additional USB port is required when using a USB storage device to install TrueNAS from <kbd>.iso</kbd> file.

### IPMI Access
Intelligent Platform Management Interface (IPMI) servers provide a way for system administrators to remotely access and control systems.
Through this remote access, administrators can install software, and configure or administer systems at the console level as though they are in the room with the server.
Home users with compatible hardware have the option to use an IPMI connection to remotely administer their system over the Internet.
To make this remote access possible you need an IPMI capable system or service:
* Assign an IP address to access to the controller in the TrueNAS system. 
* Set up your administrator credentials (user name and password) for access through the TrueNAS IPMI connections. 

### Network Access
{{< include file="/static/includes/NetworkInstallRequirementsSCALE.md" >}}
Home users obtaining network equipment and Internet service access from either an Internet or cable service provider, can contact the provider support departments for assistance with network addresses.
For SCALE support or assistance refer to the TrueNAS community forums, blog, or the Discord, or the tutorials included in the TrueNAS Documentation Hub.

### SMTP Access
Simple Mail Transfer Protocol (SMTP) service or servers allow for the transfer of electronic mail across an Internet connection. 
TrueNAS uses either SMTP to send mail from SCALE to either the administrator or designated individual email addresses for system alert notifications. 
Contact your Internet or cable service provider to obtain the SMTP addresses to allow TrueNAS to send emails from your network.

{{< taglist tag="scaleinstall" limit="10" title="Related Installation Articles" >}}
{{< taglist tag="scalemigrate" limit="10" title="Related Migration Articles" >}}
