---
Description: Serves as a parent class for classes that control the generation of events, such as timer events.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: 381b06e7-2857-4932-9f52-f1d62efa8b79
ms.prod: windows-server-dev
ms.technology: windows-management-instrumentation
ms.tgt_platform: multiple
title: '\_\_EventGenerator class'
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# \_\_EventGenerator class

The **\_\_EventGenerator** system class is an abstract base class that serves as a parent class for classes that control the generation of events, such as [timer events](receiving-a-timed-or-repeating-event.md).

The following syntax is simplified from Managed Object Format (MOF) code and includes all inherited properties. Properties are listed in alphabetic order, not MOF order.

## Syntax

``` syntax
[abstract]
class __EventGenerator : __IndicationRelated
{
};
```

## Members

The **\_\_EventGenerator** class does not define any members.

## Remarks

The **\_\_EventGenerator** class is derived from [**\_\_IndicationRelated**](--indicationrelated.md), which has no properties.

## Requirements



|                                     |                                |
|-------------------------------------|--------------------------------|
| Minimum supported client<br/> | Windows Vista<br/>       |
| Minimum supported server<br/> | Windows Server 2008<br/> |
| Namespace<br/>                | All WMI namespaces<br/>  |



## See also

<dl> <dt>

[**\_\_IndicationRelated**](https://msdn.microsoft.com/library/aa394648)
</dt> <dt>

[WMI System Classes](wmi-system-classes.md)
</dt> </dl>

 

 



