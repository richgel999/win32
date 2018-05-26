---
Description: The CheckVideoType method checks whether a specified VIDEOINFO format is compatible with the display format.
ms.assetid: a8593c7d-bde0-4c44-b450-10c129dd0007
title: CImageDisplay.CheckVideoType method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# CImageDisplay.CheckVideoType method

The `CheckVideoType` method checks whether a specified [**VIDEOINFO**](/windows/win32/amvideo/ns-amvideo-tagvideoinfo?branch=master) format is compatible with the display format.

## Syntax


```C++
HRESULT CheckVideoType(
   const VIDEOINFO *pInput
);
```



## Parameters

<dl> <dt>

*pInput* 
</dt> <dd>

Pointer to a **VIDEOINFO** structure.

</dd> </dl>

## Return value

Returns S\_OK if the format is compatible, or E\_INVALIDARG otherwise.

## Remarks

This method returns S\_OK if the proposed type can be displayed easily under the current display settings.

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Winutil.h (include Streams.h)</dt> </dl>                                                                                   |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[**CImageDisplay Class**](cimagedisplay.md)
</dt> </dl>

 

 



