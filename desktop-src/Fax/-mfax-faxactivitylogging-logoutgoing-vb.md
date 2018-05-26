---
Description: The LogOutgoing property is a Boolean value that indicates whether the fax service logs entries for outgoing faxes in the activity log database.
ms.assetid: 6cafd6aa-f5f6-4f15-adb6-2e417474fe65
title: FaxActivityLogging.LogOutgoing property
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# FaxActivityLogging.LogOutgoing property

The **LogOutgoing** property is a Boolean value that indicates whether the fax service logs entries for outgoing faxes in the activity log database.

This property is read/write.

## Syntax


```VB
Property LogOutgoing As Boolean
```



## Property value

A **Boolean** that specifies or receives a value indicating whether the fax service logs entries for outgoing faxes in the activity log database.

## Remarks

If this property is equal to **True**, the fax service logs entries for outgoing fax jobs in the activity log database. If this property is equal to **False**, the fax service does not log entries.

To read or write to this property, a user must have the [****farQUERY\_CONFIG****](/windows/previous-versions/FaxComex/ne-faxcomex-fax_access_rights_enum?branch=master) access right.

## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows XP \[desktop apps only\]<br/>                                             |
| Minimum supported server<br/> | Windows Server 2003 \[desktop apps only\]<br/>                                    |
| Header<br/>                   | <dl> <dt>FaxComex.h</dt> </dl>   |
| DLL<br/>                      | <dl> <dt>Fxscomex.dll</dt> </dl> |



## See also

<dl> <dt>

[Visual Basic Example](-mfax-setting-logging-options.md)
</dt> <dt>

[**FaxActivityLogging**](-mfax-faxactivitylogging.md)
</dt> <dt>

[**IFaxActivityLogging**](/windows/previous-versions/FaxComex/nn-faxcomex-ifaxactivitylogging?branch=master)
</dt> </dl>

 

 



