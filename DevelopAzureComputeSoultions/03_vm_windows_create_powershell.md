# Create Windows VM using Az PowerShell

### Prerequisites

- Update Windows Powershell as Administrator using: `Install-Module PSWindowsUpdate`
- Install [Azure PowerShell](https://docs.microsoft.com/en-us/powershell/azure/install-az-ps)
- Install as Powershell Administrator: `Install-Module AzureAD`

### Login and subscription management

- Let's login, may launch a browser to authenticate the session.
    - `Connect-AzAccount -SubscriptionName 'Azure for Students'`

- Ensure you're pointed at your correct subscription
    - `Set-AzContext -SubscriptionName 'Azure for Students'`

### Create resource group

- Create a Resource Group
    - `$rgName="rg-win-vm-pwsh"`
    - `$location="CentralUS"`
    - `New-AzResourceGroup -Name $rgName -Location $location`

### Create a credential to use in the VM creation

- `$adminUsername="razumovsky_r"`
- `$password="$env:AD_TEST_USER_PASSWORD"`
- `$adminPassword=ConvertTo-SecureString $password -AsPlainText -Force`
- `$psCredential = New-Object System.Management.Automation.PSCredential ($adminUsername, $adminPassword)`

### Create a Windows Virtual Machine, can be used for both Windows and Linux.

Note, you can create Windows or Linux VMs with PowerShell by specifying the correct Image parameter.
**This command does not create public IP Address**

- `$vmName="vm-win-pwsh"`
- `$image="Win2019Datacenter"`
- `Get-AzVMSize -Location $location`
- `$vmSize="Standard_B1ms"`
- `New-AzVM -ResourceGroupName $rgName -Name $vmName -Image $image -Credential $psCredential -OpenPorts "3389" -PublicIpSku "Standard" -Size $vmSize`

### Create public IP Address for the VM using Azure Portal

- https://learn.microsoft.com/en-us/azure/virtual-network/ip-services/associate-public-ip-address-vm

### Connect using RDP

- Go to `Azure Portal -> VM -> Connect (top left corner) -> RDP`
- Download RDP file
- Connect to VM providing username and password

### Delete resource group

- `Remove-AzResourceGroup -Name $rgName`
