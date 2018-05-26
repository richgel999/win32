---
Description: The HCRYPTHASH data type is used to represent handles to hash objects.
ms.assetid: 3b872bf0-cf1b-465b-82a2-c6fd154e1125
title: HCRYPTHASH
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# HCRYPTHASH

The **HCRYPTHASH** data type is used to represent handles to [*hash objects*](security.h_gly#-security-hash-object-gly). These handles indicate to the CSP module which hash is being used in a particular operation. The CSP module does not enable direct manipulation of the hash values. Instead, the user manipulates the hash values through the hash handle.


```C++
typedef ULONG_PTR HCRYPTHASH;
```



## Requirements



|                                     |                                                                                       |
|-------------------------------------|---------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows XP \[desktop apps only\]<br/>                                           |
| Minimum supported server<br/> | Windows Server 2003 \[desktop apps only\]<br/>                                  |
| Header<br/>                   | <dl> <dt>Wincrypt.h</dt> </dl> |



 

 



