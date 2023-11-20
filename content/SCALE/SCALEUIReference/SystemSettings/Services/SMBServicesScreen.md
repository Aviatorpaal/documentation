---
title: "SMB Service Screen"
description: "Provides information in the SMB service screen and settings."
weight: 50
aliases: /scale/scaleuireference/shares/smb/smbservicesscreen/
tags:
 - smb
 - services
---

{{< toc >}}

The **SMB Services** screen displays setting options to configure TrueNAS SMB settings to fit your use case.
The **Basic Options** settings continue to display after selecting the **Advanced Options** screen.

{{< trueimage src="/images/SCALE/SystemSettings/SMBServiceOptionsSCALE.png" alt="SMB Service Basic Options" id="SMB Service Basic Options" >}}

Click **Save** or **Cancel** to close the configuration screen and return to the **Services** screen.

## Basic Options Settings

{{< truetable >}}
| Setting | Description |
|---------|-------------|
| **NetBIOS Name** | Automatically populated with the original system host name. The name is limited to 15 characters and cannot be the **Workgroup** name. |
| **NetBIOS Alias** | Enter any alias name up to 15 characters long. Separate alias names with a space between them. |
| **Workgroup** | Enter a name that matches the Windows workgroup name. If you do not configure a Workgroup, but Active Directory or LDAP is active, TrueNAS detects and sets the correct workgroup from these services. |
| **Description** | (Optional) Enter any notes or descriptive details about the service configuration. |
| **Enable SMB1 support** | Select to allow legacy SMB1 clients to connect to the server. Note: SMB1 is deprecated. We advise you to upgrade clients to operating system versions that support modern SMB protocol versions. |
| **NTLMv1 Auth** | Off by default. Select to allow [smbd](https://www.samba.org/samba/docs/current/man-html/smbd.8.html) attempts to authenticate users with the insecure and vulnerable NTLMv1 encryption. This setting allows backward compatibility with older versions of Windows, but we don't recommend it. Do not use on untrusted networks. |
{{< /truetable >}}

## Advanced Options Settings
The **Basic Options** settings also display on the **Advanced Options** settings screen with the **Other Options** settings.

{{< trueimage src="/images/SCALE/SystemSettings/SMBServiceAdvanced1.png" alt="SMB Service Advanced Options" id="SMB Service Advanced Options" >}}

{{< truetable >}}
| Setting | Description |
|---------|-------------|
| **UNIX Charset** | Select the character set to use internally from the dropdown list of options. **UTF-8** is standard for most systems as it supports all characters in all languages. |
| **Log Level** | Record SMB service messages up to the specified log level from the dropdown list. Options are **None**, **Minimum**, **Normal**, **full** and **Debug**. By default, TrueNAS logs error and warning-level messages. We don't recommend using a log level above **Minimum** for production servers. |
| **Use Syslog Only** | Select to log authentication failures in */var/log/messages* instead of the default */var/log/samba4/log.smbd*. |
| **Local Master** | Selected by default and determines if the system participates in a browser election. Clear this checkbox when the network contains an AD or LDAP server or when Vista or Windows 7 machines are present. |
| **Enable Apple SMB2/3 Protocol Extensions** | Select to allow MacOS to use these [protocol extensions](https://support.apple.com/en-us/HT210803) to improve the performance and behavioral characteristics of SMB shares. TrueNAS requires Apple SMB2/3 Protocol Extensions for Time Machine support. |
| **Multichannel** | SMB multichannel allows servers to use multiple network connections simultaneously by combining the bandwidth of several network interface cards (NICs) for better performance. SMB multichannel does not function if you combine NICs into a LAGG. |
| **Administrators Group** | Enter or select members from the dropdown list. Members of this group are local administrators and automatically have privileges to take ownership of any file in an SMB share, reset permissions, and administer the SMB server through the Computer Management MMC snap-in. |
{{< /truetable >}}

{{< trueimage src="/images/SCALE/SystemSettings/SMBServiceAdvanced2.png" alt="SMB Service Advanced Options (continued)" id="SMB Service Advanced Options (continued)" >}}

{{< truetable >}}
| Setting | Description |
|---------|-------------|
| **Guest Account** | Select the account for guest access from the dropdown list. The default is **nobody**. The selected account must have permission for the shared pool or dataset. To adjust permissions, edit the dataset Access Control List (ACL), add a new entry for the chosen guest account, and configure the permissions in that entry. If you delete the selected **Guest Account**, the field resets to **nobody**. |
| **File Mask** | Overrides default **0666** file creation mask, which creates files with read and write access for everybody. |
| **Directory Mask** | Overrides default directory creation mask of **0777**, which grants everyone directory read, write, and execute access. |
| **Bind IP Addresses** | Select static IP addresses that SMB listens on for connections from the dropdown list. Leaving all unselected defaults to listening on all active interfaces.
| **Auxiliary Parameters** | Enter additional [smb.conf](https://www.samba.org/samba/docs/current/man-html/smb.conf.5.html) options. Refer to the [Samba Guide](http://www.oreilly.com/openbook/samba/book/appb_02.html) for more information on these settings. You can use **Auxiliary Parameters** to override the default SMB server configuration, but such changes could adversely affect SMB server stability or behavior. To log more details when a client attempts to authenticate to the share, add `log level = 1, auth_audit:5`. |
{{< /truetable >}}
