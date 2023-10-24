---
title: "Managing the System Configuration"
description: "Provides information on downloading your TrueNAS SCALE configuration to back up system settings, uploading a new configuration file, and resetting back to default settings."
weight: 15
aliases:
tags:
 - scalebackup
 - scalesettings
book: "SCALETutorials"
volume: "SCALE"
---


TrueNAS SCALE allows users to manage the system configuration by uploading or downloading configurations, or by resetting the system to the default configuration. 

## System Configuration Options

The **Manage Configuration** option on the **system Settings > General** screen provides three options:

* **Download File** that downloads your system configuration settings to a file on your system.
* **Upload File** that allows you to upload a replacement configuration file.
* **Reset to Defaults** that resets system configuration settings back to factory settings.

### Downloading the File
The **Download File** option downloads your TrueNAS SCALE current configuration to the local machine.

{{< include file="/content/_includes/DownloadSystemConfigFileSCALE.md" >}}

### Uploading the File
The **Upload File** option gives users the ability to replace the current system configuration with any previously saved TrueNAS SCALE configuration file.

{{< hint type=warning >}}
All passwords are reset if the uploaded configuration file was saved without the selecting **Save Password Secret Seed**.
{{< /hint >}}

### Resetting to Defaults

{{< enterprise >}}
Enterprise High Availability (HA) systems should never reset their system configuration to defaults.
Contact iXsystems Support if a system configuration reset is required.

{{< nest-expand "iXsystems Support" "v" >}}
{{< include file="content/_includes/iXsystemsSupportContact.md" >}}
{{< /nest-expand >}}
{{< /enterprise >}}

Save the current system configuration with the **Download File** option before resetting the configuration to default settings!
If you do not save the system configuration before resetting it, you could lose data that was not backed up, and you cannot revert to the previous configuration.

The **Reset to Defaults** option resets the system configuration to factory settings. 
After the configuration resets, the system restarts and users must set a new login password.

{{< taglist tag="scalesettings" vol="SCALE" limit="5" >}}
{{< taglist tag="scalebackup" vol="SCALE" limit="5" title="Related Backup Articles" >}}
