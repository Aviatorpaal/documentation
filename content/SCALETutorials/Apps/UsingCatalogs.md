---
title: "Using SCALE Catalogs"
description: "Provides basic information on adding or managing application catalogs in TrueNAS SCALE."
weight: 5
tags:
- apps
- customapp
---

TrueNAS SCALE comes with a pre-built official catalog of iXsystems-approved apps that includes over 50 available applications. 

Users can configure custom apps catalogs, although iXsystems does not directly support any non-official apps in a custom catalog.

{{< hint type=note >}}
TrueNAS uses outbound ports 80/443 to retrieve the TRUENAS catalog.
{{< /hint >}}

## Managing Catalogs

To manage and add catalogs, click on the **Manage Catalogs** on the **Discover** screen to open the **Catalogs** screen. 

{{< trueimage src="/images/SCALE/Apps/AppsDiscoverScreen.png" alt="Applications Discover Screen" id="Applications Discover Screen" >}}

Users can edit, refresh, delete, and view the summary of a catalog by clicking on a catalog to expand and show the options.

**Edit** opens the **Edit Catalog** screen where users can change the name SCALE uses to look up the catalog. You cannot change the name of the TRUENAS default catalog.
You can change the trains from which the UI retrieves available applications for the catalog.

{{< trueimage src="/images/SCALE/Apps/AppsEditCatalogScreen.png" alt="Apps Edit Catalog Screen" id="Apps Edit Catalog Screen" >}}

**Refresh** re-pulls the catalog from its repository and applies any updates.

**Delete** allows users to remove a catalog from the system. Users cannot delete the default TRUENAS catalog.

**Summary** lists all apps in the catalog and sorts them train, app, and version.

Users can filter the list by **Train** type (**All**, **charts**, or **test**), and by **Status** (**All**, **Healthy**, or **Unhealthy**).

## Adding Catalogs

To add a catalog, click the **Add Catalog** button at the top right of on the **Catalogs** screen. 

A warning dialog opens. 

{{< trueimage src="/images/SCALE/Apps/AddCatalogWarning.png" alt="Add Catalog Warning" id="Add Catalog Warning" >}}

Click **CONTINUE** to open the **Add Catalog** screen.

{{< trueimage src="/images/SCALE/Apps/AppsAddCatalogScreen.png" alt="Apps Add Catalog Screen" id="Apps Add Catalog Screen" >}}

Fill out the **Add Catalog** form.

Enter the name in **Catalog Name**, for example, type *mycatalog*.

Leave the **Force Create** checkbox clear.
Selecting this option allows adding a catalog to the system even if some trains are unhealthy, so this option is not recommended.

Select a valid git repository in **Repository**. For example, *https://github.com/mycatalog/catalog*.

Now select the train TrueNAS should use to retrieve available application information of the catalog.

Finally, enter the git repository branch TrueNAS should use for the catalog in **Branch**.

Click **Save**. 
