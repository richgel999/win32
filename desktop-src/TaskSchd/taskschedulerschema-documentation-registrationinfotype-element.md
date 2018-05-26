---
title: Documentation (registrationInfoType) Element
description: Specifies any additional documentation for the task.
ms.assetid: 5f0d2df3-4eef-430b-85a9-602bb29b85c7
keywords:
- Documentation element Task Scheduler
topic_type:
- apiref
api_name:
- Documentation
api_type:
- Schema
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Documentation (registrationInfoType) Element

Specifies any additional documentation for the task.

``` syntax
<xs:element name="Documentation"
    type="string"
    minOccurs="0"
 />
```

The **Documentation** element is defined by the [**registrationInfoType**](taskschedulerschema-registrationinfotype-complextype.md) complex type.

## Parent element



| Element                                                                           | Derived from                                                                         | Description                                                                                                                         |
|-----------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| [**RegistrationInfo**](taskschedulerschema-registrationinfo-tasktype-element.md) | [**registrationInfoType**](taskschedulerschema-registrationinfotype-complextype.md) | Specifies administrative information about the task, such as the author of the task and the date the task is registered.<br/> |



## Remarks

For scripting applications, additional task documentation is specified using the using the [**RegistrationInfo.Documentation**](registrationinfo-documentation.md) property.

For C++ applications, additional task documentation is specified using the using the [**IRegistrationInfo::Documentation**](/windows/win32/taskschd/nf-taskschd-iregistrationinfo-get_documentation?branch=master) property.

## Requirements



|                                     |                                                      |
|-------------------------------------|------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>       |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/> |



## See also

<dl> <dt>

[Task Scheduler Schema Elements](task-scheduler-schema-elements.md)
</dt> </dl>

 

 




