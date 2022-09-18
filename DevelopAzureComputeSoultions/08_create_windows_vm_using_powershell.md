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
    - `New-AzResourceGroup -Name "rg-win-vm-powershell" -Location "CentralUS"`

### Create a credential to use in the VM creation

- `$username = "razumovsky_r"`
- `$password = ConvertTo-SecureString "$env:AD_TEST_USER_PASSWORD" -AsPlainText -Force`
- `$WindowsCred = New-Object System.Management.Automation.PSCredential ($username, $password)`

### Create a Windows Virtual Machine, can be used for both Windows and Linux.

Note, you can create Windows or Linux VMs with PowerShell by specifying the correct Image parameter.
**This command does not create public IP Address**

- `New-AzVM -ResourceGroupName "rg-win-vm-powershell" -Name "vm-win-pwsh" -Image "Win2019Datacenter" -Credential $WindowsCred -OpenPorts "3389"`

### Create public IP Address for the VM using Azure Portal

- https://learn.microsoft.com/en-us/azure/virtual-network/ip-services/associate-public-ip-address-vm

### Connect using RDP

- Go to `Azure Portal -> VM -> Connect (top left corner) -> RDP`
- Download RDP file
- Connect to VM providing username and password used during its creation

### Delete resource group

- `Remove-AzResourceGroup -Name "rg-win-vm-powershell"`
