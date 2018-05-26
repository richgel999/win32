---
Description: The m\_bUsingImageAllocator member variable indicates whether the allocator for the pin connection is a CImageAllocator object. If the value is TRUE, the allocator is a CImageAllocator object (or is derived from that class).
ms.assetid: 8eddcab6-77b9-4c8f-be74-33e91661430d
title: CDrawImagem\_bUsingImageAllocator member
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# CDrawImage::m\_bUsingImageAllocator member

The `m_bUsingImageAllocator` member variable indicates whether the allocator for the pin connection is a **CImageAllocator** object. If the value is **TRUE**, the allocator is a **CImageAllocator** object (or is derived from that class).

## Syntax


```C++
BOOL m_bUsingImageAllocator;
```



## Remarks

When the value is **TRUE**, the **CDrawImage** object can use the GDI **BitBlt** and **StretchBlt** functions to render the image, rather than the slower **SetDIBitsToDevice** and **StretchDIBits** functions.

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Winutil.h (include Streams.h)</dt> </dl>                                                                                   |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[**CDrawImage Class**](cdrawimage.md)
</dt> <dt>

[**CDrawImage::NotifyAllocator**](cdrawimage-notifyallocator.md)
</dt> <dt>

[**CDrawImage::UsingImageAllocator**](cdrawimage-usingimageallocator.md)
</dt> </dl>

 

 



