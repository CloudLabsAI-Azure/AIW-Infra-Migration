# HOL 3: Run apps and workloads anywhere with Azure cloud services.

### Exercise 1: Onboard On-prem servers to Azure Arc enabled server

In this exercise, you will deploy and configure the Azure Connected Machine agent on a Windows machine hosted outside of Azure, so that it can be managed through Azure Arc-enabled servers.


1. If you are not logged in already, click on Azure portal shortcut that is available on the desktop and log in with below Azure credentials.
    * Azure Username/Email: <inject key="AzureAdUserEmail"></inject> 
    * Azure Password: <inject key="AzureAdUserPassword"></inject>

1. In the **search resources, services and docs bar**, type **Azure arc** and select it from suggestions, as shown below:
   
    ![Screenshot of the search azure arc.](Images/searchazarc.png "search azure arc")
   
1. On the **Azure Arc** page, select **Servers** under **Infrastructure** and then click on **+Add**.
    
    ![Screenshot of the add server.](Images/addserver.png "add server")
    
1. In the **Add servers with Azure Arc** page, click **Generate script** under **Add a single server**.

    ![Screenshot of the Generate script.](Images/singleserver.png "Generate script")
     
1. Under **Pre-requisites** tab, just read the given data and click on **Next**.     

    ![Screenshot of the pre-req tab.](Images/prereq.png "pre-req tab")
    
1. Under **Resource details** tab, fill the following details:
     
   - Subscription: **Select your subscription**
    
   - Resource group: **SmartHotelRG (1)**
  
   - Region: **Should be same as your resource group (2)** (You can check the region under Environment details panel.)
   
   - Operating system: **Windows (3)**
   
   - Leave other values as default and Click on **Next (4)**

    ![Screenshot of the resource details tab.](Images/upd-resourcedetails.png "resource details tab")

1. Under **Tags** tab, leave the values as default and click on **Next**.

1. Under **Download and script** tab, **copy (1)** the entire script and paste it in a notepad as it will be used in the further steps and then click on **Close (2)**.

    ![Screenshot of the copy script.](Images/upd-copyscript.png "copy script")
    
1. Go to **Start** button in the VM, search for **Hyper-V Manager** there and select it. 

    ![Screenshot of Hyper-V Manager, with the 'Hyper-V Manager' action highlighted.](Images/upd-hyper-v-manager.png "Hyper-V Manager")

   > You can also open the **Hyper-V manager** by clicking on the icon that is present in the taskbar. 
    
1. In Hyper-V Manager, select **SMARTHOST<inject key="DeploymentID" enableCopy="false" />**. 
  
    ![Screenshot of Hyper-V Manager on the SmartHotelHost.](Images/Hyperv1.png "Hyper-V Manager")
    
1. In Hyper-V Manager, select the **AzureArcVM (1)** VM, then select **Start (2)** on the right if not already running.

    ![Screenshot of Hyper-V Manager showing the start button for the AzureArcVM.](Images/upd-Hyperv2.png "Start AzureArcVM")    
    
1. In Hyper-V Manager, select the **AzureArcVM (1)** VM, then select **Connect (2)** on the right.

    ![Screenshot of Hyper-V Manager showing the connect button for the AzureArcVM.](Images/upd-Hyperv3.png "Connect to AzureArcVM")  
    
1. Under Connect to AzureArcVM, click on **Connect** and then log into the VM with the **Administrator password**: **<inject key="SmartHotelHost Admin Password" />** (the login screen may pick up your local keyboard mapping, use the 'eyeball' icon to check).
 
    ![Screenshot of the Connect to AzureArcVM.](Images/updt-E1S13.png)
    
1. From the **Start (1)** menu of the AzureArcVM, search for **Windows Powershell (2)** and open it.

    ![Screenshot of the powershell.](Images/upd-powershell.png)
      
1. In powershell, run the whole script that you copied in the notepad earlier in step 12.

1. After running the script, packages will be installed and then you will be directed to a pop-up browser page to login into your azure account for authentication purpose.
   - Use with below Azure credentials.
    * Azure Username/Email: <inject key="AzureAdUserEmail"></inject> 
    * Azure Password: <inject key="AzureAdUserPassword"></inject> 

    **Note:** Now you have connected your AzureArcVM to Azure successfully.
    
    ![Screenshot of the powershellscript.](Images/upd-package.png)
     
 1. Close the AzureArcVM, and navigate to Azure portal and go back to the **Azure Arc** page, select **Servers (1)** under **Infrastructure** and now verify that a server is connected successfully **(2)**.

    **Note:** The name of the newly server added could be different.
    
    ![Screenshot of the server added.](Images/upd-serveradded.png)
     
    
     
