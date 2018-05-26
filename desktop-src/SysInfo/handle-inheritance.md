---
Description: A child process can inherit handles from its parent process. An inherited handle is valid only in the context of the child process. To enable a child process to inherit open handles from its parent process, use the following steps.
ms.assetid: 957cd369-bebf-4e04-9f7e-a936e2e97887
title: Handle Inheritance
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Handle Inheritance

A child process can inherit handles from its parent process. An inherited handle is valid only in the context of the child process. To enable a child process to inherit open handles from its parent process, use the following steps.

1.  Create the handle with the **bInheritHandle** member of the [**SECURITY\_ATTRIBUTES**](https://msdn.microsoft.com/library/windows/desktop/aa379560) structure set to **TRUE**.
2.  Create the child process using the [**CreateProcess**](https://msdn.microsoft.com/library/windows/desktop/ms682425) function, with the *bInheritHandles* parameter set to **TRUE**.

The [**DuplicateHandle**](duplicatehandle.md) function duplicates a handle to be used in the current process or in another process. If an application duplicates one of its handles for another process, the duplicated handle is valid only in the context of the other process.

A duplicated or inherited handle is a unique value, but it refers to the same object as the original handle. Processes can inherit or duplicate handles to the following types of objects:

-   Access Token
-   Communications device
-   Console input
-   Console screen buffer
-   Desktop
-   Directory
-   Event
-   File
-   File mapping
-   Job
-   Mailslot
-   Mutex
-   Pipe
-   Process
-   Registry key
-   Semaphore
-   Socket
-   Thread
-   Timer
-   Window station

All other objects are private to the process that created them; their object handles cannot be duplicated or inherited.

For more information, see [Inheritance](https://msdn.microsoft.com/library/windows/desktop/ms683463).

 

 


