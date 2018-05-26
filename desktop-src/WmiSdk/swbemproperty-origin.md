---
Description: The Origin property of the SWbemProperty object retrieves the name of the WMI class in which this property was introduced. For classes with deep inheritance hierarchies, it is often desirable to know which properties were declared in which classes.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: 25bc0303-43b8-42da-a194-82213c1009d9
ms.prod: windows-server-dev
ms.technology: windows-management-instrumentation
ms.tgt_platform: multiple
title: SWbemProperty.Origin property
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# SWbemProperty.Origin property

The **Origin** property of the [**SWbemProperty**](swbemproperty.md) object retrieves the name of the WMI class in which this property was introduced. For classes with deep inheritance hierarchies, it is often desirable to know which properties were declared in which classes.

If the property is local (see [**SWbemQualifier.IsLocal**](swbemqualifier-islocal.md)), this value is the same as the owning class. This property is read-only.

For an explanation of this syntax, see [Document Conventions for the Scripting API](document-conventions-for-the-scripting-api.md).

This property is read-only.

## Syntax


```VB
SWbemProperty.Origin As String
```



## Property value

## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista<br/>                                                                |
| Minimum supported server<br/> | Windows Server 2008<br/>                                                          |
| Header<br/>                   | <dl> <dt>Wbemdisp.h</dt> </dl>   |
| Type library<br/>             | <dl> <dt>Wbemdisp.tlb</dt> </dl> |
| DLL<br/>                      | <dl> <dt>Wbemdisp.dll</dt> </dl> |
| CLSID<br/>                    | CLSID\_SWbemProperty<br/>                                                         |
| IID<br/>                      | IID\_ISWbemProperty<br/>                                                          |



 

 



