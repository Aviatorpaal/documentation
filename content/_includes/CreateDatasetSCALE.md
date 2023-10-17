&NewLine;

To create a dataset using the default settings, go to **Datasets**.
Default settings include the settings datasets inherit from the parent dataset.

Select a dataset (root, parent, or child), then click **Add Dataset**.

{{< trueimage src="/images/SCALE/Datasets/AddDatasetNameAndOptions.png" alt="Name and Options" id="Name and Options" >}}

Enter a value in **Name**.

Select either **Sensitive** or **Insensitive** from the **Case Sensitivity** dropdown.

Select **SMB** for the **Share Type** or leave it set to **Generic**, then click **Save**.

{{< trueimage src="/images/SCALE/Datasets/AddDatasetEncrytionAndOtherOptionsBasic.png" alt="Encryption and Other Options" id="Encryption and Other Options" >}}

You can create datasets optimized for SMB shares or with customized settings for your dataset use cases.

If you plan to deploy container applications, the system automatically creates the **ix-applications** dataset, but it is not used for application data storage.
If you want to store data by application, create the dataset first, then deploy your application.
When creating a dataset for an application, select **App** as the **Share Type** setting. This optimizes the dataset for use by an application.

{{< hint type=important >}}
Review the **Share Type** and **Case Sensitivity** options on the configuration screen before clicking **Save**.
You cannot change these or the **Name** setting after clicking **Save**.
{{< /hint >}}
