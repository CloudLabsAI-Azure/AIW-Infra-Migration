# Guided Lab : Infrastructure Migration
 
### Overall Estimated Duration: 6 Hours

## Overview
In this lab, you will onboard on-premises Hyper-V VMs to Azure Arc by deploying the Azure Connected Machine Agent on a Windows VM. This will enable you to manage the VM through Azure Arc. By the end, you'll gain hands-on experience extending Azure management to your hybrid and on-premises resources.

## Objectives
In this lab, you will learn how to onboard on-premises Hyper-V virtual machines to Azure Arc for management. By the end of this lab, you will be able to:

- **Run Workloads Anywhere and manage with Azure Arc:** Deploy the Azure Connected Machine Agent on a Windows VM to enable management through Azure Arc and extend Azure's management capabilities to your on-premises and hybrid environments.

## Pre-requisites
To successfully complete this lab, you should have basic knowledge of Microsoft Azure, Hyper-V virtualization, and virtual machine management. Familiarity with using the Azure portal, configuring storage accounts, and understanding fundamental networking and security concepts is also recommended.

## Architecture
In this hands-on lab, you will onboard on-premises Hyper-V virtual machines (VMs) to Azure Arc for management. The process starts by deploying the Azure Connected Machine Agent on a Windows VM outside Azure. Once installed, the VM is registered with Azure Arc, enabling it to be managed directly from the Azure portal. This architecture allows you to extend Azure’s management capabilities to your on-premises resources, providing centralized control over both cloud and hybrid environments. Throughout the lab, you will follow best practices for integrating, securing, and managing your hybrid infrastructure.

## Architecture Diagram

## Getting Started with the Lab
Once the environment is provisioned, a virtual machine (LabVM) and lab guide will be loaded in your browser. Use this virtual machine throughout the workshop to perform the lab. You can see the number on the bottom of the Lab guide to switch to different exercises in the lab guide.

## Accessing Your Lab Environment
 
Once you're ready to dive in, your virtual machine and Guide will be right at your fingertips within your web browser.

   ![](./Images/LAB5GETSTART.png)

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

   ![](./Images/GS4new12.png)

### Happy Learning!!
