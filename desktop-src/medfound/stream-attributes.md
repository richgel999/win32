---
Description: Stream Attributes
ms.assetid: d57a57e9-87e4-4f7f-943a-63fd2ad1d1a6
title: Stream Attributes
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Stream Attributes

The following attributes apply to media streams. To get the attributes from a media sample, use the [**IMFMediaSourceEx::GetStreamAttributes**](/windows/win32/mfidl/nf-mfidl-imfmediasourceex-getstreamattributes?branch=master) method.



| Attribute                                                                                   | Description                                   |
|---------------------------------------------------------------------------------------------|-----------------------------------------------|
| [MFStreamExtension\_CameraExtrinsics](mfstreamextension-cameraextrinsics.md)               | The camera extrinsics for the stream.         |
| [MFStreamExtension\_PinholeCameraIntrinsics](mfstreamextension-pinholecameraintrinsics.md) | The pinhole camera intrinsics for the stream. |



 

Not every media stream contains every attribute listed here. In some cases, an attribute applies only to certain kinds of data.

## Related topics

<dl> <dt>

[**IMFSample**](/windows/win32/mfobjects/nn-mfobjects-imfsample?branch=master)
</dt> <dt>

[Media Foundation Attributes](media-foundation-attributes.md)
</dt> <dt>

[Media Samples](media-samples.md)
</dt> </dl>

 

 


