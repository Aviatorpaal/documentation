&NewLine;

{{< enterprise >}}
High Availability (HA) systems cannot migrate directly from CORE to SCALE.

Enterprise customers with HA systems should contact iXsystems Support before attempting any migration.

{{< nest-expand "iXsystems Support" "v" >}}
{{< include file="content/_includes/iXsystemsSupportContact.md" >}}
{{< /nest-expand >}}
{{< /enterprise >}}

{{< hint type=warning >}}
Migrating TrueNAS from CORE to SCALE is a one-way operation.
Attempting to activate or roll back to a CORE boot environment can break the system.

Upgrade your CORE system to the latest publicly-available 13.0-U*x* release before attempting to migrate from CORE to SCALE.
{{< /hint >}}
