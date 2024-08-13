&NewLine;

{{< hint type=important title="Deprecation Notice" >}}
Due to security vulnerabilities and maintainability issues, the S3 service is deprecated in TrueNAS CORE 13.0 and scheduled for removal in CORE 13.3.
Beginning in CORE 13.0-U6, the CORE web interface generates an alert when the deprecated service is either actively running or is enabled to start on boot.
<!-- Comment out enterprise-specific content as not applicable in 13.3-RELEASE
{{< enterprise >}}
Beginning in CORE 13.0-U6, Enterprise customers with the S3 service running or enabled are prevented from upgrading to the next major version.
{{< /enterprise >}}
-->

Users should plan to migrate to a separately maintained MinIO plugin or otherwise move any production data away from the S3 service storage location.
Migrating from the built-in S3 service to the plugin could result in an extended data migration window and potential disruption to S3 data access.

See the CORE 13.0 [MinIO Plugin](http://www.truenas.com/docs/core/13.0/coretutorials/jailspluginsvms/plugins/minioplugin/) tutorial for detailed migration instructions.

{{< /hint >}}
