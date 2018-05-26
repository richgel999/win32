---
Description: Retrieves data from the Apphelp details database.
ms.assetid: f3731561-bf3f-4139-9890-bd4ce73d83fa
title: SdbReadApphelpDetailsData function
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# SdbReadApphelpDetailsData function

Retrieves data from the Apphelp details database.

## Syntax


```C++
BOOL WINAPI SdbReadApphelpDetailsData(
  _In_  PDB           pdb,
  _Out_ PAPPHELP_DATA pData
);
```



## Parameters

<dl> <dt>

*pdb* \[in\]
</dt> <dd>

A handle to the Apphelp details database, Apphelp.sdb.

</dd> <dt>

*pData* \[out\]
</dt> <dd>

An [**APPHELP\_DATA**](apphelp-data.md) structure.

</dd> </dl>

## Return value

The function returns **TRUE** on success or **FALSE** on failure.

## Requirements



|                                     |                                                                                        |
|-------------------------------------|----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                         |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/>                                   |
| DLL<br/>                      | <dl> <dt>Apphelp.dll</dt> </dl> |



 

 



