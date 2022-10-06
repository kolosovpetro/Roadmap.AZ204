# Create Linux VM using CLI

### Login and subscription management

- Login to your account via CLI
    - `az login --use-device-code`
- Check available subscriptions
    - `az account subscription list`
- Check default subscription you have active
    - `az account list -o table`
- Change subscription if necessary
    - `az account set --subscription "name or id"`

### Create VM itself

- Create resource group
    - `az group create --name "rg-ubuntu-vm" --location "westus"`
- Generate RSA key pair in current directory
    - `mkdir ./.ssh`
    - `ssh-keygen -f "./.ssh/id_rsa"`

![Ssh_keygen](./img/05_create_rsa_keypair.PNG)

- Create VM providing public key
    - `az vm create --resource-group "rg-ubuntu-vm" --name "vm-linux-cli" --image "UbuntuLTS" --admin-username "razumovsky_r" --authentication-type "ssh" --ssh-key-value "~/.ssh/id_rsa.pub"`

![Ubuntu_created](./img/06_ubuntu_vm_created_cli.png)

- Open SSH port of the VM
    - `az vm open-port --resource-group "rg-ubuntu-vm" --name "vm-linux-cli" --port "22"`
- Check IP address of the VM
    - `az vm list-ip-addresses --resource-group "rg-ubuntu-vm" --name "vm-linux-cli" --output table`
- Define IP address variable
    - `$ipAddress=$(az vm list-ip-addresses --resource-group "rg-ubuntu-vm" --name "vm-linux-cli" --query '[].{ip:virtualMachine.network.publicIpAddresses[0].ipAddress}' --output tsv)`
    - `echo $ipAddress`
- Connect to the VM via SSH
    - `ssh razumovsky_r@$ipAddress`

![ssh_connected](./img/07_ssh_connected.PNG)

### Delete resource group

- `az group delete --name "rg-ubuntu-vm" --yes`