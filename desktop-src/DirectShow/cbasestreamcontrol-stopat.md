---
Description: The StopAt method informs the pin when to stop delivering data. This method implements the IAMStreamControlStopAt method.
ms.assetid: cc9f0fdc-253b-4feb-95ce-56ebc575a49b
title: CBaseStreamControl.StopAt method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# CBaseStreamControl.StopAt method

The `StopAt` method informs the pin when to stop delivering data. This method implements the [**IAMStreamControl::StopAt**](/windows/win32/Strmif/nf-strmif-iamstreamcontrol-stopat?branch=master) method.

## Syntax


```C++
HRESULT StopAt(
   const REFERENCE_TIME *ptStop = NULL,
         BOOL           bSendExtra = FALSE,
         DWORD          dwCookie = 0
);
```



## Parameters

<dl> <dt>

*ptStop* 
</dt> <dd>

Pointer to a [**REFERENCE\_TIME**](reference-time.md) value that specifies when the pin should stop delivering data.

</dd> <dt>

*bSendExtra* 
</dt> <dd>

Specifies a Boolean value that indicates whether to send an extra sample after the scheduled stop time. If **TRUE**, the pin sends one extra sample.

</dd> <dt>

*dwCookie* 
</dt> <dd>

Specifies a value to send along with the start notification.

</dd> </dl>

## Return value

Returns S\_OK.

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Strmctl.h (include Streams.h)</dt> </dl>                                                                                   |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[**CBaseStreamControl Class**](cbasestreamcontrol.md)
</dt> </dl>

 

 



