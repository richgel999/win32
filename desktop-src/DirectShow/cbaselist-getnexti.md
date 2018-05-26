---
Description: The GetNextI method retrieves the item at the specified position, and advances the position.
ms.assetid: 3ec217ec-b0f9-4ff4-bdb7-ac204df99010
title: CBaseList.GetNextI method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# CBaseList.GetNextI method

The `GetNextI` method retrieves the item at the specified position, and advances the position.

## Syntax


```C++
void* GetNextI(
  [ref] POSITION &amp;rp
);
```



## Parameters

<dl> <dt>

*rp* \[ref\]
</dt> <dd>

Reference to a POSITION value.

</dd> </dl>

## Return value

Returns a pointer to the item. If *rp* is **NULL**, the method returns **NULL**.

## Remarks

This method advances the position indicator to the next position. If the position indicator moves past the end of the list, the method sets it to **NULL**.

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Wxlist.h (include Streams.h)</dt> </dl>                                                                                    |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[**CBaseList Class**](cbaselist.md)
</dt> </dl>

 

 



