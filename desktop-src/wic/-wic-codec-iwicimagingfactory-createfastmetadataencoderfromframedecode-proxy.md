---
Description: Proxy function for the CreateFastMetadataEncoderFromFrameDecode method.
ms.assetid: 0edc3387-47e9-401c-9153-76c8c32b52de
title: IWICImagingFactory\_CreateFastMetadataEncoderFromFrameDecode\_Proxy function
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IWICImagingFactory\_CreateFastMetadataEncoderFromFrameDecode\_Proxy function

Proxy function for the [**CreateFastMetadataEncoderFromFrameDecode**](/windows/win32/Wincodec/nf-wincodec-iwicimagingfactory-createfastmetadataencoderfromframedecode?branch=master) method.

## Syntax


```C++
HRESULT IWICImagingFactory_CreateFastMetadataEncoderFromFrameDecode_Proxy(
  _In_  IWICImagingFactory      *pFactory,
  _In_  IWICBitmapFrameDecode   *pIFrameDecoder,
  _Out_ IWICFastMetadataEncoder **ppIFME
);
```



## Parameters

<dl> <dt>

*pFactory* \[in\]
</dt> <dd>

Type: **[**IWICImagingFactory**](/windows/win32/Wincodec/nn-wincodec-iwicimagingfactory?branch=master)\***

</dd> <dt>

*pIFrameDecoder* \[in\]
</dt> <dd>

Type: **[**IWICBitmapFrameDecode**](/windows/win32/Wincodec/nn-wincodec-iwicbitmapframedecode?branch=master)\***

The [**IWICBitmapFrameDecode**](/windows/win32/Wincodec/nn-wincodec-iwicbitmapframedecode?branch=master) to create the [**IWICFastMetadataEncoder**](/windows/win32/Wincodec/nn-wincodec-iwicfastmetadataencoder?branch=master) from.

</dd> <dt>

*ppIFME* \[out\]
</dt> <dd>

Type: **[**IWICFastMetadataEncoder**](/windows/win32/Wincodec/nn-wincodec-iwicfastmetadataencoder?branch=master)\*\***

A pointer that receives a pointer to a new [**IWICFastMetadataEncoder**](/windows/win32/Wincodec/nn-wincodec-iwicfastmetadataencoder?branch=master).

</dd> </dl>

## Return value

Type: **HRESULT**

If this function succeeds, it returns **S\_OK**. Otherwise, it returns an **HRESULT** error code.

## Remarks

## Requirements



|                                     |                                                                                                                                                                  |
|-------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows XP with SP2, Windows Vista \[desktop apps only\]<br/>                                                                                              |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/>                                                                                                             |
| DLL<br/>                      | <dl> <dt>Windowscodecs.dll; </dt> <dt>Wincodec.lib</dt> </dl> |



 

 



