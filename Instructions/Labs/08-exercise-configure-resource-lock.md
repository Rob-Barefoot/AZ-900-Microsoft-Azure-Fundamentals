---
lab:
    title: 'Exercise - Configure resource locks'
    module: 'Module 02 - Describe features and tools in Azure for governance and compliance'
---
<!--
Edit the metadata above to manage the list of exercises in the home page of the GitHub site that gets generated.
You can delete the module and edit index.md in the root of the repo to customize the display so that only the exercises are listed
To enable GitHub page publishing, edit the Page settings for the repo and publish from the main branch
-->

# Configure resource locks <!-- match title in metadata above (and Learn Exercise unit and ILT slide)-->

In this exercise, you use resource locks to prevent accidental deletion of a file.

This exercise should take approximately **15** minutes to complete. <!-- update with estimated duration -->

## Task 1: Create a resource group
In this task, you'll create a resource group. By creating a resource group for this exercise, it will make it easier to clean up the exercise when you're complete.

1. Log into the [Azure portal](https://portal.azure.com/?azure-portal=true).
1. Select **Resource groups**.
1. Select **Create**.
1. Select the subscription you will use for this exercise from the **Subscription** dropdown list.
1. Enter **IntroAzureRG** for the resource group name.
1. Select **Central US** as the region.


## Task 2: Create a resource

In order to apply a resource lock, you have to have a resource created in Azure. The first task focuses on creating a resource that you can then lock in subsequent tasks.

1.  Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com/?azure-portal=true)
2.  Select **Create a resource**.
3.  Under Categories, select **Storage**.
4.  Under Storage Account, select **Create**.
5.  On the Basics tab of the Create storage account blade, fill in the following information. Leave the defaults for everything else.
    
    | **Setting**          | **Value**                           |
    | -------------------- | ----------------------------------- |
    | Resource group       | Select **IntroAzureRG**             |
    | Storage account name | enter a unique storage account name |
    | Location             | default                             |
    | Performance          | Standard                            |
    | Redundancy           | Locally redundant storage (LRS)     |
6.  Select **Review + Create** to review your storage account settings and allow Azure to validate the configuration.
7.  Once validated, select **Create**. Wait for the notification that the account was successfully created.
8.  Select **Go to resource**.

## Task 3: Apply a read-only resource lock

In this task you apply a read-only resource lock to the storage account. What impact do you think that has on the storage account?

1.  Scroll down until you find the Settings section of the blade on the left of the screen.
2.  Select Locks.
3.  Select + Add.
4.  Enter a Lock name.
5.  Verify the Lock type is set to Read-only.
6.  Select OK.

## Task 4: Add a container to the storage account

In this task, you add a container to the storage account. This container is where you can store your blobs.

1.  Scroll up until you find the Data storage section of the blade on the left of the screen.
2.  Select Containers.
3.  Select + Container.
4.  Enter a container name and select Create.
5.  You should receive an error message: Failed to create storage container.

> [!NOTE]
> The error message lets you know that you couldn't create a storage container because a lock is in place. The read-only lock prevents any create or update operations on the storage account, so you're unable to create a storage container.

## Task 5: Modify the resource lock and create a storage container

1.  Scroll down until you find the Settings section of the blade on the left of the screen.
2.  Select Locks.
3.  Select the read-only resource lock you created.
4.  Change the Lock type to Delete and select OK.   
5.  Scroll up until you find the Data storage section of the blade on the left of the screen.
6.  Select Containers.
7.  Select + Container.
8.  Enter a container name and select Create.
9.  Your storage container should appear in your list of containers.

You can now understand how the read-only lock prevented you from adding a container to your storage account. Once the lock type was changed (you could have removed it instead), you were able to add a container.

## Task 6: Delete the storage account

You'll actually do this last task twice. Remember that there's a delete lock on the storage account, so you won't actually be able to delete the storage account yet.

1.  Scroll up until you find Overview at the top of the blade on the left of the screen.
2.  Select Overview.
3.  Select Delete.
    

You should get a notification letting you know you can't delete the resource because it has a delete lock. In order to delete the storage account, you need to remove the delete lock.

## Task 7: Remove the delete lock and delete the storage account

In the final task, you remove the resource lock and delete the storage account from your Azure account. This step is important. You want to make sure you don't have any idle resource just sitting in your account.

1.  Select your storage account name in the breadcrumb at the top of the screen.
2.  Scroll down until you find the Settings section of the blade on the left of the screen.
3.  Select Locks.
4.  Select Delete.
5.  Select Home in the breadcrumb at the top of the screen.
6.  Select Storage accounts
7.  Select the storage account you used for this exercise.
8.  Select Delete.
9.  To prevent accidental deletion, Azure prompts you to enter the name of the storage account you want to delete. Enter the name of the storage account and select Delete.
10. You should receive a message that the storage account was deleted. If you go Home &gt; Storage accounts, you should see that the storage account you created for this exercise is gone.

## Task 8: Clean up

To clean up the assets created in this exercise and avoid unnecessary costs, delete the resource group (and all associated resources).
1. From the Azure home page, under Azure services, select **Resource groups**.
1. Select the **IntroAzureRG** resource group.
1. Select **Delete resource group**.
1. Enter `IntroAzureRG` to confirm deletion of the resource group and select delete.

Congratulations! You've completed configuring, updating, and removing a resource lock on an Azure resource.
