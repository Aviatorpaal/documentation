---
title: "Using the Console Setup Menu"
description: "Provides information on using the Console setup menu after installing TrueNAS SCALE from the iso file to configure network settings."
weight: 20
aliases:
 - /scale/gettingstarted/post-installconfiguration/
tags:
- scaleinstall
- scalenetwork
- scaleconsole
book: "SCALEGettingStarted"
volume: "SCALE"
---

{{< toc >}}

The Console setup menu (CSM) displays at the end of the <file>iso </file> installation process and after the system boots up.
You can access this menu to administer the TrueNAS system if it has a keyboard and monitor.

By default, TrueNAS does not display the Console setup menu when you connect via SSH or the web shell. 
The admin user, the root user (if enabled), or another user with root permissions can start the Console setup menu by entering this command:

`/usr/bin/cli --menu`  

The menu provides these options:

{{< trueimage src="/images/SCALE/CLI/ConsoleSetupMenuSCALE.png" alt="TrueNAS SCALE Console Setup Menu" id="TrueNAS SCALE Console Setup Menu" >}}

For network configuration options **1**, **2**, and **3**, we recommend using the SCALE UI to configure network interfaces, as it has safeguards to prevent breaking network access to SCALE.

* **1) Configure network interfaces** 

  Use this to configure the primary network interface with a static IP. This is for switching away from the DHCP-assigned IP address TrueNAS provides when the system boots after installing SCALE.
  Also, use this to set up other network interfaces or to add alias IP addresses for the primary interface.

* **2) Configure network settings** 
  
  Use this to set up the network default gateway, host name, domain, IPv4 gateway and DNS name servers.
  Configured options display in the **Global Configuration** widget in the web UI **Network** screen. 

* **3) Configure static routes** 
  
  Use this to set up static IP routes, but this is not required as part of the initial configuration setup.

* **4) Change local administrator password** 
  
  Use to change the administrator user password.
  If you selected option 1 on the iso installer menu, you already configured the admin user and password. 
  Use can use this to change the admin password before you log into the SCALE UI.
  {{< hint type=note >}}
  This is not the password for the root user in the CLI or the root user login password for the web UI.
  The [root user password]({{< relref "rootlessLogin.md" >}}) is disabled by default. You can turn on the root user password in the UI, but we do not recommend doing that.
  {{< /hint >}}

* **5) Reset configuration to defaults** 
  
  Use to wipe all system configuration settings and return the system to a fresh install state.

* **6) Open TrueNAS CLI Shell** 

  Use to start a shell for running TrueNAS commands, or use the SCALE UI **[System Settings > Shell]({{< relref "UseScaleShell.md" >}})**. 
  Type `exit` to leave the shell.

* **7) Open Linux Shell** 
  
  Use to start a shell window for running Linux CLI commands. 
  Configuration changes made here are not written to the database and are reset on each system boot.
  We do not recommend using the Linux shell unless you are an advanced user. Type `exit` to leave the shell.

* **8) Reboot** 

  Use to power down, then automatically power on the system.

* **9) Shut down** 

  Use to power down the system.

{{< hint type=note >}}
Console setup menu options can change with software updates, service agreements, etc.
{{< /hint >}}

During its first boot, TrueNAS attempts to connect to a DHCP server from all live interfaces.
If it receives an IP address, the Console setup menu displays it under **The web user interface is at:** so you can access the SCALE web UI.

You might be able to access the web UI using a `hostname.domain` command at the prompt (default is `truenas.local`) if your system:

* Does not have a monitor.
* Is on a network that supports Multicast DNS (mDNS).

## Console Setup Menu Network Settings

You can either use SCALE UI or the Console setup menu to configure your network settings for the primary network interface or other interfaces such as a link aggregate (LAGG) or virtual LAN (VLAN), or aliases for an interface, and to configure other network settings such as the default gateway, host name, domain, and the DNS name servers, or add static routes. 

{{< include file="/content/_includes/UsingConsoleSetupMenuSCALE.md" >}}

Enter <kbd>1</kbd> to display the **Configure Network Interfaces** screen where you can select the interface settings. 

{{< trueimage src="/images/SCALE/CLI/CSMEditInterface.png" alt="TrueNAS SCALE Console Setup Menu Edit Interface" id="TrueNAS SCALE Console Setup Menu Edit Interface" >}}

Follow the instructions on the screen to configure an IP for a network interface. 
Type <kbd>n</kbd> to open the new interface screen or press <kbd>Enter</kbd> to edit the existing interface.

{{< trueimage src="/images/SCALE/CLI/CSMEditInterfaceSettings.png" alt="TrueNAS SCALE Console Setup Menu Edit Interface Settings" id="TrueNAS SCALE Console Setup Menu Edit Interface Settings" >}}

You can enter aliases for an interface when you create a new one or edit an existing interface.

{{< include file="/_includes/AliasOrStaticIP.md" >}}

Type <kbd>q</kbd> to to return to the main Console setup menu screen. 

Enter <kbd>2</kbd> to display the **Network Settings** screen where you can set up the host name, domain, default gateway and name servers.

{{< trueimage src="/images/SCALE/CLI/CSMEditNetworkSettings.png" alt="TrueNAS SCALE Console Setup Menu Edit Network Settings" id="TrueNAS SCALE Console Setup Menu Edit Network Settings" >}}

Enter <kbd>3</kbd> to display the Static Route Settings screen where you can set up any static routes. You can also add static routes in the web UI.

{{< trueimage src="/images/SCALE/CLI/CSMEditStaticRoute.png" alt="TrueNAS SCALE Console Setup Menu Static Routes" id="TrueNAS SCALE Console Setup Menu Static Routes" >}}

{{< include file="/_includes/AliasOrStaticIP.md" >}}

### Configuring Required Network Settings 

{{< include file="/content/_includes/DHCPCreatedNetwork.md" >}}

To use the Console setup menu to change the network interface IP address, type <kbd>1</kbd> and then press <kbd>Enter</kbd> to open the **Configure Network Interfaces** screen. 
Use either <kbd>Tab</kbd> or the arrow keys to select the interface to use as your primary network interface if you have more than one interface installed and wired to your network. 
Type in the IP address then use either <kbd>Tab</kbd> or the arrow keys to move through the menu and down to select **Save**, and then press <kbd>Enter</kbd>. 
After saving, return to the main Console setup menu by entering <kbd>q</kbd>. 

To configure the default gateway, host name, domain and DNS name severs using the Console setup menu type <kbd>2</kbd> and then press <kbd>Enter</kbd> to open the **Network Settings** screen. 

To configure network settings in the SCALE UI, enter the IP address displayed on the Console setup menu screen in a browser URL field and press <kbd>Enter</kbd>. 
Log in with the admin user name and the password you set for the administration user during the <file>iso</file> installation process, and then go to **Network** and or edit and interface or global network configuration settings. 

For home users, you have a few options to allow Internet access using TrueNAS SCALE:
* Use 8.8.8.8 as the DNS nameserver address
* Use your ISP provider DNS servers (contact them for assistance with these addresses)
* Use 1.1.1.1 for [Cloudflare](https://www.cloudflare.com/)
* Use 9.9.9.9 for [Quad9](https://www.quad9.net/)

## Changing the Administrator Password

SCALE has implemented rootless login, making the admin user the default account, and has disabled the root password by default. 
You can change the admin user password in the UI or from the Console setup menu.
You can set and enable the root user password in the UI, but for security hardening, we recommend you leave it disabled.

Changing the admin user (or root if you have not created the admin user) password disables 2FA (Two-Factor Authentication).

{{< hint type=important >}}
Disabling a password in the UI prevents the user from logging in with it. When both root and local admin user passwords are disabled and the web interface session times out, a temporary sign-in screen allows logging in.
Immediately go to the **Credentials > Local User** screen, select the admin user, and then **Edit** to re-enable the password.
{{< /hint >}}

## Resetting the System Configuration
{{< hint type=warning >}}
**Caution!**
Resetting the configuration deletes all settings and reverts TrueNAS to default settings. Before resetting the system, back up all data and encryption keys/passphrases! 
After the system resets and reboots, you can go to **Storage** and click **Import Pool** to re-import pools.
{{< /hint >}}

Enter **5** in the Console setup menu, then enter <kbd>y</kbd> to reset the system configuration. The system reboots and reverts to default settings.

## Completing your System Setup

After setting up network requirements, log into the web UI to complete your system setup by:
* [Setting up storage]({{< relref "SetUpStorageSCALE.md" >}})
* [Setting up sharing]({{< relref "SetUpSharing.md" >}})
* [Backing Up your Configuration]({{< relref "SetUpBackupSCALE.md" >}})

{{< taglist tag="scaleinstall" vol="SCALE" limit="5" >}}
{{< taglist tag="scalenetwork" vol="SCALE" limit="5" title="Related Network Articles" >}}
