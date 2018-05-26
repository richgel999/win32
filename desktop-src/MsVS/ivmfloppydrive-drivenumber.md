---
title: IVMFloppyDrive DriveNumber property
description: The DriveNumber property contains the zero-based index of the controller to which this floppy drive is attached.
ms.assetid: 48a1eb14-fc6c-4d28-987f-bac7c28c5e2a
keywords:
- DriveNumber property Virtual Server
- DriveNumber property Virtual Server , IVMFloppyDrive interface
- IVMFloppyDrive interface Virtual Server , DriveNumber property
- DriveNumber property Virtual Server , VMFloppyDrive interface
- VMFloppyDrive interface Virtual Server , DriveNumber property
topic_type:
- apiref
api_name:
- IVMFloppyDrive.DriveNumber
- IVMFloppyDrive.get_DriveNumber
- VMFloppyDrive.DriveNumber
api_location:
- VsComInterfaces.h
api_type:
- COM
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IVMFloppyDrive::DriveNumber property

The **DriveNumber** property contains the zero-based index of the controller to which this floppy drive is attached.

This property is read-only.

## Syntax


```C++
HRESULT get_DriveNumber(
  [out] long *driveNumber
);
```

<span codelanguage="VisualBasic"></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th>VB</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><pre><code>VMFloppyDrive.DriveNumber( _
  ByRef driveNumber _
)</code></pre></td>
</tr>
</tbody>
</table>



## Property value

The zero-based index of the controller to which this floppy drive is attached.

This property value is read-only.

## Error codes



| Name                                                                                          | Meaning                                  |
|-----------------------------------------------------------------------------------------------|------------------------------------------|
| <dl> <dt>S\_OK</dt> </dl>              | The operation was successful.<br/> |
| <dl> <dt>E\_POINTER</dt> </dl>         | The parameter is **NULL**.<br/>    |
| <dl> <dt>DISP\_E\_EXCEPTION</dt> </dl> | An unexpected error occurred.<br/> |



## Requirements



|                     |                                                                                                   |
|---------------------|---------------------------------------------------------------------------------------------------|
| Product<br/>  | Microsoft Virtual Server 2005 onWindows Server 2003<br/>                                    |
| Download<br/> | Microsoft Virtual Server 2005 R2 SP1 Update onWindows Server 2008orWindows Server 2003<br/> |
| Header<br/>   | <dl> <dt>VsComInterfaces.h</dt> </dl>      |



## See also

<dl> <dt>

[**IVMFloppyDrive**](ivmfloppydrive.md)
</dt> </dl>

 

 




