# Day 2: Create an Azure Virtual Machine

# Step 1: Login into Azure Console

# Step 2: Create VM

Search 'Virtual Machines' > Create

#Basics

Project Details:

Virtual Machine Name:
Region:
Image:
Size:
Select inbound ports: SSH(22)

Disks:

OS disk size: Image default (30 GiB)
OS disk type: Standard HDD (locally-redundant storage)

Review + Create

-> Download private key and create resources

-> Once deployment is completed, click on 'Go to resources'

# Step3: Check SSH Connection

Click on connections > check connections

OR

Connect to VM via local CLI (GitBash or MobaXterm)

$ ssh -i ~path/pem-key azureuser@vm-pub-ip


# If connection is successful, submit the task!!
