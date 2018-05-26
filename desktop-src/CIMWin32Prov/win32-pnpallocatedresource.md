---
Description: The Win32\_PnPAllocatedResource association WMI class represents an association between logical devices and system resources.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: e3cef457-cf88-4df5-8db8-b0495f636904
ms.prod: windows-server-dev
ms.technology:
- cimwin32
- windows-management-instrumentation
ms.tgt_platform: multiple
title: Win32\_PnPAllocatedResource class
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# Win32\_PnPAllocatedResource class

The **Win32\_PnPAllocatedResource** association [WMI class](wmi.retrieving_a_class) represents an association between logical devices and system resources. This class is used to discover the resources that are in-use by a specific device, such as an Interrupt ReQuest (IRQ) or a Direct Memory Access (DMA) channel.

The following syntax is simplified from Managed Object Format (MOF) code and includes all of the inherited properties. Properties are listed in alphabetic order, not MOF order.

## Syntax

``` syntax
[Dynamic, Provider("CIMWin32"), UUID("970C0998-41FE-4275-B7D9-7DABAD3FBC4D"), AMENDMENT]
class Win32_PnPAllocatedResource : CIM_AllocatedResource
{
  CIM_SystemResource REF Antecedent;
  Win32_PnPEntity    REF Dependent;
};
```

## Members

The **Win32\_PnPAllocatedResource** class has these types of members:

-   [Properties](#properties)

### Properties

The **Win32\_PnPAllocatedResource** class has these properties.

<dl> <dt>

**Antecedent**
</dt> <dd> <dl> <dt>

Data type: **CIM\_SystemResource**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: [**Key**](wmi.key_qualifier), [**Override**](wmi.standard_qualifiers) ("Antecedent"), [**MappingStrings**](wmi.standard_qualifiers) ("CIM\|CIM\_SystemResource")
</dt> </dl>

Reference to the [**CIM\_SystemResource**](cim-systemresource.md) instance that represents the properties of a system resource available to the logical device. This property is inherited from [**CIM\_Dependency**](cim-dependency.md).

</dd> <dt>

**Dependent**
</dt> <dd> <dl> <dt>

Data type: **Win32\_PnPEntity**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: [**Key**](wmi.key_qualifier), [**Override**](wmi.standard_qualifiers) ("Dependent"), [**MappingStrings**](wmi.standard_qualifiers) ("CIM\|CIM\_LogicalDevice")
</dt> </dl>

Reference to the [**Win32\_PnPEntity**](win32-pnpentity.md) instance that represents the properties of the logical device using the system resources assigned to it. This property is inherited from [**CIM\_Dependency**](cim-dependency.md).

</dd> </dl>

## Remarks

The **Win32\_PnPAllocatedResource** class is derived from [**CIM\_AllocatedResource**](cim-allocatedresource.md).

## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista<br/>                                                                |
| Minimum supported server<br/> | Windows Server 2008<br/>                                                          |
| Namespace<br/>                | Root\\CIMV2<br/>                                                                  |
| MOF<br/>                      | <dl> <dt>CIMWin32.mof</dt> </dl> |
| DLL<br/>                      | <dl> <dt>CIMWin32.dll</dt> </dl> |



## See also

<dl> <dt>

[**CIM\_AllocatedResource**](cim-allocatedresource.md)
</dt> <dt>

[Computer System Hardware Classes](computer-system-hardware-classes.md)
</dt> </dl>

 

 



