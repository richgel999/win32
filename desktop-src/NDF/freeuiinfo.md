---
title: FreeUiInfo function
description: Deallocates the memory allocated internally to a UiInfo structure.
ms.assetid: 41d923fd-2fb3-406e-a5cf-f3ba475685f6
keywords:
- FreeUiInfo function NDF
topic_type:
- apiref
api_name:
- FreeUiInfo
api_location:
- ndattributils.h
api_type:
- HeaderDef
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# FreeUiInfo function

The **FreeUiInfo** function deallocates the memory allocated internally to a [**UiInfo**](/windows/win32/ndattrib/ns-ndattrib-taguiinfo?branch=master) structure. This function calls [**CoTaskMemFree**](https://msdn.microsoft.com/library/windows/desktop/ms680722) to deallocate memory.

## Syntax


```C++
VOID FreeUiInfo(
  _In_ UiInfo *pInfo
);
```



## Parameters

<dl> <dt>

*pInfo* \[in\]
</dt> <dd>

Type: **[**UiInfo**](/windows/win32/ndattrib/ns-ndattrib-taguiinfo?branch=master)\***

The structure. The allocated memory pointed to by this structure will be freed.

</dd> </dl>

## Return value

This function does not return a value.

## Requirements



|                                     |                                                                                            |
|-------------------------------------|--------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 8 \[desktop apps only\]<br/>                                                 |
| Minimum supported server<br/> | Windows Server 2012 \[desktop apps only\]<br/>                                       |
| Header<br/>                   | <dl> <dt>Ndattributils.h</dt> </dl> |



## See also

<dl> <dt>

[**UiInfo**](/windows/win32/ndattrib/ns-ndattrib-taguiinfo?branch=master)
</dt> <dt>

[**CoTaskMemFree**](https://msdn.microsoft.com/library/windows/desktop/ms680722)
</dt> </dl>

 

 




