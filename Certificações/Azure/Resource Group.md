deleting a resource group in Azure will also delete all the resources contained within that resource group. This includes virtual machines, storage accounts, databases, and any other resources provisioned within the resource group. It is important to be cautious when deleting a resource group as it will result in the permanent deletion of all resources within it.

A resource group in Azure can contain resources from multiple Azure regions. Resource groups are logical containers that hold related resources for an Azure solution. They help manage and organize resources and do not limit the resources to a specific region. This allows for flexibility in organizing resources across different regions within the same resource group.

Not all resource types in Azure support Tags. Some resource types may not have the capability to have Tags applied to them. It is essential to understand which resource types allow for the use of Tags and which do not in Azure.

Resources **don't** inherit the tags you apply to a resource group or a subscription.

![[{75128DD0-A335-4282-89D3-104451F161B0}.png]]

- A resource lock doesn't block the subscription cancellation.
    
- Azure preserves your resources by deactivating them instead of immediately deleting them.
    
- Azure only deletes your resources permanently after a waiting period.