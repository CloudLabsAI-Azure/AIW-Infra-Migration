# Exercise 03: Set Up Test Failover

### Estimated time: 30 Minutes

## Overview

In this exercise, you will perform a test failover of a replicated virtual machine, allowing you to validate the health of the virtualized workload without interrupting your production workload or ongoing replication.

## Lab objectives

In this exercise, you will complete the following task:

- Task 1: Set Up Test Failover

## Task 1: Set Up Test Failover

1. On the **Recovery Services vault** page, expand **Protected Items (1)**, click **Replicated Items (2)**, and select **AzureArcVM (3)** that you replicated in the previous exercise.

    ![Screenshot of the replicate items.](Images/image621.png "replicate items") 
   
1. On the **AzureArcVM** page, click on **Test Failover**.  

    ![Screenshot of the Test Failover.](Images/image622.png "Test Failover") 
   
1. On the **Test failover** page, select **SmartHotelVNet (1)** under **Azure virtual network** and click **OK (2)** to initiate the test failover.

    ![Screenshot of the Test Failover page.](Images/image623.png "Test Failover page") 
    
1. Go back to the **Replicated items** page. Under **Monitoring (1)** in the left-hand panel, select **Site Recovery jobs (2)** and then click **Test failover (3)** to view the job status.

    ![Screenshot of the Test Failover status](Images/image624.png "Test Failover status")

1. On the **Test failover** job details page, wait for **10–15 minutes** for the **Test failover** job to complete successfully and reflect the **Successful** status across key steps in the job list.

    ![Screenshot of the Test Failover status.](Images/image625.png "Test Failover status") 
  
1. In the **Search resources, services, and docs** bar, type **Virtual Machines** **(1)** and select **Virtual machines** from the Services **(2)**.

    ![](Images/image626.png "Test Failover status")

1. On the **Virtual machines** page, select **AzureArcVM-test**, which is automatically created after the test failover.

    ![Screenshot of the Test vm.](Images/image627new.png "Test vm") 
  
1. On the **AzureArcVM-test** page, confirm the VM is in **Running** state **(1)**, then click **Connect** **(2)** and select **Connect** from the dropdown **(3)**. On the **Connect** pane, under **Most common**, select **Download RDP file** to connect via **Native RDP**.   

    ![Screenshot of the Test vm status.](Images/image628.png "Test vm status") 

    ![Screenshot of the Test vm status.](Images/image629.png "Test vm status") 
    

## Summary

In this exercise, you learned how to validate a replication and disaster recovery strategy by performing a test failover without any data loss or downtime.

Now, click on the **Next** button in the lower right corner to move to the next page.

   ![](./Images/Lab06-Nextpagebutton.png)
