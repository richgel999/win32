---
Description: Not supported. Call the IAMTimelineAddGroup method instead.
ms.assetid: dd671fa5-ed5a-46e2-b4bd-a37f0e7458ca
title: IAMTimelineGroupSetTimeline method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IAMTimelineGroup::SetTimeline method

> [!Note]  
> \[Deprecated. This API may be removed from future releases of Windows.\]

 

Not supported. Call the [**IAMTimeline::AddGroup**](iamtimeline-addgroup.md) method instead.

## Syntax


```C++
HRESULT SetTimeline(
   IAMTimeline *pTimeline
);
```



## Parameters

<dl> <dt>

*pTimeline* 
</dt> <dd>

Reserved.

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

[**IAMTimelineGroup Interface**](iamtimelinegroup.md)
</dt> </dl>

 

 



