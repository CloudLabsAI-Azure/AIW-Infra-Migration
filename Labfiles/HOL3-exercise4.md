# Exercise 04: Failover the infrastructure to Azure Cloud

### Estimated time: 35 minutes

## Overview

In this exercise, you will deploy the Failover from on-premises to Azure. After setting up replication to Azure for on-premises machines, when your on-premises site goes down, you fail those machines over to Azure. After failover, Azure VMs are created from replicated data.

## Lab objectives

In this exercise, you will complete the following task:

- Task 1: Failover the Infrastructure to Azure Cloud

## Task 1: Failover the Infrastructure to Azure Cloud

1. In the **search resources, services and docs bar**, type **Recovery services vaults (1)**. From the dropdown results under **Services**, click on **Recovery Services vaults (2)**.
   
   ![Screenshot of the search Recovery service vaults.](Images/image641.png "Recovery service vaults")
    
1. On the **Recovery service vaults**, click on **SmartHotelMigration<inject key="DeploymentID" enableCopy="false" />-MigrateVault-_xxxx_**.  

    ![Screenshot of the create Recovery service vaults.](Images/image642.png "create Recovery service vaults")
    
1. On the **Recovery Service Vault page**, click on **Replicated Items (2)** under **Protected Items (1)** section and select **AzureArcVM (3)**.     

    ![Screenshot of the replicate items.](Images/image643.png "replicate items") 
    
1. On the **AzureArcVM** page, click on **Cleanup test Failover**.   

   ![Screenshot of the cleanup test failover.](Images/image644.png "cleanup test failover") 
   
1. On the **Test failover cleanup** page, enter `Test failover ok.` under **Notes (1)** and make sure to **(2) check the box: Testing is complete. Delete test failover virtual machine(s)** and then click on **OK (3)**.

   > **Note:** Wait for the cleanup test failover to get completed successfully.
   
   ![Screenshot of the cleanup test failover.](Images/image645.png "cleanup test failover") 
   
1. On the **AzureArcVM** page, click on **Failover**.

   ![Screenshot of the failover.](Images/image646.png "failover") 
   
1. On the **Failover** page, review the settings and click on **Ok**.  

   ![Screenshot of the failover page.](Images/image647new.png "failover page") 
   
1. Go back to the Replicated items page and select **Site Recovery Jobs (2)** under **Monitoring (1)** from the left-hand side panel and click on **Failover (3)** to view the job status.      

   ![Screenshot of the failover jobs.](Images/image648.png "failover jobs") 
   
1. On the **Failover** page, wait for **10-15 minutes** for the failover job to complete. The **Status** column should show **Successful** for all key steps.

    ![Screenshot of the Failover status.](Images/image649.png "Failover status")    
   
1. After the Failover is completed successfully, go to **Protected items (1)** → **Replicated items (2)** and verify that the status of the replicated **AzureArcVM (3)** shows **Failover completed** with **Active location** as **Microsoft Azure**.

   ![Screenshot of the failover done.](Images/image6410a.png "failover done")  
   
   > **Note:** If you want to switch to a different recovery point to use for the failover, use **Change recovery point**.  
  
   ![Screenshot of the recovery points.](Images/image6410b.png "recovery points") 
   
1. On the **replicated AzureArcVM** page, click on **Commit** to commit the failover (The Commit action deletes all the recovery points available with the service).

   ![Screenshot of the commit.](Images/image6411.png "commit")
   
1. On the **Commit** page, click on **Ok**.   

   ![Screenshot of the commit page.](Images/image6412.png "commit page") 
   
1. After the Failover is **committed successfully**,  In the **Search resources, services, and docs** bar, type **Virtual Machines** **(1)** and select **Virtual machines (2)** from the Services.   

   ![Screenshot of the commit page.](Images/image6413.png "commit page") 

1. Under the **Virtual Machines** page, select the **AzureArcVM**, which is automatically created from replicated data after a Failover.

    ![Screenshot of the vm-created.](Images/image6414new.png "vm-created") 
   
1. On the **AzureArcVM** page, verify that the status of the VM is in the **Running state**.  

    ![Screenshot of the vm-created status.](Images/image6415.png "vm-created status")

    > **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
    > - Hit the Inline Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
    > - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
    > - If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help.

   <validation step="f44dc9dc-f959-4f70-9cbd-09949f72c0fb" />

## Summary

In this exercise, you explored how to fail over on-premises physical servers that are replicating to Azure with Azure Site Recovery. After you've failed over, you fail back from Azure to your on-premises site when it's available.

### You have successfully completed the Hands-on Lab.

