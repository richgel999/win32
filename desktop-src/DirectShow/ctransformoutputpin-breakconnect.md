---
Description: The BreakConnect method releases the pin from a connection.
ms.assetid: bf68aca3-93e5-4f9d-9980-1a5eed1513f5
title: CTransformOutputPin.BreakConnect method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# CTransformOutputPin.BreakConnect method

The `BreakConnect` method releases the pin from a connection.

## Syntax


```C++
HRESULT BreakConnect();
```



## Parameters

This method has no parameters.

## Return value

Returns S\_OK or another **HRESULT** value.

## Remarks

This method overrides the [**CBaseOutputPin::BreakConnect**](cbaseoutputpin-breakconnect.md) method. It calls the filter's [**CTransformFilter::BreakConnect**](ctransformfilter-breakconnect.md) method, which returns S\_OK in the base class. The derived class can override the **CTransformFilter::BreakConnect** method.

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Transfrm.h (include Streams.h)</dt> </dl>                                                                                  |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



 

 



