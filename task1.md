## Task 1 - Azure Linux VM Setup with SSH and GUI Access

### 🔧 Tool/Command Used:
Azure Portal, Azure CLI, SSH, Remote Desktop Protocol (RDP), XRDP, XFCE4

### 📘 Explanation:
This task involves provisioning a Linux virtual machine in Azure, enabling secure SSH access, installing a desktop environment (XFCE4), and setting up remote GUI access using XRDP and RDP. Azure CLI was used to open the required ports for RDP access.

### 🖼️ Screenshot:
![rgimage](images/imagetask1/rgimage.png)

This shows the creation of a Resource Group to logically organize resources. The Azure CLI command `az group create` was used to create the resource group.

---

![vm create](images/imagetask1/vm%20create.png)

Linux VM is being created within the resource group via Azure Portal. 

---

![resourcedispay](images/imagetask1/resourcedispay.png)

Displays the deployed VM details including public IP and resource name. The public IP is used for RDP access. The resource name is used for SSH access. The Azure CLI command `az vm open-port` was used to open the required ports for RDP.

---

![vmdeployment](images/imagetask1/vmdeployment.png)

Successful deployment confirmation of the Azure Linux VM. The Azure CLI command `az vm show` was used to verify the VM details. 

---

![sshazure](images/imagetask1/sshazure.png)

The SSH credentials screen in Azure, showing connection command to access the VM securely. 

---

![ssh-init-connection](images/imagetask1/ssh-init-connection.png)

First-time SSH attempt from local terminal to Azure VM using the provided public IP and credentials. The Azure CLI command `ssh-keygen` was used to generate SSH keys. The Azure CLI command `ssh-copy-id` was used to copy the local SSH key to the Azure VM. The Azure CLI command `ssh` was used to establish the SSH connection. 

---

![ssh-ubuntu-login](images/imagetask1/ssh-ubuntu-login.png)

Successful login into the Ubuntu Linux VM using SSH. The Azure CLI command `ssh` was used to establish the SSH connection. 

---

![pwdazure](images/imagetask1/pwdazure.png)

Displays the present working directory inside the SSH session confirming successful login. The Azure CLI command `pwd` was used to display the present working directory. 

---

![xrdpinstall](images/imagetask1/xrdpinstall.png)

Installation of XRDP package to allow remote desktop connections. The Azure CLI command `sudo apt-get install xrdp` was used to install the XRDP. 

---

![xfce4](images/imagetask1/xfce4.png)

Installation of XFCE4 desktop environment on the Linux VM. The Azure CLI command `sudo apt-get install xfce4` was used to install the xfce4. 

---

![enablexrdp](images/imagetask1/enablexrdp.png)

XRDP is enabled and started, and necessary configuration is done to use XFCE4 with XRDP . The Azure CLI command `sudo systemctl enable xrdp` was used to enable XRDP. The Azure CLI command `sudo systemctl start xrdp` was used to start XRDP.  

---

![xrdp-setup-commands](images/imagetask1/xrdp-setup-commands.png)

Final setup and configuration of XRDP including restarting the service. The Azure CLI command `sudo systemctl restart xrdp` was used to restart XRDP. The Azure CLI command `sudo systemctl status xrdp` was used to check the status of xrdp.

---

![az-vm-open-port](images/imagetask1/az-vm-open-port.png)

Using Azure CLI to open port 3389 for allowing RDP traffic into the Linux VM. The Azure CLI command `az vm open-port --resource-group myResourceGroup --name myVM --port 3389` was used to open port 3389.   

---

![rdp-login-screen](images/imagetask1/rdp-login-screen.png)

Successfully connecting to the Linux VM GUI using RDP after XRDP and XFCE setup. The Azure CLI command `mstsc /v:public_ip_address:3389` was used to connect to the Linux VM GUI. The Azure CLI command `mstsc` was used to connect to the Linux VM GUI. 
