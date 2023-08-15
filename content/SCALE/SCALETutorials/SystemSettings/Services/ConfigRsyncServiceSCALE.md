---
title: "Configuring Rsync Modules"
description: "Provides information on configuring an rsync module and TCP port to use as an alternative to SSH when communicating with TrueNAS as a remote rsync server."
weight: 35
alias: 
tags:
- scalersync
---

{{< toc >}}

{{< include file="content/_includes/SCALEServiceDeprecationNotice.md" type="page" >}}

{{< hint type="important" >}}
This service is not needed when rsync is configured externally with SSH or with the [TrueNAS built-in rsync task in SSH mode]({{< relref "RsyncTasksSCALE.md" >}}).
It is always recommended to use rsync with SSH as a security best practice.
{{< /hint >}}

When necessary to enable an rsync server with modules, go to **Apps > Available Applications** and [install the new **rsyncd** application]({{< relref "Rsyncd.md" >}}).

Rsync is a utility that copies data across a network. The **Services > Rsync** screen has two tabs: **Configure** and **Rsync Module**. 
Use the **Configure** screen to add the TCP port number for the rsync service. Port 22 is reserved for TrueNAS. 

Use the **Rsync Module** screen to configure an rsync module on a TrueNAS system.
You must configure at least one rsync module for the service to function.

## Adding an Rsync Module TCP Port

Go to **Services** and click the **Configure** icon for **Rsync** to open the **Configure** screen.

{{< trueimage src="/images/SCALE/22.12/ServicesRsyncConf.png" alt="Services Rsync Configure Screen" id="Services Rsync Configure Screen" >}}

Enter a new port number if not the default in **TCP Port**. This is the port the rsync server listens on.

Enter any additional parameters from [rsyncd.conf(5)](https://www.samba.org/ftp/rsync/rsyncd.conf.html) you want to use in **Auxiliary Parameters**. 

Click **Save**.

## Adding an Rsync Module 

To configure an rsync module click **Add** or **Add Rsync Modules** on the **Services > Rsync > Rsync Module** screen. 

{{< trueimage src="/images/SCALE/22.12//ServicesRsyncCreateModule.png" alt="Rsync Module No Rsync Module" id="Rsync Module No Rsync Module" >}}

Click either **Add RSYNC Modules** if a remote module does not exist, or **Add** to open the **Add Rsync** screen to configure a module to use as the mode. 

{{< trueimage src="/images/SCALE/22.12/AddRsyncModuleGeneral.png" alt="Services Add Rsync Module General Settings" id="Services Add Rsync Module General Settings" >}}

Enter a name, and then either enter the path or use the <span class="material-icons">arrow_right</span> to the left of <span class="material-icons">folder</span>**/mnt** to browse to the pool or dataset to store received data.
Click on the dataset or zvol name to populate the path field.
To collapse the dataset tree, click the <span class="material-icons">arrow_right</span> to the left of <span class="material-icons">folder</span>**/mnt** again.

Select **Enable** to activate the module for use with the rsync service.

{{< trueimage src="/images/SCALE/22.12/AddRsyncModuleAccess.png" alt="Services Add Rsync Module Access Settings" id="Services Add Rsync Module Access Settings" >}}

Select the permission access level in **Access Mode**.

Select the user and group that runs the rsync command during file transfer to and from this module.

Enter any allow and or deny hosts.
Separate multiple entries by pressing <kbd>Enter</kbd> after each entry in **Hosts Allow** and/or **Hosts Deny**.

{{< hint type=note >}}
When a **Hosts Allow** list is defined, *only* the IPs and hostnames on the list are able to connect to the module.
{{< /hint >}}

{{< trueimage src="/images/SCALE/22.12/AddRsyncModuleOtherOptions.png" alt="Services Add Rsync Module Other Options Settings" id="Services Add Rsync Module Other Options Settingse" >}}

Enter any additional rsync configuration parameters from [rsyncd.conf(5)](https://www.samba.org/ftp/rsync/rsyncd.conf.html) in **Auxiliary Parameters**.

Click **Save**.

{{< taglist tag="scalersync" limit="10" >}}