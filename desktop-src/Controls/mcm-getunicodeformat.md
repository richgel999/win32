---
title: MCM\_GETUNICODEFORMAT message
description: Retrieves the Unicode character format flag for the control. You can send this message explicitly or use the MonthCal\_GetUnicodeFormat macro.
ms.assetid: 28261e11-0fd0-407e-9f62-446536d62460
keywords:
- MCM_GETUNICODEFORMAT message Windows Controls
topic_type:
- apiref
api_name:
- MCM_GETUNICODEFORMAT
api_location:
- Commctrl.h
api_type:
- HeaderDef
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# MCM\_GETUNICODEFORMAT message

Retrieves the Unicode character format flag for the control. You can send this message explicitly or use the [**MonthCal\_GetUnicodeFormat**](/windows/win32/Commctrl/nf-commctrl-monthcal_getunicodeformat?branch=master) macro.

## Parameters

<dl> <dt>

*wParam* 
</dt> <dd>Must be zero.</dd> <dt>

*lParam* 
</dt> <dd>Must be zero.</dd> </dl>

## Return value

Returns the Unicode format flag for the control. If this value is nonzero, the control is using Unicode characters. If this value is zero, the control is using ANSI characters.

## Remarks

See the remarks for [**CCM\_GETUNICODEFORMAT**](ccm-getunicodeformat.md) for a discussion of this message.

## Requirements



|                                     |                                                                                       |
|-------------------------------------|---------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                        |
| Minimum supported server<br/> | Windows Server 2003 \[desktop apps only\]<br/>                                  |
| Header<br/>                   | <dl> <dt>Commctrl.h</dt> </dl> |



## See also

<dl> <dt>

[**MCM\_SETUNICODEFORMAT**](mcm-setunicodeformat.md)
</dt> </dl>

 

 




