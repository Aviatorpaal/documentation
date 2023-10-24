---
title: "Preparing to Migrate TrueNAS CORE to SCALE (Enterprise HA)"
description: "Provides information for CORE Enterprise (HA) users planning to migrate to SCALE and what you need to know and have ready before beginning the one-way process."
weight: 20
aliases:
tags:
- scalemigrate
- scaleconfigure


---

{{< toc >}}

{{< include file="/_includes/MigrateCOREtoSCALEWarning.md" >}}

{{< include file="/_includes/MigrateCoreServicesToCobiaEnterprise.md" >}}

## What can or cannot migrate?

{{< include file="/_includes/COREMigratesList.md" >}}

## Before Migrating to SCALE

You cannot directly migrate a TrueNAS Enterprise High Availability (HA) system from CORE to SCALE!
Instead, the system can be freshly installed with TrueNAS SCALE and storage data pools reimported after the install process is complete.

This section outlines actions to take or consider to prepare for the clean installation of SCALE for an Enterprise (HA) system.

Before you begin the clean install of SCALE, on CORE:

1. Back up your stored data files and any critical data!
   If you need to do a clean install with the SCALE <file>iso</file> file, you can import your data into SCALE.

2. Write down your network configuration information to use after the clean install of SCALE.
   {{< include file="/_includes/NetworkInstallRequirementsSCALE.md" >}}

3. Identify your system dataset.
   If you want to use the same dataset for the system dataset in SCALE, note the pool and system datasat.
   When you set up the first required pool on SCALE import this pool first.

4. Review and document down any system configuration information in CORE you want to duplicate in SCALE. Areas to consider:

   * Tunables on CORE.
     SCALE does not use **Tunables** the way CORE does. SCALE provides script configuration on the **System Settings > Advanced** screen as **Sysctl** scripts.
     A future release of SCALE could introduce similar tunables options found in CORE but for now it is not available.

   * CORE init/shutdown scripts to add to SCALE.

   * CORE cron jobs configured if you want to set the same jobs up in SCALE.

   * The global self-encrypting drive (SED) password to configure in SCALE, or unlock these drives in CORE before you clean install SCALE.

   * Cloud storage backup provider credentials configured in CORE if you do not have these recorded in other files kept secured outside of CORE.

   * Replication, periodic snapshot, cloud sync, or other tasks settings to reconfigure in SCALE if you want to duplicate these tasks.

   * Make sure you have backed-up copies of certificates used in CORE to import or configure in SCALE.

   * Record deprecated service settings and any WebDAV share dataset and user configurations.

Download the SCALE [SCALE ISO file](https://www.truenas.com/download-tn-scale/) or the SCALE upgrade file and save it to your computer or on two USB drives (see the **Physical Hardware tab** in [Installing SCALE]({{< relref "InstallingSCALE.md" >}})).

{{< taglist tag="scalemigrate" vol="SCALE" limit="5" title="Related Migration Articles" >}}
{{< taglist tag="scaleconfigure" vol="SCALE" limit="5" title="Related Configuration Articles" >}}