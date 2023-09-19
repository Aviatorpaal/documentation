&NewLine;

### Cloning to New Dataset

The **Clone to New Dataset** button creates a clone of the snapshot. The clone appears directly beneath the parent dataset in the dataset tree table on the **Datasets** screen. Clicking the **Clone to New Dataset** button opens a clone confirmation dialog.

![StorageSnapshotCloneNewDatasetSCALE](/images/SCALE/Datasets/StorageSnapshotCloneNewDatasetSCALE.png "Clone Snapshot to New Dataset")

Click **Clone** to confirm.

![StorageSnapshotCloneNewDatasetCreatedSCALE](/images/SCALE/Datasets/StorageSnapshotCloneNewDatasetCreatedSCALE.png "Clone Successfully Created")

The **Go to Datasets** button opens the **Datasets** screen. 

![StorageSnapshotCloneNewDatasetListedContentSCALE](/images/SCALE/Datasets/StorageSnapshotCloneNewDatasetListedContentSCALE.png "Dataset Listing with Clone")

### Promoting a Dataset

Clicking on the clone name in the dataset listing populates the **Dataset Details** widget. The **Promote** button is visible.

![StorageSnapshotCloneNewDatasetPromoteSCALE](/images/SCALE/Datasets/StorageSnapshotCloneNewDatasetPromoteSCALE.png "Clone Promote Button")

After clicking the **Promote** button, the dataset clone is promoted and this button no longer appears. 

![StorageSnapshotCloneNewDatasetAfterPromoteSCALE](/images/SCALE/Datasets/StorageSnapshotCloneNewDatasetAfterPromoteSCALE.png "Clone After Promotion")

**Promote** now displays on the **Dataset Details** widget when you select the demoted parent dataset.

![DatasetDetailsParentDataNotPromotedSCALE](/images/SCALE/Datasets/DatasetDetailsParentDataNotPromotedSCALE.png "Demoted Volume Promote Button")

See [zfs-promote.8](https://openzfs.github.io/openzfs-docs/man/8/zfs-promote.8.html) for more information.
