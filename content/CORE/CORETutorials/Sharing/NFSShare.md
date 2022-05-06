---
title: "Share Creation"
weight: 10
---

{{< toc >}}

Creating a Network File System (NFS) share on TrueNAS gives the benefit of making lots of data easily available for anyone with share access.
Depending how the share is configured, users accessing the share can be restricted to read or write privileges.

To create a new share, make sure a dataset is available with all the data for sharing.

## Creating an NFS Share

Go to **Sharing > Unix Shares (NFS)** and click **ADD**.

![Services NFS Add](/images/CORE/12.0/SharingNFSAdd.png "Services NFS Add")

Use the file browser to select the dataset to share.
Enter an optional **Description** to help identify the share.
Clicking **SUBMIT** creates the share.
At the time of creation, you can select **ENABLE SERVICE** for the service to start and to automatically start after any reboots.
If you wish to create the share but not immediately enable it, select **CANCEL**.

![Services NFS Add Service Enable](/images/CORE/12.0/SharingNFSAddServiceEnable.png "Services NFS Add Service Enable")

![Services NFS Service Enable Success](/images/CORE/12.0/SharingNFSAddServiceEnableSuccess.png "Services NFS Add Service Enable Success")

### NFS Share Settings

See [Sharing NFS Screen]({{< relref "/CORE/UIReference/Sharing/NFS/NFSShareScreen.md" >}}) for more information on NFS share settings.

To edit an existing NFS share, go to **Sharing > Unix Shares (NFS)** and click <i class="material-icons" aria-hidden="true" title="Options">more_vert</i> **> Edit**.
The options available are identical to the share creation options.

## Configure the NFS Service

To begin sharing the data, go to **Services** and click the **NFS** toggle.
If you want NFS sharing to activate immediately after TrueNAS boots, set **Start Automatically**.

NFS service settings can be configured by clicking <i class="fa fa-pen" aria-hidden="true" title="Configure"></i> (Configure).

See [Service NFS screen]({{< relref "/CORE/UIReference/Services/NFSScreen.md" >}})

Unless a specific setting is needed, it is recommended to use the default settings for the NFS service.
When TrueNAS is already connected to [Active Directory]({{< relref "/CORE/UIReference/DirectoryServices/ActiveDirectory.md" >}}), setting **NFSv4** and **Require Kerberos for NFSv4** also requires a [kerberos keytab]({{< relref "/CORE/UIReference/DirectoryServices/Kerberos.md#kerberos-keytabs" >}}).

## Connecting to the NFS Share with a Linux/Unix OS

Although you can connect to an NFS share with various operating systems, it is recommended to use a Linux/Unix operating system.
First, download the `nfs-common` kernel module.
This can be done using the package manager of the installed distribution.
For example, on Ubuntu/Debian, enter `sudo apt-get install nfs-common` in the terminal.

After installing the module, connect to an NFS share by entering `sudo mount -t nfs {IPaddressOfTrueNASsystem}:{path/to/nfsShare} {localMountPoint}`, where *{IPaddressOfTrueNASsystem}* is the IP address of the remote TrueNAS system that contains the NFS share, *{path/to/nfsShare}* is the path to the NFS share on the TrueNAS system, and *{localMountPoint}* is a local directory on the host system configured for the mounted NFS share.
For example, `sudo mount -t nfs 10.239.15.110:/mnt/pool1/photoDataset /mnt` mounts the NFS share *photoDataset* to the local directory `/mnt`.

By default, anyone that connects to the NFS share only has the read permission.
To change the default permissions, edit the share, open the **Advanced Options**, and change the **Access** settings.

{{< hint warning >}}
ESXI 6.7 or later is required for read/write functionality with NFSv4 shares.
{{< /hint >}}
