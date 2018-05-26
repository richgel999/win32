---
Description: The RetryDelay property is a value that indicates the time interval, in minutes, that the fax service waits before attempting to retransmit an outbound fax job.
ms.assetid: fc65cc57-5eee-49da-8533-c2592321d43a
title: FaxOutgoingQueue.RetryDelay property
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# FaxOutgoingQueue.RetryDelay property

The **RetryDelay** property is a value that indicates the time interval, in minutes, that the fax service waits before attempting to retransmit an outbound fax job.

This property is read/write.

## Syntax


```VB
Property RetryDelay As String
```



## Property value

A **String** that specifies or receives the time interval, in minutes, that the fax service waits before attempting to retransmit an outbound fax job.

## Remarks

To read or to write to this property, a user must have the [****farQUERY\_CONFIG****](/windows/previous-versions/FaxComex/ne-faxcomex-fax_access_rights_enum?branch=master) access right.

## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows XP \[desktop apps only\]<br/>                                             |
| Minimum supported server<br/> | Windows Server 2003 \[desktop apps only\]<br/>                                    |
| Header<br/>                   | <dl> <dt>FaxComex.h</dt> </dl>   |
| DLL<br/>                      | <dl> <dt>Fxscomex.dll</dt> </dl> |



## See also

<dl> <dt>

[**FaxOutgoingQueue**](-mfax-faxoutgoingqueue.md)
</dt> <dt>

[**IFaxOutgoingQueue**](/windows/previous-versions/FaxComex/nn-faxcomex-ifaxoutgoingqueue?branch=master)
</dt> <dt>

[Setting the Outgoing Queue Properties](-mfax-setting-the-outgoing-queue-properties.md)
</dt> </dl>

 

 



