First Enable DataProc Metastore

Create an endpoint with gRPC Protocol

takes atleast 40-60 mins

Goto Buckets

> Create Bucket->Standard Class,Uniform Access Control->Create(Preferably us central 1 region)

> Goto Data Plex->ManageLakes->Manage->Create->Give Name and Select the Metastore Created before->Create Lake

Click On the lake once its done, Click On Add Zone Under Zones Section->Give Name, Make sure Zone type is raw->Save(Enable if any APIs are needed to be enabled)
