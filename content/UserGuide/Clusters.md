---
title: "Clusters"
description: "Option descriptions in the TrueCommand Clusters menu."
weight: 30
geekdocCollapseSection: true
tags:
 - clustering

---

{{< hint type="warning" title="Deprecated Feature" >}}
{{< include file="/content/_includes/ClusterDeprecated.md" >}}
{{< /hint >}}

This article describes the various screens used for clustering TrueNAS SCALE systems with TrueCommand.
If you want to create and integrate clusters, see [Clustering and Sharing SCALE Volumes with TrueCommand](https://www.truenas.com/docs/solutions/integrations/smbclustering/).

## Clusters

The **Clusters** screen contains all options related to the cluster feature.
To see this screen, log in to TrueCommand and click the <span class="iconify" data-icon="mdi:server-network"></span> **Clusters** icon in the upper left.

{{< trueimage src="/images/TrueCommand/Clusters/ClustersScreen.png" alt="TrueCommand Clusters Screen" id="TrueCommand Clusters Screen" >}}

{{< expand "Option descriptions (click to expand)" "v" >}}
If you have not created a cluster, there is a single option on this screen:

{{< truetable >}}
| Setting | Description |
|---------|-------------|
| **CREATE CLUSTER** | Opens the form to create a new cluster. |
{{< /truetable >}}

{{< /expand >}}

### Create Cluster

The cluster creation options split into two pages: **Systems** and **Confirmation**.

#### Systems

The initial form has two fields:

{{< trueimage src="/images/TrueCommand/Clusters/CreateClusterSystems.png" alt="Configuring Systems in the Cluster" id="Configuring Systems in the Cluster" >}}

{{< expand "Option descriptions (click to expand)" "v" >}}

{{< truetable >}}
| Setting | Description |
|---------|-------------|
| **Name** | Enter a string to identify the cluster. |
| **Systems** | Dropdown list shows all connected TrueNAS SCALE systems available for this cluster. Clusters can consist of between 3 and 20 individual SCALE systems. |
{{< /truetable >}}

{{< /expand >}}

Making selections in the **Systems** field adds more options.

{{< trueimage src="/images/TrueCommand/Clusters/CreateClusterSystemsNetwork.png" alt="Network Options for Clustered Systems" id="Network Options for Clustered Systems" >}}

{{< expand "Option descriptions (click to expand)" "v" >}}

{{< truetable >}}
| Setting | Description |
|---------|-------------|
| **Delete** | Clicking the  <i class="material-icons" aria-hidden="true" title="Delete">delete</i> **Delete** icon removes the system from the cluster. |
| **Network Address** | Dropdown list shows available IP addresses to use for cluster traffic. Using private dedicated network addresses is recommended. |
{{< /truetable >}}

{{< /expand >}}

#### Confirmation

There is a single option on this page.

{{< trueimage src="/images/TrueCommand/Clusters/CreateClusterReview.png" alt="Review and create page for Clusters" id="Review and create page for Clusters" >}}

{{< expand "Option descriptions (click to expand)" "v" >}}

{{< truetable >}}
| Setting | Description |
|---------|-------------|
| **CREATE** | Begins creating the cluster, which restricts the SMB functionality on the SCALE systems. |
{{< /truetable >}}

{{< /expand >}}

### Configure Cluster

Successfully creating a cluster adds a cluster widget to the **Clusters** screen and opens options to configure the new cluster.
These options are split into four screens: **VIPs**, **Associate VIPs**, **Active Directory**, and **Confirmation**.

#### VIPs

The VIPs page has options and fields added for each SCALE system in the cluster.

{{< trueimage src="/images/TrueCommand/Clusters/ConfigureClusterSMBNetwork.png" alt="Configure Cluster SMB Network" id="Configure Cluster SMB Network" >}}

{{< truetable >}}
| Setting | Description |
|---------|-------------|
| **ADD** | Adds another line under VIPs for IPs and netmasks. |
| **Address** | Virtual IP address for one of the cluster systems. |
| **Netmask** | Netmask for the IP address. |
{{< /truetable >}}

#### Associate VIPs

The Associate VIPs page allows you to select interfaces to assign to the VIPs.

{{< trueimage src="/images/TrueCommand/Clusters/ConfigureClusterAssociateVIPs.png" alt="Configure Associate VIPs" id="Configure Associate VIPs" >}}

{{< truetable >}}
| Setting | Description |
|---------|-------------|
| **Interface** | Select an interface from the dropdown list of interface options and assign it to the VIP. |
{{< /truetable >}}

#### Active Directory

The options on this page let you establish a connection between an Active Directory environment, SCALE systems, and TrueCommand.

{{< trueimage src="/images/TrueCommand/Clusters/ConfigureClusterActiveDirectory.png" alt="Configure Cluster Active Directory Connection" id="Configure Cluster Active Directory Connection" >}}

{{< expand "Option descriptions (click to expand)" "v" >}}

{{< truetable >}}
| Setting | Description |
|---------|-------------|
| **Domain Name** | Enter a string for the Microsoft Active Directory (AD) environment host name.
| **NetBIOS** | Automatically populates with the cluster name. |
| **Username** | Enter a string for the account credential to establish the AD connection. You must use an account with administrative access. |
| **Password** | Enter a string for the account credential to establish the AD connection. You must use an account with administrative access. |
{{< /truetable >}}

{{< /expand >}}

#### Confirmation

All chosen settings display here for you to confirm before being applied to the cluster.

{{< trueimage src="/images/TrueCommand/Clusters/ConfigureClusterReview.png" alt="Configure Cluster: Review and confirm" id="Review and Confirm" >}}

{{< expand "Option descriptions (click to expand)" "v" >}}

{{< truetable >}}
| Setting | Description |
|---------|-------------|
| **CONFIRM** | Saves the configuration settings and permanently apply them to the cluster. |
{{< /truetable >}}

{{< /expand >}}

## Manage Clusters

Clusters display as standalone cards.

{{< trueimage src="/images/TrueCommand/Clusters/ClusterCard.png" alt="TrueCommand Cluster View" id="TrueCommand Cluster View" >}}

The card displays the name of the cluster, the current state, and the names of the systems used in the cluster (**Nodes**).
Click the <i class="material-icons" aria-hidden="true" title="Options">more_vert</i> **Options** icon to see management options for the cluster.
Click the **^** or **v** icons to minimize or expand (respectively) the list of nodes.

{{< expand "Option descriptions (click to expand)" "v" >}}

{{< truetable >}}
| Setting | Description |
|---------|-------------|
| **CREATE VOLUME** | Opens the form to create new clustered storage. |
| **Rename** | Opens the form to enter a new **Cluster Name**. |
| **Delete** | Disconnects each SCALE system from the cluster and removes the card from TrueCommand. Shows a confirmation popup when clicked. |
{{< /truetable >}}

{{< /expand >}}

## Cluster Volumes

Clicking **CREATE VOLUME** for an existing cluster shows options to configure new clustered storage.
The options split into two pages: **Details** and **Confirmation**.

### Details

{{< trueimage src="/images/TrueCommand/Clusters/ClustersCreateVolumeDetails.png" alt="Add Cluster Volume: Details" id="Details" >}}

{{< expand "Option descriptions (click to expand)" "v" >}}

{{< truetable >}}
| Setting | Description |
|---------|-------------|
| **Name** | Enter a string as an identifying label for this cluster volume. |
| **Type** | Dropdown list. Select the layout and behavior for the volume. |
| **Cluster** | String (disabled). Shows the cluster that controls the new volume. |
| **Brick Size** | Enter an integer and select from the dropdown list to define storage capacity. Allows numeric values and selecting units of size. |
| **Pools** | Dropdown list. Select a storage pool on the individual SCALE system that provides capacity for the cluster volume. |
{{< /truetable >}}

The **Type** field has four options:

{{< include file="/content/_includes/ClusterTypes.md" >}}

{{< /expand >}}

### Confirmation

The **Confirmation** page shows details for the chosen volume **Type** and storage makeup of the new clustered volume.

{{< trueimage src="/images/TrueCommand/Clusters/ClustersCreateVolumeConfirmation.png" alt="Add Cluster Volume: Review and create" id="Review and Create" >}}

{{< expand "Option descriptions (click to expand)" "v" >}}

{{< truetable >}}
| Setting | Description |
|---------|-------------|
| **BACK** | Click the button to go to the previous configuration page. |
| **CREATE** | Click the button to save the configuration and build the clustered volume on each system in the cluster. |
{{< /truetable >}}

{{< /expand >}}

## Managing Cluster Volumes

Created cluster volumes display in the related cluster card.

{{< trueimage src="/images/TrueCommand/Clusters/ClusterCardwithVolume.png" alt="Cluster Volume added to a Cluster" id="Cluster Volume added to a Cluster" >}}

The card displays the name, used storage, and volume status.
Click the volume name to expand the details and see more management options.

{{< trueimage src="/images/TrueCommand/Clusters/ClustersClusterVolumeExpanded.png" alt="Cluster Volume Details" id="Cluster Volume Details" >}}

{{< expand "Option descriptions (click to expand)" "v" >}}

{{< truetable >}}
| Setting | Description |
|---------|-------------|
| **DELETE** | Click the button to remove the volume from the cluster and destroy stored data. |
| **CREATE SHARE** | Opens the form to configure a new SMB share for remote access to this cluster volume. |
{{< /truetable >}}

{{< /expand >}}

### Cluster Volume Sharing

Adding a cluster share shows a few options.

{{< trueimage src="/images/TrueCommand/Clusters/ClustersClusterVolumeExpandedCreateShare.png" alt="Add Cluster Share" id="Add Cluster Share" >}}

{{< expand "Option descriptions (click to expand)" "v" >}}

{{< truetable >}}
| Setting | Description |
|---------|-------------|
| **Cluster** | String (disabled). Shows the name of the cluster related to this share. |
| **Cluster Volume** | String (disabled). Shows the name of the cluster volume to share. |
| **Name** | Enter a string to create a label for this new cluster share. |
| **ACL** | Dropdown list. Access Control List. Choose permissions for the share. |
| **Readonly** | Checkbox disables or allows file management options for connected users. Select to disable. |
| **CONFIRM** | Click the button to save the settings, create the share, and make the cluster volume accessible to Active Directory user accounts. |
{{< /truetable >}}

**ACL Options**

* **POSIX_OPEN** - Grants read, write, and execute permissions to all users.
* **POSIX_RESTRICTED** - Grants read, write, and execute to owner and group, but not others. The template may optionally include the special-purpose 'builtin_users' and 'builtin_administrators' groups and Domain Users and Domain Admins groups in Active Directory environments.

{{< /expand >}}

#### Managing Cluster Volume Shares

Click the cluster volume name to open the **Cluster Volume Details** and see any shares.

{{< trueimage src="/images/TrueCommand/Clusters/ClustersClusterVolumeExpandedShareOptions.png" alt="Cluster Volume Share Options" id="Cluster Volume Share Options" >}}

{{< expand "Option descriptions (click to expand)" "v" >}}

{{< truetable >}}
| Setting | Description |
|---------|-------------|
| **DELETE** | Removes the share from the Cluster Volume. This operation does not destroy data. |
| **CREATE SHARE** | Opens the form to configure a new SMB share for remote access to this cluster volume. |
{{< /truetable >}}

{{< /expand >}}
