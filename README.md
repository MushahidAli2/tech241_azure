## Step-by-Step Guide: Creating an Azure Virtual Machine

1. **Create your first Azure Virtual Network:**

- Login to [portal.azure.com](https://portal.azure.com).
- Click on the "Create a resource" button.
- Search for "Virtual network" and select it from the options.
- Click on "Create" to start the virtual network creation process.

    **Basics:**
    - In the Basics tab, provide a name for your virtual network in the "Name" field, following the format `<group>-<first name>-test-vnet` (e.g., `tech201-Mushahid-test-vnet`).
    - Change the region to "UK South" from the dropdown menu.
    - Under Tags, add a tag called "Owner" with your first name as the value (e.g., "Mushahid").
    - Leave the other settings as default.

    **Review + Create:**
    - Click on "Review + Create" to review the settings.
    - Verify that the settings match your requirements.
    - Click on "Create" to create the virtual network.

2. **Understand what is needed to create an Azure VM:**

- Realize that you won't be able to SSH into the virtual machine unless it has a public IP assigned to it.
- Create an SSH key pair on your local machine using Git Bash or a similar tool.
- Proceed to the Azure portal to create an SSH Key.

## SSH key pair using Launch Git Bash:

Open the Git Bash application on your local machine. It provides a command-line interface where you can execute Git commands and other Unix-like commands.
Generate SSH Key Pair:

In the Git Bash terminal, use the ssh-keygen command to generate a new SSH key pair.
Type the following command and press Enter:
```python
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

Replace "your_email@example.com" with your actual email address associated with your Azure account.

You will be prompted to provide a file name for the key pair and choose a passphrase. Press Enter to accept the default file location and an empty passphrase if you don't want to set one (although it's generally recommended to use a passphrase for added security).
The SSH key pair, consisting of a private key (id_rsa) and a public key (id_rsa.pub), will be generated and saved in the specified file location.
Copy the Public Key:

Use the cat command to display the content of the public key file.
Type the following command and press Enter:
bash
Copy code
cat ~/.ssh/id_rsa.pub
The content of the public key will be displayed in the terminal.
Select the entire key, including the "ssh-rsa" at the beginning, and copy it to your clipboard. This is your public key that you'll need to add to Azure.
Add SSH Key to Azure:

Proceed to the Azure portal and navigate to the virtual machine creation process or the SSH key configuration section as mentioned in the previous steps.
Paste the copied public key into the "Public key data" field.
Provide a name for the SSH public key.
Click on "Save" to add the SSH key to Azure.

3. **Create an SSH Key in Azure:**

- Open the Azure portal and navigate to your virtual machine.
- In the left-hand menu, click on "Settings" and select "SSH public keys."
- Click on "Generate SSH public key."
- Provide a name for the SSH public key.
- Paste the public key content generated on your local machine into the "Public key data" field.
- Click on "Save" to create the SSH key in Azure.

4. **Create a Virtual Machine:**

- In the Azure portal, navigate to the virtual network you created earlier.
- In the left-hand menu, click on "Settings" and select "Virtual machines."
- Click on "Add" to start the virtual machine creation process.

    **Basics:**
    - Provide a name for the virtual machine.
    - Choose a region for the virtual machine.
    - Select the appropriate image for the virtual machine's operating system.
    - Configure the size and other hardware settings based on your requirements.
    
    **Disks:**
    - Configure the OS disk and data disks for the virtual machine, specifying their sizes and types.
    
    **Networking:**
    - Select the virtual network you created earlier.
    - Choose the appropriate subnet within the virtual network.
    - Enable the "Public IP" option to assign a public IP to the virtual machine.
    
    **Management:**
    - Configure any additional management settings, such as availability options, extensions, or boot diagnostics.
    
    **Advanced:**
    - Configure any advanced settings, such as custom script execution, virtual machine scale sets, or Azure Spot Instances.
    
    **Tags:**
    - Add any relevant tags to organize and manage your virtual machine.
    
    **Review + Create:**
    - Review the settings to ensure they match your requirements.
    - Click on "Create" to start the virtual machine creation process.

Congratulations! You have successfully created a virtual machine in Azure. You can now access and manage your virtual machine through the Azure portal. Remember to take note of the public IP address if you need to connect to the virtual machine via SSH.

Please note that the above guide provides a general outline, and some

