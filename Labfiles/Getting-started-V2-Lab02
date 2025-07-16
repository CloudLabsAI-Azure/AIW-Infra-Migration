# Guided Lab : Infrastructure Migration
 
### Overall Estimated Duration: 4 Hours

## Overview
In this hands-on lab, you will go through the end-to-end process of migrating Windows Servers from a Hyper-V environment to Microsoft Azure using Azure Migrate. You will begin by creating a storage account in Azure to hold the data for virtual machine migration. Next, you will register your Hyper-V host with the Azure Migrate service and configure the Azure Site Recovery provider for replication.

Once registration is complete, you will enable replication for virtual machines from your on-premises environment to Azure, ensuring that data is synced and ready for migration. Following this, you will migrate the selected virtual machines to Azure and validate the migration process. The lab also covers key networking and security best practices to ensure your migrated VMs are securely integrated into the Azure environment. By the end of the lab, you will have a solid understanding of how to migrate workloads to Azure and ensure their readiness for cloud deployment.

## Objectives
Learn how to prepare, replicate, and migrate Windows Servers from an on-premises Hyper-V environment to Azure using Azure Migrate. By the end of this lab, you will be able to:

- **Migrate Windows Servers from Hyper-V to Azure:** Successfully migrate Windows Servers from Hyper-V to Azure by preparing the environment, configuring replication, executing the migration, and applying core networking and security best practices.

## Pre-requisites
To effectively complete this lab, you need basic knowledge of Microsoft Azure, Hyper-V virtualization, and virtual machine management. You should also be familiar with using the Azure portal, configuring storage accounts, and understanding fundamental networking and security concepts.

## Architecture
In this hands-on lab, you will work through the architecture flow illustrated in the diagram, focusing on discovering, replicating, and migrating Windows Servers from a Hyper-V environment to Azure. You’ll start by registering your on-premises Hyper-V host with Azure Migrate and deploying the Azure Site Recovery provider. Next, you’ll enable replication to synchronize your virtual machines’ data to an Azure Storage account. Finally, you’ll perform the migration of these VMs to Azure as IaaS instances. Throughout the lab, you’ll apply networking and security best practices to ensure a secure and efficient cloud migration.

## Architecture Diagram

## Getting Started with the Lab
Once the environment is provisioned, a virtual machine (LabVM) and lab guide will be loaded in your browser. Use this virtual machine throughout the workshop to perform the lab. You can see the number on the bottom of the Lab guide to switch to different exercises in the lab guide.

## Accessing Your Lab Environment
 
Once you're ready to dive in, your virtual machine and Guide will be right at your fingertips within your web browser.

   ![](./Images/30052025(1)new.png)

## Virtual Machine & Lab Guide
 
Your virtual machine is your workhorse throughout the workshop. The lab guide is your roadmap to success.
 
## Exploring Your Lab Resources
 
To get a better understanding of your lab resources and credentials, navigate to the **Environment** tab.

   ![](./Images/30052025(2)new.png)
 
## Utilizing the Split Window Feature
 
For convenience, you can open the lab guide in a separate window by selecting the **Split Window** button from the Top right corner.
 
   ![](./Images/30052025(3)new.png)
 
## Managing Your Virtual Machine
 
Feel free to **Start**, **Stop**, or **Restart** your virtual machine as needed from the **Resources** tab. Your experience is in your hands!
 
  ![](./Images/30052025(4)new.png)

## Lab Guide Zoom In/Zoom Out

To adjust the zoom level for the environment page, click the **A↕ : 100%** icon located next to the timer in the lab environment.

   ![](./Images/30052025(5)new.png)
 
## Let's Get Started with Azure Portal
 
1. On your virtual machine, click on the **Azure Portal** icon as shown below:
 
    ![](./Images/GS1new.png)
 
2. You'll see the **Sign into Microsoft Azure** tab. Here, enter your credentials:
 
   - **Email/Username:** <inject key="AzureAdUserEmail"></inject>
 
      ![](./Images/GS2new.png)
 
3. Next, provide your password:
 
   - **Password:** <inject key="AzureAdUserPassword"></inject>
 
      ![](./Images/GS3new.png)

4. If **Action required** pop-up window appears, click on **Ask later**.

      ![](./Images/ask-later-01new.png)
 
4. If you see the pop-up **Stay Signed in?**, click **No**.

      ![](./Images/GS9new.png)

6. If a **Welcome to Microsoft Azure** pop-up window appears, click **Cancel** to skip the tour.

7. Now you will see the Azure Portal Dashboard, click on **Resource groups** from the Navigate panel to see the resource groups.

   ![](Images/select-rgnew.png "Resource groups")
   
8. Confirm you have all resource groups present as shown below.

   ![](Images/upimage10new.png "Resource groups")
 
## Support Contact
The CloudLabs support team is available 24/7, 365 days a year, via email and live chat to ensure seamless assistance at any time. We offer dedicated support channels tailored specifically for both learners and instructors, ensuring that all your needs are promptly and efficiently addressed.

Learner Support Contacts:

- Email Support: labs-support@spektrasystems.com
- Live Chat Support: https://cloudlabs.ai/labs-support

Now, click on the **Next** button in the lower right corner to move to the next page.

   ![](./Images/GS4new.png)

### Happy Learning!!
