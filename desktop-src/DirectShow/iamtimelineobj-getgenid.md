---
Description: The GetGenID method retrieves the objects generated identifier. The identifier is a reserved number; applications should not use it.
ms.assetid: b71b9b52-589b-4f80-915f-4805b1b8e295
title: IAMTimelineObjGetGenID method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IAMTimelineObj::GetGenID method

> [!Note]  
> \[Deprecated. This API may be removed from future releases of Windows.\]

 

The `GetGenID` method retrieves the object's generated identifier. The identifier is a reserved number; applications should not use it.

## Syntax


```C++
HRESULT GetGenID(
   long *pVal
);
```



## Parameters

<dl> <dt>

*pVal* 
</dt> <dd>

Receives the generated identifier.

</dd> </dl>

## Return value

If this method succeeds, it returns **S\_OK**. Otherwise, it returns an **HRESULT** error code.

## Remarks

> [!Note]  
> The header file Qedit.h is not compatible with Direct3D headers later than version 7.

 

> [!Note]  
> To obtain Qedit.h, download the [Microsoft Windows SDK Update for Windows Vista and .NET Framework 3.0](http://go.microsoft.com/fwlink/p/?linkid=129787). Qedit.h is not available in the Microsoft Windows SDK for Windows 7 and .NET Framework 3.5 Service Pack 1.

 

## Requirements



|                    |                                                                                         |
|--------------------|-----------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Qedit.h</dt> </dl>      |
| Library<br/> | <dl> <dt>Strmiids.lib</dt> </dl> |



## See also

<dl> <dt>

[**IAMTimelineObj Interface**](iamtimelineobj.md)
</dt> <dt>

[Error and Success Codes](error-and-success-codes.md)
</dt> </dl>

 

 



