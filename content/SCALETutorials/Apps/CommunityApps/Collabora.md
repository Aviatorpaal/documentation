---
title: "Collabora"
description: "Provides basic configuration instructions for adding the Collabora app using the TrueNAS webUI."
weight:
tags:
 - apps
 - cloud
---


{{< hint type=important title="24.04 Application Tutorials" >}}
{{< include file="/static/includes/AppsUnversioned.md" >}}
{{< /hint >}}

The SCALE **Apps** catalogue now includes [Collabora](https://nextcloud.com/collaboraonline/) from the developers of [Nextcloud](https://nextcloud.com/).

With Collabora, you can host your online office suite at home.

{{< hint type=note >}}
To integrate Collabora correctly, you must have a [Nextcloud account with Collabora added](https://nextcloud.com/collaboraonline/).
{{< /hint >}}

## Install the Collabora App

Click on the Collabora app **Install** button in the **Available Applications** list.

Name your app and click **Next**. In this example, the name is *collabora1*.

![Collabora1](/images/SCALE/Apps/Collabora1.png "Install Collabora")

Select a **Timezone** and, if you wish, enter a custom **Username** and **Password**.

You can also add extra parameters to your container as you see fit. See The [LibreOffice GitHub Parameters](https://github.com/LibreOffice/online/blob/master/loolwsd.xml.in) page for more.

After you select your container settings, choose a **Certificate** and click **Next**.

![Collabora2](/images/SCALE/Apps/Collabora2.png "Configure Collabora Container")

Enter **Environmental Variables** as needed, then click **Next**.

![Collabora3](/images/SCALE/Apps/Collabora3.png "Configure Collabora Environmental Variables")

Choose a node port to use for Collabora (we recommend the default), then click **Next**.

![Collabora4](/images/SCALE/Apps/Collabora4.png "Configure Collabora Networking")

Configure extra host path volumes for Collabora as you see fit, then click **Next**.

![Collabora5](/images/SCALE/Apps/Collabora5.png "Configure Collabora Extra Host Path Volumes")

Confirm your Collabora container options and click **Save** to complete setup.

![Collabora6](/images/SCALE/Apps/Collabora6.png "Confirm Collabora Options")

After a few minutes, the Collabora container displays as **ACTIVE**.

![Collabora7](/images/SCALE/Apps/Collabora7.png "Collabora Active")

After it does, you can click **Web Portal** to access the admin console.

![Collabora8](/images/SCALE/Apps/Collabora8.png "Collabora Admin Console")
