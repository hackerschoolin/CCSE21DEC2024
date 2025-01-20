Create Two Buckets in Two Regions with bucket versioning and also object lock enabled

pick one bucket goto management

look for replication rules

create replication rules

give name

scope will be "Apply to all objects in the bucket"

Select Destination bucket as second bucket

IAM Role will be "Create new role"

Save

Now any objects you upload to first bucket, will be replicated to the second bucket ASAP
