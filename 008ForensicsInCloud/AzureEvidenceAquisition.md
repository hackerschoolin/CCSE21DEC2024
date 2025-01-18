Create a ubuntu suspect vm in suspect resource group(new)

Create a windows forensic vm in forensic resource group(new)

find the disk name of suspect

`az vm show --resource-group suspect --name suspect --query "storageProfile.osDisk.name"`

create a snapshot of that disk find the sas uri from the output and save

`az snapshot create  --resource-group suspect --name evidencesnapshot --location eastus --source DISKNAMEYOUGOTABOVE`

and share to get the sas URI

`az snapshot grant-access --resource-group  suspect --name evidencesnapshot --duration-in-seconds 3600 --access-level read`

create a storage account in forensic RG find the storage account key and save
```azure
az storage account create --resource-group forensic --location eastus --name ccsedec2024 --kind storageV2 --sku Standard_LRS
az storage account keys list --resource-group forensic --account-name ccsedec2024 --output json
```

create a share in that storage account

```azure
Syntax: az storage share create --account-name ccsedec2024 --account-key "ACCOUNTKEYFROMABOVECOMMAND" --name ccsedec2024`
Example: az storage share create --account-name ccsedec2024 --account-key "F+Ohm/ettXG6Jg==" --name ccsedec2024`
```

copy snapshot into that share
```azure
Syntax: az storage file copy start --source-uri "SASURI" --destination-share ccsedec2024 --destination-path azureevidence.dd --account-name ccsedec2024 --account-key "ACCOUNTACCESSKEY"
Example: az storage file copy start --source-uri "https://md-xhlm.z25.blob.storage.azure.net/bph/abcd?sv=2018-03-28&sr=b&si=a739453e-d43b-4ef5-a0c7-a247&sig=OZ%2A%3D" --destination-share ccsedec2024 --destination-path azureevidence.dd --account-name ccsedec2024 --account-key "F+Ohrtm/eJg=="
```

to check copy status 

`az storage file show --path azureevidencefile.dd --share-name ccsefileshare --account-name ccsefilestorage --account-key "ACCOUNTACCESSKEY" --query "properties.copy.status`

Search for storage accounts->Click Your Storage Account->DataStorage->FileShares->Click On Your Share->Browse->Select Your .dd file and click connect, 
select OS windows, and pick drive letter and authentication as access key->Show Script->and execute the resulting code in your forensic Machine
