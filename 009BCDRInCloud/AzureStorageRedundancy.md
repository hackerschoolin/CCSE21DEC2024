in Azure Bash Setup Variables
```bash
export AZURE_STORAGE_ACCOUNT=forbcdr
export LOCATION=eastus1
export RESOURSEGROUP=AzureBackupRG_eastus_1
```

in Azure Powershell Findout Storage Account Access Key For Later Use

`az storage account keys list --account-name forbcdr --resource-group AzureBackupRG_eastus_1 --output table`

in Azure Bash Setup Storage Account Key and Container name(mustbeinlowercase)
```bash
export AZURE_STORAGE_KEY="qpT7lY=="
export BLOB_CONTAINER_NAME=demoblobcontainer
```

in Azure Powershell

`az storage container create --account-key qpT7lY== --account-name forbcdr --name demoblobcontainer`

in Azure Bash Create Files
```bash
echo daasdfasdf > importantdata.txt
echo asdfasdfadsfasd > secretvideo.mp4
echo secretphoto > secretphoto.jpg
```

in Azure Powershell To Upload Created Files to Storage Account and Check the upload status
```powershell
az storage blob upload --container-name demoblobcontainer --name ImpData --file importantdata.txt --account-name forbcdr --accoun
t-key qpT7lY==
az storage blob upload --container-name demoblobcontainer --name SecretVid --file secretvideo.mp4 --account-name forbcdr --accoun
t-key qpT7lY==
az storage blob upload --container-name demoblobcontainer --name SecretPic --file secretphoto.jpg --account-name forbcdr --accoun
t-key qpT7lY==
az storage blob list --account-name forbcdr --account-key qpT7lYg== --container-name demoblobcontainer --output table
```

goto storage account->click on storage account->search for redundancy->Prepare for failover.
after failover is prepared, pick geop redundancy.
