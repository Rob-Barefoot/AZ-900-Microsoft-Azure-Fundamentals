---
lab:
    title: 'Exercise - Create an Azure resource'
    module: 'Module 01 - Describe the core architectural components of Azure'
---
<!--
Edit the metadata above to manage the list of exercises in the home page of the GitHub site that gets generated.
You can delete the module and edit index.md in the root of the repo to customize the display so that only the exercises are listed
To enable GitHub page publishing, edit the Page settings for the repo and publish from the main branch
-->

# Create a Microsoft Azure resource <!-- match title in metadata above (and Learn Exercise unit and ILT slide)-->

In this exercise, you’ll use the Azure portal to create a resource. The focus of the exercise is observing how Azure resource groups populate with created resources.

This exercise should take approximately **10** minutes to complete. <!-- update with estimated duration -->

## Task 1: Create a resource group
In this task, you'll create a resource group. By creating a resource group for this exercise, it will make it easier to clean up the exercise when you're complete.

1. Log into the [Azure portal](https://portal.azure.com/?azure-portal=true).
1. Select **Resource groups**.
1. Select **Create**.
1. Select the subscription you will use for this exercise from the **Subscription** dropdown list.
1. Enter **IntroAzureRG** for the resource group name.
1. Select **Central US** as the region.

## Task 2: Create a virtual machine

In this task, you’ll create a virtual machine using the Azure portal.

1.  Sign in to the [Azure portal](https://portal.azure.com/learn.docs.microsoft.com?azure-portal=true).
2.  Select Create a resource &gt; Compute &gt; Virtual Machine &gt; Create.
3.  The Create a virtual machine pane opens to the basics tab.
4.  Verify or enter the following values for each setting. If a setting isn’t specified, leave the default value.
    
    **Basics tab**
    
    | **Setting**                  | **Value**                                                  |
    | ---------------------------- | ---------------------------------------------------------- |
    | Subscription                 | Select the subscription you selected in Task 1.            |
    | Resource group               | IntroAzureRG                                               |
    | Virtual machine name         | my-VM                                                      |
    | Region                       | Leave default                                              |
    | Availability options         | Leave default                                              |
    | Security type                | Leave default                                              |
    | Image                        | Leave default                                              |
    | VM architecture              | Leave default                                              |
    | Run with Azure Spot discount | Unchecked                                                  |
    | Size                         | Leave default                                              |
    | Authentication type          | Password                                                   |
    | Username                     | azureuser                                                  |
    | Password                     | Enter a custom password                                    |
    | Confirm password             | Reenter the custom password                                |
    | Public inbound ports         | None                                                       |

5.  Select Review and Create.

6.  Select Create

Wait while the VM is provisioned. Deployment is in progress will change to Deployment is complete when the VM is ready.

## Task 3: Verify resources created

Once the deployment is created, you can verify that Azure created not only a VM, but all of the associated resources the VM needs.

1.  Select **Home**
2.  Select **Resource groups**
3.  Select the **IntroAzureRG** resource group

You should see a list of resources in the resource group. By default, Azure gave them all a similar name to help with association and grouped them in the same resource group.

Congratulations! You've created a resource in Azure and had a chance to see how resources get grouped on creation.

## Clean up
1. From the Azure home page, under Azure services, select **Resource groups**.
1. Select the **IntroAzureRG** resource group.
1. Select **Delete resource group**.
1. Enter `IntroAzureRG` to confirm deletion of the resource group and select delete.
