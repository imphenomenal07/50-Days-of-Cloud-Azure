# Day 20: Deploy Azure Resources Using ARM Template

# Step1: Update the json file accordingly
$ cd dir-name
$ vi filename.json

# Step2: Find out resource group
$ az group list --query '[].name' --output table | grep 'kml'

#Expected Output:
kml_rg_main-37d4074399cf4f05

# Step3: Deploy the ARM template tp create resources

az deployment group create \
  --resource-group kml_rg_main-37d4074399cf4f05 \
  --template-file vnet-deployment-template.json

# Step4: Verify that the Virtual Network created or not

az network vnet show \
  --resource-group kml_rg_main-37d4074399cf4f05 \
  --name arm-vnet-datacenter
