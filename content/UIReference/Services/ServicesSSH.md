---
title: "SSH Screen"
description: "Describes the SSH screen in TrueNAS CORE."
weight: 130
tags:
- ftp
- tftp
- sftp
- ssh
---

Secure Socket Shell (SSH) is a network communication protocol. It provides encryption to secure data. Use the SSH services screen to configure SSH File Transfer Protocol (SFTP). SFTP is available by enabling SSH remote access to the TrueNAS system. 

{{< hint type=important >}}
Allowing external connections to TrueNAS is a security vulnerability!
Enable SSH only when there is a need for external connections.
See [Security Recommendations](https://www.truenas.com/docs/solutions/optimizations/security/) for more security considerations when using SSH.
{{< /hint>}}

![SSHBasicOptionsScreen](/images/CORE/Services/SSHBasicOptionsScreen.png "SSH Basic Options")

{{< include file="/static/includes/ServicesSSHFields.md" markdown="true" >}}

**ADVANCED OPTIONS** displays additional configuration fields to set up SSH for specific uses cases. 

![SSHAdvancedOptionsScreen](/images/CORE/Services/SSHAdvancedOptionsScreen.png "SSH Advanced Options")

{{< include file="/static/includes/ServicesSSHAdvancedFields.md" markdown="true" >}}
