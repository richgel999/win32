---
Description: Gets statistics from the Digital Living Network Alliance (DLNA) media sink.
ms.assetid: 1fa6ea9f-fd30-4fa2-a0e6-1647273bcc35
title: MF\_MP2DLNA\_STATISTICS attribute
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# MF\_MP2DLNA\_STATISTICS attribute

Gets statistics from the Digital Living Network Alliance (DLNA) media sink.

## Data type

**[**MFMPEG2DLNASINKSTATS**](/windows/win32/mfmp2dlna/ns-mfmp2dlna-_mfmpeg2dlnasinkstats?branch=master)** stored as **BYTE\[\]**

## Get/set

To get this attribute, call [**IMFAttributes::GetBlob**](/windows/win32/mfobjects/nf-mfobjects-imfattributes-getblob?branch=master).

## Remarks

During streaming, the DLNA media sink updates this attribute with statistics about the encoding and multiplexing of the MPEG-2 streams. The application can query this attribute at any time to get the latest values.

Setting this attribute on the DLNA media sink has no effect.

## Requirements



|                                     |                                                                                        |
|-------------------------------------|----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 7 \[desktop apps only\]<br/>                                             |
| Minimum supported server<br/> | Windows Server 2008 R2 \[desktop apps only\]<br/>                                |
| Header<br/>                   | <dl> <dt>Mfmp2dlna.h</dt> </dl> |



## See also

<dl> <dt>

[Alphabetical List of Media Foundation Attributes](alphabetical-list-of-media-foundation-attributes.md)
</dt> </dl>

 

 



