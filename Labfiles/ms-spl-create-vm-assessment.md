# Lab 02: Set up your environment on Azure to migrate servers

### Estimated Duration: 90 Minutes

In this lab, you will use Azure Migrate: Server Assessment to assess the already discovered on-prem servers by creating a migration assessment in your Azure Migrate project and configuring dependencies for migration. Azure Migrate assessment is a feature within the Azure Migrate service that helps evaluate the readiness and suitability of on-premises workloads for migration to Azure. It analyzes data collected during the discovery phase to provide insights into performance, cost estimation, and compatibility

## Lab Objectives

In this lab, you will perform the following tasks:

- Task 1: Create a migration assessment
- Task 2: Configure dependency visualization

### Task 1: Create a migration assessment

In this task, you will use Azure Migrate to create a migration assessment for the SmartHotel application, using the data gathered during the discovery phase.

1. On **Azure Migrate | Servers, databases and web apps** page, select **Assess (1)** under **Azure Migrate: Discovery and assessment** and click on **Azure VM (2)** to start a new migration assessment.

    ![Screenshot of the Azure Migrate portal blade, with the '+Assess' button highlighted.](Images/assess-servers.png "Start assessment")

2. On the Basics blade, ensure the Assessment type is **Azure VM** and the Discovery Source is **Servers discovered from Migrate Appliance**. Under **Assessment settings**, select **Edit**.

    ![Screenshot of the Azure Migrate 'Assess servers' blade, showing the assessment name.](Images/create-assessment-edit.png "Assess servers - assessment name")

3. The **Assessment settings** blade allows you to tailor many of the settings used when making a migration assessment report. Take a few moments to explore the wide range of assessment properties. Hover over the information icons to see more details on each setting. Choose any settings you like, then select **Save**. (You have to make a change for the Save button to be enabled; if you don't want to make any changes, just close the blade.)

    ![Screenshot of the Azure Migrate 'Assessment properties' blade, showing a wide range of migration assessment settings.](Images/assessment-settings-save.png "Assessment properties")

4. Select **Next** to move to the **Select servers to assess** tab and enter the following information:
     
    - Assessment name: Enter **SmartHotelAssessment (1)** 
    - Select or create a group: Choose **Create New (2)**  
    - Enter the Group name: **SmartHotel VMs (3)**
    - Add machines to the Group:  Select **SmarthotelAppl(Hyper-V) (4)** from dropdown.
    - Select the **smarthotelweb1**, **smarthotelweb2**, **UbuntuWAF**, and **redhat** VMs **(5)** and
    - Click on **Next: Review+Create assessment (6)**.

        ![Screenshot of the Azure Migrate 'Assess servers' page. A new server group containing servers smarthotelweb1, smarthotelweb2, and UbuntuWAF.](Images/updt-hol1-e2-t1-s4.png "Assessment VM group")

        > **Note:** There is no need to include the **smarthotelSQL1**, **AzureMigrateAppliance** and other VMs in the assessment, since they will not be migrated to Azure.
    
        > **Note:** Please note that even though we are adding a **redhat** VM to the assessment here, we will not be setting up our environment in the RedHat VM in this exercise. Users will review the assessment and perform all the steps for environment setup in HOL2.
    
    
5. Click on **Create assessment** to create the assessment. 

    ![](Images/upd-hol1-e2-t1-s5.png)

6. In Azure Migrate, on the **Servers, databases, and web apps** blade, select **Refresh** periodically until the number of assessments shown is **1** (This may take a few minutes). Once the assessments count is updated, click on **1** that is next to **Total** under **Assessments**.  

    ![Screenshot from Azure Migrate showing the number of assessments as '1'.](Images/L2T1S6-2009.png "Azure Migrate - Assessments (count)")
    
7. Select **Assessments (1)** under **Azure Migrate: Discovery and assessment** to see **SmartHotelAssessment (2)** in the list of assessments.

    ![Screenshot showing a list of Azure Migrate assessments. There is only one assessment in the list. It has been highlighted.](Images/L2T1S7-2009.png "Azure Migrate - Assessments (list)")

### Task 2: Configure dependency visualization

In this task, you will configure the Azure Migrate dependency visualization feature. This requires you to first create a Log Analytics workspace, and then to deploy agents on the to-be-migrated VMs.

When migrating a workload to Azure, it is important to understand all workload dependencies. A broken dependency could mean that the application does not run properly in Azure, perhaps in hard-to-detect ways. Some dependencies, such as those between application tiers, are obvious. Other dependencies, such as DNS lookups, Kerberos ticket validation or certificate revocation checks, are not.

Azure Migrate dependency visualization helps you identify and map these dependencies by using agents installed on the machines to be migrated. The agents collect data about network connections and process activity, and send this data to a Log Analytics workspace. The data is then processed and presented in a graphical format in the Azure Migrate portal.

1. Return to the **Azure Migrate** blade in the Azure Portal, select **Servers, databases and web apps (1)**. Under **Discovery and assessment** select **Groups (2)**.

    ![](Images/upd-nwgrpopen.png)   

2. Under the **Groups (1)** pane, select the **SmartHotel VMs (2)** group to see the group details. 

    ![](Images/upd-hol1-e2-t2-s2.png)   

3. Note that each VM has their **Dependencies** status as **Requires agent installation**. Select **Requires agent installation** for the **smarthotelweb1** VM.

    ![Screenshot showing the SmartHotel VMs group. Each VM has dependency status 'Requires agent installation'.](Images/updt-hol1-e2-t2-s3.png "SmartHotel VMs server group")

4. On the **Dependencies** blade, select **Configure Log Analytics workspace**.

    ![Screenshot of the Azure Migrate 'Dependencies' blade, with the 'Configure OMS Workspace' button highlighted.](Images/L2T2S4-2009.png "Configure OMS Workspace link")

5. On the **Configure Log Analytics workspace** blade, provide the below information and select **Configure (4)**.

    - Log Analytics workspace: Click on **Create new (1)** and enter **AzureMigrateWS<inject key="DeploymentID" enableCopy="false" /> (2)**
    - Log Analytics workspace location: Select **East US (3)** from the dropdown.

        ![Screenshot of the Azure Migrate 'Configure OMS workspace' blade.](Images/L2T2S5-2009.png "OMS Workspace settings")

6. Wait for the workspace to be deployed. Once it is deployed, navigate to **AzureMigrateWS<inject key="DeploymentID" enableCopy="false" />** by clicking on it.

    ![Screenshot of the Azure Migrate 'Configure OMS workspace' blade.](Images/L2T2S6-2009.png "OMS Workspace settings")

7. On the **AzureMigrateWS<inject key="DeploymentID" enableCopy="false" />** page, select **Agents (1)** under **Settings** from the left navigation menu. Under Log analytics agent instructions, copy the **Workspace ID (2)** and **Primary Key (3)** and paste them into a text file for later use.

    ![Screenshot of part of the Azure Migrate 'Dependencies' blade, showing the OMS workspace ID and key.](Images/L2T2S7-2009.png "OMS Workspace ID and primary key")

8. Return to the Azure Migrate **Dependencies** blade. Right click on each of the 4 agent download URLs, select copy and paste them alongside the Workspace ID and key you noted in the previous step. 
   
    ![Screenshot of the Azure Migrate 'Dependencies' blade with the 4 agent download links highlighted.](Images/L2T2S8-2009.png "Agent download links")

9. From **Hyper-V Manager** console, select **smarthotelweb1 (1)** and select **Connect (2)**.

    ![Screenshot from Hyper-V manager highlighting the 'Connect' button for the smarthotelweb1 VM.](Images/HOL1-EX2-T2-S9.png "Connect to smarthotelweb1")

10. Select **Connect** again when prompted and log in to the **Administrator** account using the password **<inject key="SmartHotel Admin Password" />**.

11. Go to **Start** button in the **smarthotelweb1** VM. Search and select **Internet Explorer** to open it. Paste the link to the 64-bit Microsoft Monitoring Agent for Windows, which you noted earlier. When prompted, **Run** the installer.

     > **Note:** You may need to disable **Internet Explorer Enhanced Security Configuration** on **Server Manager** under **Local Server** to complete the download. 

    ![Screenshot showing the Internet Explorer prompt to run the installer for the Microsoft Monitoring Agent.](Images/upd-mma-win-run.png "Run MMA installer")

12. On the **Welcome to the Microsoft Monitoring Agent Setup Wizard** blade, select **Next**. 

    ![Screenshot for installing 64-bit Microsoft Monitoring Agent for Windows.](Images/L2T2S12-2009.png "MMA installation")

13. On the **Microsoft Software License Terms** blade, select **I Agree**.

    ![Screenshot for installing 64-bit Microsoft Monitoring Agent for Windows.](Images/L2T2S13-2009.png "MMA installation")

14. On the **Destination Folder** blade, leave everything as default and select **Next**. 

    ![Screenshot for installing 64-bit Microsoft Monitoring Agent for Windows.](Images/L2T2S14-2009.png "MMA installation") 

15. On the **Agent Setup Options** blade, select **Connect the agent to Azure Log Analytics (OMS) (1)** and select **Next (2)**.

    ![Screenshot for installing 64-bit Microsoft Monitoring Agent for Windows.](Images/L2T2S15-2009.png "MMA installation") 

16. On the **Azure Log Analytics** blade, enter the **Workspace ID and Workspace Key (1)** that you copied earlier, and select **Azure Commercial** from the Azure Cloud drop-down then select **Next (2)**.

    ![Screenshot of the Microsoft Monitoring Agent install wizard, showing the Log Analytics (OMS) workspace ID and key.](Images/L2T2S16-2009.png "MMA agent installer - workspace configuration")

17. On the **Microsoft Update** blade, leave everything as default and select **Next**. 

    ![Screenshot for installing 64-bit Microsoft Monitoring Agent for Windows.](Images/updt-mma7.png "MMA installation")

18. On the **Ready to Install** blade, click on **Install**.

    ![Screenshot for installing 64-bit Microsoft Monitoring Agent for Windows.](Images/mma5.png "MMA installation")

19. Select **Finish** to finish the installation process of **Microsoft Monitoring Agent for Windows**.

    ![Screenshot for installing 64-bit Microsoft Monitoring Agent for Windows.](Images/upd-mma6.png "MMA installation")

20. Paste the link to the **Dependency Agent Windows installer** into the browser address bar. **Run** the installer.

    ![Screenshot showing the Internet Explorer prompt to run the installer for the Dependency Agent.](Images/upd-da-win-run.png "Run Dependency Agent installer")

21. On the **License Agreement** blade, select **I Agree** to accept the agreement and continue. 

    ![Screenshot for installing Dependency Agent.](Images/dependencyagent1.png "Dependency Agent installation") 

22. On the **Completing Dependency Agent Setup** blade, select **Finish** to finish the installation process.

    ![Screenshot for installing Dependency Agent.](Images/dependencyagent2.png "Dependency Agent installation") 

    > **Note:** You do not need to configure the workspace ID and key when installing the Dependency Agent, since it uses the same settings as the Microsoft Monitoring Agent, which must be installed beforehand.

23. Close the virtual machine connection window for the **smarthotelweb1 VM**. Connect to the **smarthotelweb2 VM** and repeat the installation process (steps 10-22) for both agents (the administrator password is the same as for smarthotelweb1). Close the virtual machine connection window for the **smarthotelweb2 VM** once the installation of agents is done.

24. On you HostVM, open a command prompt using the desktop shortcut.  

    > **Note:** The SmartHotelHost runs Windows Server 2019 with the Windows Subsystem for Linux enabled. This allows the command prompt to be used as an SSH client. More info of supported Linux on Azure can be found here: https://Azure.com/Linux. 

25. Enter the following command to connect to the **UbuntuWAF** VM running in Hyper-V on the SmartHotelHost:

    ```bash
    ssh demouser@192.168.0.8
    ```

26. Enter 'yes' when prompted whether to connect. Use the password **<inject key="SmartHotel Admin Password" />**.

    ![Screenshot showing the command prompt with an SSH session to UbuntuWAF.](Images/L2T2S23-2009.png "SSH session with UbuntuWAF")

27. Enter the following command, followed by the password **<inject key="SmartHotel Admin Password" />** when prompted:
  
    ```
    sudo -s
    ```

    > This gives the terminal session elevated privileges.

28. Enter the following command, substituting \<Workspace ID\> and \<Primary Key\> with the values copied previously. Answer **Yes** when prompted to restart services during package upgrades without asking.  

    ```
    wget https://raw.githubusercontent.com/Microsoft/OMS-Agent-for-Linux/master/installer/scripts/onboard_agent.sh && sh onboard_agent.sh -w <Workspace ID> -s <Primary Key>
    ```
    
    > **Note:** If you receive any error while running the above command, run the below command to update the packages and perform **Step 28** again.
     
     ```
     apt-get update
     ```

29. Enter the following command, substituting \<Workspace ID\> with the value copied earlier:

    ```s
    /opt/microsoft/omsagent/bin/service_control restart <Workspace ID>
    ```

30. Enter the following command. This downloads a script that will install the Dependency Agent.

    ```s
    wget --content-disposition https://aka.ms/dependencyagentlinux -O InstallDependencyAgent-Linux64.bin
    ```

31. Install the dependency agent by running the script downloaded in the previous step.

    ```s
    sh InstallDependencyAgent-Linux64.bin -s
    ```

    ![Screenshot showing that the Dependency Agent install on Linux was successful.](Images/L2T2S31-2009.png "Dependency Agent installation was successful")
    

32. Return to the Azure Portal and refresh the Azure Migrate **SmartHotel VMs** VM group blade. The 3 VMs on which the dependency agent was installed should now show their status as **Installed**. (If not, refresh the page **using the browser refresh button**, not the refresh button in the blade.  It may take up to **5 minutes** after installation for the status to be updated.)

    ![Screenshot showing the dependency agent installed on each VM in the Azure Migrate VM group.](Images/upd-dependency-viz-installed.png "Dependency agent installed")
   
     >**Note:** If you notice that the dependency agent status is showing as **Requires Agent Installation** instead of Installed even after installing dependency agents in all the three VMs, please follow the steps from [here](https://github.com/CloudLabsAI-Azure/Know-Before-You-Go/blob/main/AIW-KBYG/AIW-Infrastructure-Migration.md#4-exercise1---task6---step1) to confirm dependency agent installation in VMs using Log Analytics workspace.
 
33. Select **View dependencies**.

    ![Screenshot showing the view dependencies button in the Azure Migrate VM group blade.](Images/upd-view-dependencies.png "View dependencies")
   
34. Take a few minutes to explore the dependencies view. Expand each server to show the processes running on that server. Select a process to see process information. See which connections each server makes.

    ![Screenshot showing the dependencies view in Azure Migrate.](Images/dependencies1.png "Dependency map")
    
## Summary 

In this lab, you created a migration assessment for the SmartHotel application using Azure Migrate and configured dependency visualization by creating a Log Analytics workspace and installing agents on the VMs to be migrated.

### You have successfully completed the lab. Click on **Next >>** to proceed with the next lab.

![](./Images/next-page-2009.png)