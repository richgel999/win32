---
Description: MPEG-1 Stream Splitter Filter
ms.assetid: abadf37f-2876-496d-90e7-77c3475a0064
title: MPEG-1 Stream Splitter Filter
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# MPEG-1 Stream Splitter Filter

This filter splits an MPEG-1 system stream into its component audio and video streams.



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Filter Interfaces</td>
<td>[<strong>IAMMediaContent</strong>](/windows/win32/Qnetwork/nn-qnetwork-iammediacontent?branch=master), [<strong>IAMStreamSelect</strong>](/windows/win32/Strmif/nn-strmif-iamstreamselect?branch=master), [<strong>IBaseFilter</strong>](/windows/win32/Strmif/nn-strmif-ibasefilter?branch=master)</td>
</tr>
<tr class="even">
<td>Input Pin Media Types</td>
<td>Major type: MEDIATYPE_Stream<br/> Subtypes:<br/>
<ul>
<li>MEDIASUBTYPE_MPEG1System</li>
<li>MEDIASUBTYPE_MPEG1VideoCD</li>
<li>MEDIASUBTYPE_Audio</li>
<li>MEDIASUBTYPE_Video</li>
</ul>
See [<strong>MPEG-1 Media Types</strong>](mpeg-1-media-types.md)<br/></td>
</tr>
<tr class="odd">
<td>Input Pin Interfaces</td>
<td>[<strong>IMemInputPin</strong>](/windows/win32/Strmif/nn-strmif-imeminputpin?branch=master), [<strong>IPin</strong>](/windows/win32/Strmif/nn-strmif-ipin?branch=master), [<strong>IQualityControl</strong>](/windows/win32/Strmif/nn-strmif-iqualitycontrol?branch=master)</td>
</tr>
<tr class="even">
<td>Output Pin Media Types</td>
<td>Major type: MEDIATYPE_Audio or MEDIATYPE_Video<br/> Subtype: MEDIASUBTYPE_MPEG1Payload or MEDIASUBTYPE_MPEG1Packet<br/> See [<strong>MPEG-1 Media Types</strong>](mpeg-1-media-types.md)<br/></td>
</tr>
<tr class="odd">
<td>Output Pin Interfaces</td>
<td>[<strong>IPin</strong>](/windows/win32/Strmif/nn-strmif-ipin?branch=master), [<strong>IMediaSeeking</strong>](/windows/win32/Strmif/nn-strmif-imediaseeking?branch=master)</td>
</tr>
<tr class="even">
<td>Filter CLSID</td>
<td>CLSID_MPEG1Splitter</td>
</tr>
<tr class="odd">
<td>Property Page CLSID</td>
<td>No property page</td>
</tr>
<tr class="even">
<td>Executable</td>
<td>quartz.dll</td>
</tr>
<tr class="odd">
<td>[Merit](merit.md)</td>
<td>MERIT_NORMAL</td>
</tr>
<tr class="even">
<td>[Filter Category](filter-categories.md)</td>
<td>CLSID_LegacyAmFilterCategory</td>
</tr>
</tbody>
</table>



 

## Remarks

This file supports pull mode via [**IAsyncReader**](/windows/win32/Strmif/nn-strmif-iasyncreader?branch=master) only; it does not support push mode.

Because MPEG-1 content is not indexed, seeking can be very approximate. It is usually good for a fixed bitrate MPEG-1 system stream (which is usually hardware generated for video CD).

The filter supports the [**IAMMediaContent**](/windows/win32/Qnetwork/nn-qnetwork-iammediacontent?branch=master) interface for retrieving ID3 metadata.

Not all MPEG samples have time stamps. The lack of a time stamp on an MPEG sample is not an error. For filter developers, this means that you should not return an error code from your input pin's **Receive** method if [**IMediaSample::GetTime**](/windows/win32/Strmif/nf-strmif-imediasample-gettime?branch=master) fails. If **Receive** returns any value other than S\_OK, it will cause the splitter to stop sending samples.

If the file contains a video stream, the MPEG-1 Stream Splitter supports seeking by frame number. To enable frame-based seeking, call [**IMediaSeeking::SetTimeFormat**](/windows/win32/Strmif/nf-strmif-imediaseeking-settimeformat?branch=master) on the [Filter Graph Manager](filter-graph-manager.md) with the value **TIME\_FORMAT\_FRAME**.

## Related topics

<dl> <dt>

[DirectShow Filters](directshow-filters.md)
</dt> </dl>

 

 



