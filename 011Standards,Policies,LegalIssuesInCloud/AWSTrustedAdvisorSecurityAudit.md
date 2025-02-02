Create a VM

and open a bunch of ports to anywhere (21, 20, 1433, 1234, 8080)

Create a snapshot of that harddisk

Make the snapshot public

> Select Your snapshot->Actions->SnapshotSettings->ModifyPermissions->Public->Save

Create a S3 Bucket, goto permissions, make it publicly accessible, and also use acl to make to read write to everyone.

Goto Trusted Advisor, and Click Refresh all Checks.
