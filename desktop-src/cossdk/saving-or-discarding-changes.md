---
Description: Saving or Discarding Changes
ms.assetid: eba4e794-0929-450c-a172-6de6c2f2f2c4
title: Saving or Discarding Changes
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Saving or Discarding Changes

When you set properties on an item, no changes are actually recorded to the COM+ catalog until you explicitly save changes. You do this using the [**SaveChanges**](/windows/win32/ComAdmin/nf-comadmin-icatalogcollection-savechanges?branch=master) method on the [**COMAdminCatalogCollection**](/windows/win32/ComAdmin/?branch=master) object for the collection containing the item.

If you want to discard changes that have not yet been committed, you can call the [**Populate**](/windows/win32/ComAdmin/nf-comadmin-icatalogcollection-populate?branch=master) method on the [**COMAdminCatalogCollection**](/windows/win32/ComAdmin/?branch=master) object. This reads in all persistent data from the COM+ catalog for all items in the collection, effectively deleting any pending changes.

When you use [**SaveChanges**](/windows/win32/ComAdmin/nf-comadmin-icatalogcollection-savechanges?branch=master), any inconsistencies in property settings that you have chosen result in an error, and **SaveChanges** fails to write the object that returned the error. All properties on a given item either are written or fail to be written as a whole.

However, when write errors occur, they might not be due to incompatible settings; some other failure might have occurred. You need to inspect the details of the failure to be certain. For more information, see [Handling COM+ Administration Errors](handling-com--administration-errors.md) and [Interdependencies Between Properties](interdependencies-between-properties.md).

As a general rule, the more changes you attempt to save at once, particularly changes to multiple objects, the more likely you are to get an error and the more difficult it is to track down.

Additionally, between calls to [**Populate**](/windows/win32/ComAdmin/nf-comadmin-icatalogcollection-populate?branch=master) and [**SaveChanges**](/windows/win32/ComAdmin/nf-comadmin-icatalogcollection-savechanges?branch=master), you do not have a lock on the items in the collection; contention is possible. For more details, see [Getting and Setting Properties](getting-and-setting-properties.md).

## Related topics

<dl> <dt>

[Getting and Setting Properties](getting-and-setting-properties.md)
</dt> <dt>

[Interdependencies Between Properties](interdependencies-between-properties.md)
</dt> <dt>

[Querying for Available Properties](querying-for-available-properties.md)
</dt> </dl>

 

 


