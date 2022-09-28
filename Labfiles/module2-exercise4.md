### Exercise 4: Optimizing newly migrated workloads, and emphasizing commonalities across all stacks

#### Task 1: Getting started with Azure Active Directory for Linux 

In this task, you will be enabling the AAD authentication using a VM extension and enbaling Managed identity. 

1. In the Azure portal `https://portal.azure.com`, Navigate to your newly migrated LinuxVM and select it.
    
    ![](Images/linucvm.png)
    
2. Now from the left side menu, select the **Identity**.

    ![](Images/identityt.png)

3. Under Identity,Under System assigned tab, Click on the **On** button under Status tag and clik on **Save** button to turn on the identity. It will take sometime to complete the process and there have some Service principal is getting created behind the process.

      ![](Images/turinon.png)
      ![](Images/identidone.png)
      
4. Now, Navigate to **Extension + application** from the left side menu.
   
    ![](Images/extension.png)

5. In the Extension page, Click on **add** button to add an extension that will help you to connect to your machine using your AAD account.

    ![](Images/addexn.png)

6. Once you are on **Install an extension** page, search for **Azr=ure AD based SSH Login** extension and select it and click on **Next** button.

    ![](Images/aaadextensfd.png)

7. You will be redirected to the **Configure Azure AD based SSH Login extension** page, now click on **Review + create** and then **create** button. It should start the installation of the extension into your LinuxVM.

    ![](Images/creasd.png)
    ![](Images/isntallas.png)

8. Once you have the extension installed, please move to the next task.

    ![](Images/completed.png)

#### Task 2: Leveraging SSH to connect and authenticate Linux Servers on Azure 

To improve the security of Linux virtual machines in Azure, you can integrate with Azure Active Directory (Azure AD) authentication. You can now use Azure AD as a core authentication platform and a certificate authority to SSH into a Linux VM by using Azure AD and OpenSSH certificate-based authentication. This functionality allows organizations to manage access to VMs with Azure role-based access control (RBAC) and Conditional Access policies.

In this task we are using Azure CloudShell to configure a Linux VM and log in with Azure AD by using OpenSSH certificate-based authentication.

1. In the Azure portal `https://portal.azure.com`, select the Azure Cloud Shell icon from the top menu.

   ![The Azure Cloud Shell icon is highlighted in the Azure portal's top menu.](Images/cloud-shell-icon.png "Azure Cloud Shell")

2. In the Cloud Shell window that opens at the bottom of your browser window, select **PowerShell**.

   ![In the Welcome to Azure Cloud Shell window, PowerShell is highlighted.](Images/cloud-shell-select-powershell.png "Azure Cloud Shell")

3. If prompted about not having a storage account mounted, click on **Show advanced settings**. Select Create new under Storage account and provide values as below: 
  
      - **Resource Group**: Select **Use existing** then select **SmartHotelRG**
      - **Storage account** : **storage<inject key="Suffix" enableCopy="false"/>**
      - **File Share** : **blob**

   ![This is a screenshot of the cloud shell opened in a browser window. Powershell was selected.](Images/b4-image36.png "Azure Cloud Shell")

4. After a moment, a message is displayed that you have successfully requested a Cloud Shell, and you are presented with a PS Azure prompt.

   ![In the Azure Cloud Shell dialog, a message is displayed that requesting a Cloud Shell succeeded, and the PS Azure prompt is displayed.](Images/cloud-shell-ps-azure-prompt.png "Azure Cloud Shell")
   
5. At the prompt, login to the azure by entering the following PowerShell command.

  ```
  Az login
  ```
  
  - **Note:** Copy the login URL and enter the unique code in the browser.
  
 
 ![](Images/azlogin.png)
 
  
6. Run the following commands to connect to the VM by using the name and resource group of the VM:

  ```
  az ssh vm -n UbuntuVM -g SmartHotelRG
  ```
  

#### Task 3: Azure auto manage

In this task, you will Enable Automanage on existing machines.

1. If you are not logged in already, click on Azure portal shortcut that is available on the desktop and log in with below Azure credentials.
    * Azure Username/Email: <inject key="AzureAdUserEmail"></inject> 
    * Azure Password: <inject key="AzureAdUserPassword"></inject>

2. In the search bar, search for and select **Automanage – Azure machine best practice**s.

3. Under **Automanage machines**, select the **+Enable on existing VM**.
   
   ![](Images/upd-zero-vm-list-view.png)

4. Under **Configuration profile**, select your profile type: **Azure Best Practices - Production or Azure Best Practices - Dev/Test or Custom profile**.
   
   ![](Images/upd-existing-vm-quick-create.png)
   
   > Click View best practice profiles to see the differences between the environments.
    
   ![](Images/upd-browse-production-profile.png)

5. On the Select **machines blade**:

   a. Filter the list by your Subscription and Resource group.
   
   b. Check the checkbox of **UbuntuVM** virtual machine 
   
   c. Click the **Review+Create** button.
   
   ![](Images/auto-manage.png)

6. Click **Create**.
