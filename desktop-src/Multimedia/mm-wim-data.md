---
title: MM\_WIM\_DATA message
description: The MM\_WIM\_DATA message is sent to a window when waveform-audio data is present in the input buffer and the buffer is being returned to the application. The message can be sent either when the buffer is full or after the waveInReset function is called.
ms.assetid: 14298153-ea2f-40b7-bca7-196f4e6c1155
keywords:
- MM_WIM_DATA message Windows Multimedia
topic_type:
- apiref
api_name:
- MM_WIM_DATA
api_location:
- Mmsystem.h
api_type:
- HeaderDef
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# MM\_WIM\_DATA message

The **MM\_WIM\_DATA** message is sent to a window when waveform-audio data is present in the input buffer and the buffer is being returned to the application. The message can be sent either when the buffer is full or after the [**waveInReset**](waveinreset.md) function is called.


```C++
MM_WIM_DATA 
wParam = (WPARAM) hInputDev 
lParam = (LONG) lpwvhdr 
```



## Parameters

<dl> <dt>

<span id="hInputDev"></span><span id="hinputdev"></span><span id="HINPUTDEV"></span>*hInputDev*
</dt> <dd>

Handle to the waveform-audio input device that received the data.

</dd> <dt>

<span id="lpwvhdr"></span><span id="LPWVHDR"></span>*lpwvhdr*
</dt> <dd>

Pointer to a [**WAVEHDR**](wavehdr.md) structure that identifies the buffer containing the data.

</dd> </dl>

## Return Value

This message does not return a value.

## Remarks

The returned buffer might not be full. Use the **dwBytesRecorded** member of the [**WAVEHDR**](wavehdr.md) structure specified by *lParam* to determine the number of bytes recorded into the returned buffer.

## Requirements



|                                     |                                                                                                           |
|-------------------------------------|-----------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 2000 Professional \[desktop apps only\]<br/>                                                |
| Minimum supported server<br/> | Windows 2000 Server \[desktop apps only\]<br/>                                                      |
| Header<br/>                   | <dl> <dt>Mmsystem.h (include Windows.h)</dt> </dl> |



## See also

<dl> <dt>

[Waveform Audio](waveform-audio.md)
</dt> <dt>

[Waveform Messages](waveform-messages.md)
</dt> </dl>

 

 




