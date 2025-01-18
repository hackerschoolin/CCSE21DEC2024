Create Suspect Linux VM, do some bad stuff like download some malicous photos or docs or text files

Create Forensic Windows VM with more storage and RAM than suspect

Goto Elastic Block Storage->Volumes->Select Your suspect volume->Create a snapshot of your suspect harddisk volume

Goto Elastic Block Storage->Snapshots->Select Your suspect snapshot->Create an evidence volume from snapshot

Goto Elastic Block Storage->Volumes->Select your new evidence volume->Attach->to Forensic PC

In Your Forensic PC If you are using Windows Server with Internet Explorer Secure Mode

Search for Server Manager->Local Server->Search for Enhanced Protection for Internet Exploere and Turn off

then download chrome from IE, and in chrome download autopsy. and install.

after autopsy is installed, create new case fill the necessary details

add data source and select logical disk->Select your newly attached evidence disk. and continue.

wait for the analysis to complete and explore the evidence after that.
