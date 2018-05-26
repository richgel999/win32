---
Description: Specifies the field dominance for an interlaced video frame.
ms.assetid: 680c42e4-2808-46ed-98a8-c77b14a55def
title: MFSampleExtension\_BottomFieldFirst attribute
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# MFSampleExtension\_BottomFieldFirst attribute

Specifies the field dominance for an interlaced video frame. This attribute applies to media samples.

## Data type

**BOOL** stored as **UINT32**

## Get/set

To get this attribute, call [**IMFAttributes::GetUINT32**](/windows/win32/mfobjects/nf-mfobjects-imfattributes-getuint32?branch=master).

To set this attribute, call [**IMFAttributes::SetUINT32**](/windows/win32/mfobjects/nf-mfobjects-imfattributes-setuint32?branch=master).

## Applies to

[**IMFSample**](/windows/win32/mfobjects/nn-mfobjects-imfsample?branch=master)

## Remarks

If the video frame is interlaced and the sample contains two interleaved fields, this attribute indicates which field is displayed first. If **TRUE**, the bottom field is first in time. If **FALSE**, the top field is first.

If the frame is interlaced and the sample contains a single field, this attribute indicates which field the sample contains. If **TRUE**, the sample contains the bottom field. If **FALSE**, the sample contains the top field.

If the frame is progressive, this attribute describes how the fields should be ordered when the output is interlaced. If **TRUE**, the bottom field should be output first. If **FALSE**, the top field should be output first.

If this attribute not set, the media type describes the field dominance.

The GUID constant for this attribute is exported from mfuuid.lib.

## Requirements



|                                     |                                                                                    |
|-------------------------------------|------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps \| UWP apps\]<br/>                              |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps \| UWP apps\]<br/>                        |
| Header<br/>                   | <dl> <dt>Mfapi.h</dt> </dl> |



## See also

<dl> <dt>

[Alphabetical List of Media Foundation Attributes](alphabetical-list-of-media-foundation-attributes.md)
</dt> <dt>

[Sample Attributes](sample-attributes.md)
</dt> <dt>

[Media Samples](media-samples.md)
</dt> <dt>

[Video Interlacing](video-interlacing.md)
</dt> </dl>

 

 



