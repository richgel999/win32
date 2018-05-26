---
title: Miscellaneous TSF Text Service Constants
description: The following values are used with text services.
ms.assetid: 38110314-1638-4963-92b6-4ba2f81fb7c2
topic_type:
- apiref
api_name:
- TF_MENUREADY
- TF_PROPUI_STATUS_SAVETOFILE
api_location:
- Ctffunc.h
api_type:
- HeaderDef
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Miscellaneous TSF Text Service Constants

The following values are used with text services.



| Constant/value                                                                                                                                                                                                                                                            | Description                                                                                                                                                                                                                                                                              |
|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span id="TF_MENUREADY"></span><span id="tf_menuready"></span><dl> <dt>**TF\_MENUREADY**</dt> <dt>0x00000001</dt> </dl>                                                | Not currently used.<br/>                                                                                                                                                                                                                                                           |
| <span id="TF_PROPUI_STATUS_SAVETOFILE"></span><span id="tf_propui_status_savetofile"></span><dl> <dt>**TF\_PROPUI\_STATUS\_SAVETOFILE**</dt> <dt>0x00000001</dt> </dl> | The property can be serialized. If this value is not present, the property cannot be serialized. This value is used with [ITfFnPropertyUIStatus::GetStatus](/windows/win32/Ctffunc/nf-ctffunc-itffnpropertyuistatus-getstatus?branch=master) and [ITfFnPropertyUIStatus::SetStatus](/windows/win32/Ctffunc/nf-ctffunc-itffnpropertyuistatus-setstatus?branch=master).<br/> |



## Requirements



|                                     |                                                                                        |
|-------------------------------------|----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 2000 Professional \[desktop apps only\]<br/>                             |
| Minimum supported server<br/> | Windows 2000 Server \[desktop apps only\]<br/>                                   |
| Redistributable<br/>          | TSF 1.0 on Windows 2000 Professional<br/>                                        |
| Header<br/>                   | <dl> <dt>Ctffunc.h</dt> </dl>   |
| IDL<br/>                      | <dl> <dt>Ctffunc.idl</dt> </dl> |



## See also

<dl> <dt>

[ITfFnPropertyUIStatus::GetStatus](/windows/win32/Ctffunc/nf-ctffunc-itffnpropertyuistatus-getstatus?branch=master)
</dt> <dt>

[ITfFnPropertyUIStatus::SetStatus](/windows/win32/Ctffunc/nf-ctffunc-itffnpropertyuistatus-setstatus?branch=master)
</dt> </dl>

 

 




