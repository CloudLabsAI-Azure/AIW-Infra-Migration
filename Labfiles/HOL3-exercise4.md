
# HOL3: Exercise 4: Failover the Infrastructure to Azure Cloud


### Estimated time: 35 minutes

In this exercise, you will deploy the Failover from on-premises to Azure. After setting up replication to Azure for on-premises machines, when your on-premises site goes down, you fail those machines over to Azure. After failover, Azure VMs are created from replicated data.

## Lab objectives

In this exercise, you will complete the following task:

- Task 1: Failover the Infrastructure to Azure Cloud

### Task 1: Failover the Infrastructure to Azure Cloud

1. In the **search resources, services and docs bar**, type **Recovery service vaults** and select it from suggestions, as shown below:
   
   ![Screenshot of the search Recovery service vaults.](Images/rsv.png "Recovery service vaults")
    
1. Under Recovery service vaults, click on **SmartHotelMigration<inject key="DeploymentID" enableCopy="false" />-MigrateVault-_xxxx_**.  

    ![Screenshot of the create Recovery service vaults.](Images/hol3-e2-s2.png "create Recovery service vaults")
    
1. On the **Recovery Service Vault page**, click on **Replicated Items (1)** under **Protected Items** and select **AzureArcVM (2)**.     

    ![Screenshot of the replicate items.](Images/upd-hol3-e4-s4.png "replicate items") 
    
1. On the **AzureArcVM** page, click on **Cleanup test Failover**.   

   ![Screenshot of the cleanup test failover.](Images/hol3-e3-s8.png "cleanup test failover") 
   
1. On the Test failover cleanup page, enter `Test failover ok.` under **Notes (1)** and make sure to **(2) check the box: Testing is complete. Delete test failover virtual machine(s)** and then click on **OK (3)**.

   > **Note:** Wait for the cleanup test failover to get completed successfully.
   
   ![Screenshot of the cleanup test failover.](Images/hol3-e3-s9.png "cleanup test failover") 
   
1. On the **AzureArcVM** page, click on **Failover**.

   ![Screenshot of the failover.](Images/hol3-e4-s5.png "failover") 
   
1. On the **Failover** page, review the settings and click on **Ok**.  

   ![Screenshot of the failover page.](Images/hol3-e4-s6.png "failover page") 
   
1. Go back to the Replicated items page and select **Site Recovery Jobs (1)** under **Monitoring** from the left-hand side panel and click on **Failover (2)** to view the job status.      

   ![Screenshot of the failover jobs.](Images/hol3-e4-s7.png "failover jobs") 
   
1. Wait for 10-15 minutes, for the job status of the failover to get completed successfully.

    ![Screenshot of the Failover status.](Images/H3E4S9.png "Failover status")    
   
1. After the Failover is completed successfully, move back to the **Replicated items** page and verify that the **Active Location** of the replicated **AzureArcVM** is now changed to **Microsoft Azure**.

   ![Screenshot of the failover done.](Images/hol3-e4-s10.png "failover done")  
   
   > **Note:** If you want to switch to a different recovery point to use for the failover, use **Change recovery point**.   
  
   ![Screenshot of the recovery points.](Images/hol3-e4-s14.png "recovery points") 
   
1. On the **replicated AzureArcVM** page, click on **Commit** to commit the failover (The Commit action deletes all the recovery points available with the service). 

   ![Screenshot of the commit.](Images/hol3-e4-s15.png "commit")
   
1. On the **Commit** page, click on **Ok**.   

   ![Screenshot of the commit page.](Images/hol3-e4-s16.png "commit page") 
   
1. After the Failover is **committed successfully**, go to the **search resources, services and docs** bar, type **Virtual Machines** and select it from suggestions.   

1. Under the **Virtual Machines** page, select the **AzureArcVM** which is automatically created from replicated data after a Failover.

    ![Screenshot of the vm-created.](Images/hol3-e4-s11.png "vm-created") 
   
1. On the **AzureArcVM** page, verify that the status of the VM is in **Running state**. 

    ![Screenshot of the vm-created status.](Images/hol3-e4-s13.png "vm-created status")  

    > **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
    > - Hit the Inline Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
    > - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
    > - If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help.
  
    <validation step="5f5a1f2a-bb3b-4f38-9f12-4b57af351efc" />

### Summary

In this exercise, you explored how to fail over on-premises physical servers that are replicating to Azure with Azure Site Recovery. After you've failed over, you fail back from Azure to your on-premises site when it's available.

Click on **Next** from the lower right corner to move on to the next page.
