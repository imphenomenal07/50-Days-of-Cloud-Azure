# Day 13: SSH into an Azure Virtual Machine

# Step1: Login  into Azure Console

# Step2: Setup SSH connection for root user

#Copy public from Azure client

$ cd .ssh
$ cat rsa_id.pub #Copy key

#Login into Azure VM via Azure client

$ ssh azureuser@az-pub-ip
$ sudo -i #Switch to root user
$ cd .ssh
$ vi authorized_keys #Paste key content here and save-exit from file

# Step3: Verify SSH connection with root user

$ ssh root@az-pub-ip #In new terminal
