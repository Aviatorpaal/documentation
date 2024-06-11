---
title: "Apps"
description: "Expanding TrueNAS SCALE functionality with additional applications."
geekdocCollapseSection: true
weight: 100
aliases:
 - /scale/scaletutorials/apps/usingapps/
 - /scale/scaleuireference/apps/usingapps/
 - /scale/apps/usingapps/
tags:
- scaleapps
- scaledocker
---

{{< toc >}}

{{< include file="/static/includes/AppsUnversioned.md" >}}

## Configuring the Apps Service

The first time you open the **Applications** screen, it displays an <i class="fa fa-cog" aria-hidden="true"></i> **Apps Service Not Configured** status on the screen header.

{{< trueimage src="/images/SCALE/23.10/AppsServiceNotConfigured.png" alt="Apps Service Not Configured" id="Apps Service Not Configured" >}}

Click **Settings > Choose Pool** to choose a storage pool for Apps.

{{< trueimage src="/images/SCALE/23.10/AppsSettingsChoosePool.png" alt="Choosing a Pool for Apps" id="Choosing a Pool for Apps" >}}

We recommend keeping the application use case in mind when choosing a pool.
Select a pool with enough space for all the applications you intend to use.
For stability, we also recommend using SSD storage for the applications pool.

TrueNAS creates an *ix-applications* dataset on the chosen pool and uses it to store all container-related data.
The dataset is for internal use only.
Set up a new dataset before installing your applications if you want to store your application data in a location separate from other storage on your system.
For example, create the datasets for the Nextcloud application, and, if installing Plex, create the dataset(s) for Plex data storage needs.

{{< include file="/static/includes/AppsVMsNoHTTPS.md" >}}

{{< trueimage src="/images/SCALE/22.12/SystemSettingsGUISettingsSCALE.png" alt="General System Settings" id="General System Settings" >}}

After an Apps storage pool is configured, the status changes to <span class="iconify" data-icon="mdi:check-circle" color=#71BF44></span> **Apps Service Running**.

## Using the Installed Applications Screen

The **Installed Applications** screen displays **No Applications Installed** before you install the first application.

{{< trueimage src="/images/SCALE/23.10/AppsInstalledAppsScreenNoApps.png" alt="Installed Applications Screen No Apps" id="Installed Applications Screen No Apps" >}}

Use **Check Available Apps** or **Discover Apps** to open the **[Discover](#using-the-discover-applications-screen)** applications screen to see widgets for applications available in SCALE.

After installing an application, the **Installed** screen populates the **Applications** area with a table of applications.
Select an installed application to view and edit information and to access the **Web Portal** for the application, if applicable.

{{< trueimage src="/images/SCALE/23.10/InstalledAppsScreenWithApps.png" alt="Installed Applications Screen with Apps" id="Installed Applications Screen with Apps" >}}

### Upgrading Apps

To upgrade an app to the latest version, click **Update** on the **Application Info** widget.
To upgrade multiple apps, click the **Update All** button on the **Installed** applications header.
Both buttons only display if TrueNAS SCALE detects an available update.

**Update** opens an upgrade window for the application that includes two selectable options, **Images (to be updated)** and **Changelog**.
Click on the down arrow to see the options available for each.

{{< trueimage src="/images/SCALE/23.10/AppUpdateWindow.png" alt="Update Application Window" id="Update Application Window" >}}

Click **Upgrade** to begin the process and open a counter dialog that shows the upgrade progress.
When complete, the update badge and buttons disappear and the application **Update** state on the **Installed** screen changes from **Update Available** to **Up to date**.

### Deleting Apps

To delete an application, click <i class="fa fa-stop" aria-hidden="true"></i> **Stop** on the [**Installed Applications**](#using-the-installed-applications-screen) screen and wait for the status to show stopped.
Click **Delete** on the **Application Info** widget for the selected application to open the **Delete** dialog.

{{< trueimage src="/images/SCALE/23.10/AppsDeleteAppDialog.png" alt="Delete Application Dialog" id="Delete Application Dialog" >}}

Click **Confirm** then **Continue** to delete the application.

## Using the Discover Applications Screen

The **Discover** screen displays **New & Updated Apps** application widgets for the official TrueNAS **Chart**, **Community**, and **Enterprise** train applications based on the **Trains** settings selected on the **Edit Catalog** screen.
First time SCALE installation includes the **Chart** catalog train.
See [Using SCALE Catalogs]({{< relref "usingcatalogs.md" >}}) for more information.

{{< trueimage src="/images/SCALE/23.10/AppsDiscoverScreen.png" alt="Applications Discover Screen" id="Applications Discover Screen" >}}

Browse the widgets or use the search field to find an available applications.
Click an application widget to go to the application information screen.

{{< trueimage src="/images/SCALE/23.10/MiniIOS3AppInfoScreen.png" alt="Application Information Screen Example" id="Application Information Screen Example" >}}

Click **Install** to open the installation wizard for the application.

## Installing Official Applications

Official applications found on the **Chart** catalog train are pre-configured and only require a name during deployment.

{{< trueimage src="/images/SCALE/23.10/InstallMinioS3Screen.png" alt="Application Install Screen Example" id="Application Install Screen Example" >}}

After installing an application, the **Installed** applications screen shows the application in the **Deploying** state.
It changes to **Running** when the application is ready to use.

{{< trueimage src="/images/SCALE/23.10/MinIOAppInstalled.png" alt="Installed Application Example" id="Installed Application Example" >}}

### Changing Official Application Networking

Official applications use the default system-level Kubernetes Node IP settings.

You can change the Kubernetes Node IP to assign an external interface to your apps, separate from the web UI interface, in **Apps > Settings > Advanced Settings**.

{{< trueimage src="/images/SCALE/23.10/KubernetesSettingsScreenTop.png" alt="Advanced/Kubernetes Settings" id="Advanced/Kubernetes Settings" >}}

We recommend using the default Kubernetes Node IP (0.0.0.0) to ensure apps function correctly.

## Container Image Management

Click **Settings** > **Manage Container Images** to see every container image downloaded to TrueNAS.

{{< trueimage src="/images/SCALE/23.10/AppsManageContainerImages.png" alt="Apps Manage Container Images" id="Apps Manage Container Images" >}}

Images can be updated and deleted from this screen, or click **Pull Image** to download a specific custom image to TrueNAS.

{{< trueimage src="/images/SCALE/23.10/AppsManageContainerImagesPullImage.png" alt="Pull a Container Image" id="Pull a Container Image" >}}

To download a specific image, click the button and enter a valid path and tag to the image.
Use the format *registry*/*repository*/*image* to identify the specific image.
The default **latest** tag downloads the most recent image version.

When downloading a private image, enter user account credentials that allow access to the private registry.

## Installing Custom Applications

To deploy a custom application, go to **Discover** and click **Custom App** to open the **Install Custom App** screen.
See [Using Install Custom App]({{< relref "UsingCustomApp.md" >}}) for more information.

### Changing Custom Application Networking

Custom applications use the system-level Kubernetes Node IP settings by default.
You can assign an external interface to custom apps by setting one on the **Networking** section of the **Install Custom App** screen.

Unless you need to run an application separately from the Web UI, we recommend using the default Kubernetes **Node IP** (0.0.0.0) to ensure apps function correctly.

## Section Contents

{{< children depth="1" description="true" >}}
