---
title: CDN\_FILEOK notification code
description: Sent by an Explorer-style Open or Save As dialog box when the user specifies a file name and clicks the OK button.
ms.assetid: 7f3de96f-68d8-4f40-b74f-304835f9def2
keywords:
- CDN_FILEOK notification code Dialog Boxes
topic_type:
- apiref
api_name:
- CDN_FILEOK
api_location:
- Commdlg.h
api_type:
- HeaderDef
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# CDN\_FILEOK notification code

Sent by an Explorer-style **Open** or **Save As** dialog box when the user specifies a file name and clicks the **OK** button.

Your [*OFNHookProc*](ofnhookproc.md) hook procedure receives this message in the form of a [**WM\_NOTIFY**](_win32_WM_NOTIFY) message.


```C++
#define CDN_FIRST               (0U-601U)
#define CDN_FILEOK              (CDN_FIRST - 0x0005)
```



## Parameters

<dl> <dt>

*wParam* 
</dt> <dd>

This parameter is not used.

</dd> <dt>

*lParam* 
</dt> <dd>

A pointer to an [**OFNOTIFY**](/windows/win32/Commdlg/ns-commdlg-_ofnotifya?branch=master) structure.

The [**OFNOTIFY**](/windows/win32/Commdlg/ns-commdlg-_ofnotifya?branch=master) structure contains an [**NMHDR**](_win32_nmhdr_str) structure whose **code** member indicates the **CDN\_FILEOK** notification message.

The [**OFNOTIFY**](/windows/win32/Commdlg/ns-commdlg-_ofnotifya?branch=master) structure also contains a pointer to an [**OPENFILENAME**](/windows/win32/Commdlg/ns-commdlg-tagofna?branch=master) structure whose **lpstrFile** member specifies the address of the selected file name.

</dd> </dl>

## Return value

If the hook procedure returns zero, the dialog box accepts the specified file name and closes.

To reject the specified file name and force the dialog box to remain open, return a nonzero value from the hook procedure and call the [**SetWindowLong**](https://msdn.microsoft.com/library/windows/desktop/ms633591) function to set a nonzero **DWL\_MSGRESULT** value.

## Remarks

The system sends this notification only if the dialog box was created using the **OFN\_EXPLORER** value.

## Requirements



|                                     |                                                                                                          |
|-------------------------------------|----------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 2000 Professional \[desktop apps only\]<br/>                                               |
| Minimum supported server<br/> | Windows 2000 Server \[desktop apps only\]<br/>                                                     |
| Header<br/>                   | <dl> <dt>Commdlg.h (include Windows.h)</dt> </dl> |



## See also

<dl> <dt>

**Reference**
</dt> <dt>

[**GetOpenFileName**](/windows/win32/Commdlg/nf-commdlg-getopenfilenamea?branch=master)
</dt> <dt>

[**GetSaveFileName**](/windows/win32/Commdlg/nf-commdlg-getsavefilenamea?branch=master)
</dt> <dt>

[*OFNHookProc*](ofnhookproc.md)
</dt> <dt>

[**OFNOTIFY**](/windows/win32/Commdlg/ns-commdlg-_ofnotifya?branch=master)
</dt> <dt>

[**OPENFILENAME**](/windows/win32/Commdlg/ns-commdlg-tagofna?branch=master)
</dt> <dt>

[**SetWindowLong**](https://msdn.microsoft.com/library/windows/desktop/ms633591)
</dt> <dt>

**Conceptual**
</dt> <dt>

[Common Dialog Box Library](common-dialog-box-library.md)
</dt> <dt>

**Other Resources**
</dt> <dt>

[**WM\_NOTIFY**](_win32_WM_NOTIFY)
</dt> </dl>

 

 




