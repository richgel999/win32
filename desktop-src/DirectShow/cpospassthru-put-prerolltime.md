---
Description: The put\_PrerollTime method sets the amount of data that will be queued before the start position. This method implements the IMediaPositionput\_PrerollTime method.
ms.assetid: 5c35fb1d-2296-493f-8104-601127d7dd9f
title: CPosPassThru.put\_PrerollTime method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# CPosPassThru.put\_PrerollTime method

The `put_PrerollTime` method sets the amount of data that will be queued before the start position. This method implements the [**IMediaPosition::put\_PrerollTime**](/windows/win32/Control/nf-control-imediaposition-put_prerolltime?branch=master) method.

## Syntax


```C++
HRESULT put_PrerollTime(
   REFTIME llTime
);
```



## Parameters

<dl> <dt>

*llTime* 
</dt> <dd>

Preroll time, in seconds.

</dd> </dl>

## Return value

Returns the **HRESULT** value from the connected pin.

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Ctlutil.h (include Streams.h)</dt> </dl>                                                                                   |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[**CPosPassThru Class**](cpospassthru.md)
</dt> </dl>

 

 



