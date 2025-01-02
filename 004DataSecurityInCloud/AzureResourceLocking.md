## Create New Resource Group
`New-AzResourceGroup -Name "CCSEDEC2024" -Location "EastUS"`

## Create a new VM inside the RG
`New-AzVm -ResourceGroupName "CCSEDEC2024" -Name "DataSecurityVM" -Location "EastUS" -VirtualNetworkName "myVnet" -SubnetName "mySubnet" -SecurityGroupName "myNetworkSecurityGroup" -PublicIpAddressName "myPublicIpAddress" -OpenPorts 80,3389,22`

## Get Details of the resources
`get-Azresource`

## Lock VM
`New-AzResourceLock -LockLevel CanNotDelete -LockNotes "For CCSE Practical" -LockName "CCSEDEC2024Demo" -ResourceName "DataSecurityVM" -ResourceType "Microsoft.Compute/virtualMachines" -ResourceGroupName "CCSEDEC2024"`

## Lock Resource Group
`New-AzResourceLock -LockName "CCSEDEC2024Demo2" -LockLevel CanNotDelete -ResourceGroupName "CCSEDEC2024" -LockNotes "For CCSE Practical"`

## Check the locks
`Get-AzResourceLock`

## Try deleting (should not work)
`remove-AzVM -ResourceGroupName "CCSEDEC2024" -Name "DataSecurityVM"`

## Remove resource Lock
`Get-AZResourceLock | Where-Object ResourceGroupName -eq CCSEDEC2024 | Remove-AzResourceLock -Force`

## Try Deleting VM and RG(should work)
`remove-AzVM -ResourceGroupName "CCSEDEC2024" -Name "DataSecurityVM"`
`remove-AzResourceGroup -Name "CCSEDEC2024"`
