# Exercise 2: Creating VM Scale sets from Azure VMs

### Estimated Duration: 3 hours

## Overview

In this exercise, you will create a Virtual Machine Scale Set (VMSS) from an existing VM image to enable scalability and high availability. You will also enable Azure Automanage to automatically apply best practices for backup, monitoring, and security on a virtual machine.

## Lab objectives

After completing this exercise, you will:
- Task 1: Using VM Scale Sets to Drive Business Resiliency
- Task 2: Enabling Azure Automanage on Virtual Machines

1. If you are not logged in already, click on the Azure portal shortcut that is available on the desktop and log in with the below Azure credentials.
    
    * Azure Username/Email: <inject key="AzureAdUserEmail"></inject> 
    
    * Azure Password: <inject key="AzureAdUserPassword"></inject>


## Task 1: Using VM Scale Sets to Drive Business Resiliency

In this task, you will capture a specialized image from an existing virtual machine and use it to create a Virtual Machine Scale Set (VMSS). This enables scalable deployment of identical VMs, ensuring high availability and consistent performance for business-critical applications.

1. In the Azure portal, go to **Resource groups**, select **SmartHotelHostRG (1)**, then click on **smarthotelweb1 (2)** to begin creating an image.

   ![](Images/rg-of-lab03new.png)


5. On the VM page, click **Capture (1)** from the top menu and select **Image (2)** from the dropdown.
   
   ![](Images/upd-capture-1new.png)

6. Under **Project details**, ensure the Resource group is set to **SmartHotelHostRG (1)**, then under **Instance details**, select **Yes, share it to a gallery as a VM image version (2)**.

   ![](Images/create-image-6-0407new1.png)

7. In **Gallery details**, create a new gallery by selecting **Create new (1)** and enter **imagemigration<inject key="DeploymentID" enableCopy="false" /> (2)** and click **Ok (3)**.

   ![](Images/create-image-7-0407new.png)

9. In the **Operating System state**, select **Specialized (1)**, then click **Create new (2)** under image definition to create a new VM image definition and click **Ok (7)**.

   - Image VM definition name: **imagedefinition<inject key="DeploymentID" enableCopy="false" /> (2)**

   - Publisher: **Microsoft (4)**
    
   - Offer: **windows (5)**
  
   - SKU: **migration (6)**

       ![](Images/create-image-9-0407new.png)

10. Set the **Version number** to **1.0.0 (1)**, then click **Review + create (2)** to proceed.

       ![](Images/img-ver-lab03.png)

12. After validation passes, select **Create** to create the image and wait for the image creation.

       ![](Images/lab02-cret-res.png)

13.  Once the image is created, click on **Go to resource**. 

       ![](Images/lab03-clk-gtr-01.png)

13. On the VM image version page, click **Create VMSS** on the top menu to start creating a Virtual Machine Scale Set using this image.

    ![](Images/image-overview-0407new.png)

14. On the **Create a Virtual Machine Scale Set (VMSS)** page, under **Basics** tab, select the **SmartHotelHostRG (1)** resource group, enter **migrationscaleset<inject key="DeploymentID" enableCopy="false" /> (2)** as the **Virtual machine scale set name**.

    ![](Images/createvmss1-0407new.png)

16. Select the **VM size** as **Standard D2s v3 (1)**, choose **Windows server (2)** as the **License type**, and then click **Review + create (3)** to proceed.

     ![](Images/createvmss2-0407new.png)

    > **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
    > - Hit the Inline Validate button for the corresponding task. If you receive a success message, you can proceed to the next task.
    > - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
    > - If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.
    
    <validation step="3435fc35-adbc-4789-885e-d2231cc767d4" />

   In this task, you have created an Image from the smarhotelweb1 virtual machine, and using that image, you successfully created a Virtual machine scale set (VMSS).

## Task 2: Enabling Azure Automanage on Virtual Machines

Azure Automanage automatically configures best practice services like backup, monitoring, and security on your virtual machines. When enabled on an existing machine, it applies these configurations without manual setup. This helps ensure compliance, operational efficiency, and reduces management overhead. In this task, you will enable Automanage on existing machines.

1. If you are not logged in already, click on the Azure portal shortcut that is available on the desktop and log in with below Azure credentials below.
    
    * Azure Username/Email: <inject key="AzureAdUserEmail"></inject> 
    
    * Azure Password: <inject key="AzureAdUserPassword"></inject>

2. In the search bar, search for and select **Automanage**.

3. From the left side panel select **Automanage machines (1)** and click on **+Enable on existing VM (2)**.
   
   ![](Images/T2S3-0407.png)

4. Under **Configuration profile**, select your profile type: **Azure Best Practices - Production or Azure Best Practices - Dev/Test, or Custom profile**.
   
   ![](Images/upd-existing-vm-quick-create.png)
   
   > Click **View best practice profiles** to see the differences between the environments.
    
   ![](Images/upd-browse-production-profile.png)

5. On the **Select Machines** blade:

   a. Filter the list by your Subscription and Resource group and click on **Check eligibility on machines (1)**.
   
   b. **Check the checkbox of the virtual machine (2)** you want to onboard. (for example: let's enable automanage for smarthotelweb2.)
   
   c. Click the **Review + Create (3)** button.
   
   ![](Images/updt-existing-vm-select-machine.png)

6. Click **Create**.

   In this task, you have successfully enabled Automanage on a virtual machine. 

## Summary

In this lab, you learned about:
 - How to create an image using an existing virtual machine
 - How to create a Virtual Machine Scale Set (VMSS) using the image
 - and how to enable Automanage on a virtual machine.

## You have successfully completed the Lab

