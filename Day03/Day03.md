# Day 3: Create VM using Azure CLI

# Step1: Check the already existed resources

az group list -o table

# Step2: Create the VM and make sure to update resource group as per the Step1

az vm create \
  --resource-group kml_rg_main-3c4c8006653948de \
  --name devops-vm \
  --image Ubuntu2204 \
  --size Standard_B2s \
  --admin-username azureuser \
  --generate-ssh-keys \
  --storage-sku Standard_LRS \
  --os-disk-size-gb 30

#Expected Output:
{
  "fqdns": "",
  "id": "/subscriptions/f0c3bcdd-5ce2-4fa0-8cf3-41559747512b/resourceGroups/kml_rg_main-3c4c8006653948de/providers/Microsoft.Compute/virtualMachines/devops-vm",
  "location": "eastus",
  "macAddress": "7C-1E-52-81-A4-AC",
  "powerState": "VM running",
  "privateIpAddress": "10.0.0.4",
  "publicIpAddress": "20.120.103.245",
  "resourceGroup": "kml_rg_main-3c4c8006653948de",
  "zones": ""
}

# Step3: Verify the status of VM

az vm get-instance-view \
  --resource-group kml_rg_main-3c4c8006653948de \
  --name devops-vm \
  --query "instanceView.statuses[?starts_with(code, 'PowerState/')].displayStatus" \
  --output table

#Expected Output:

Result
----------
VM running
