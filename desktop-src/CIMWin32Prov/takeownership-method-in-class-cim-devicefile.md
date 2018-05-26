---
Description: The TakeOwnerShip method obtains ownership of the logical file specified in the object path.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: ef7d5ce7-99fb-464f-9739-ec9189148f94
ms.prod: windows-server-dev
ms.technology:
- cimwin32
- windows-management-instrumentation
ms.tgt_platform: multiple
title: TakeOwnerShip method of the CIM\_DeviceFile class
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# TakeOwnerShip method of the CIM\_DeviceFile class

The **TakeOwnerShip** method obtains ownership of the logical file specified in the object path. If the logical file is a directory, then this method will act recursively, taking ownership of all of the files and sub-directories that the directory contains. This method is inherited from [**CIM\_LogicalFile**](cim-logicalfile.md).

> \[!Important\]  
> The DMTF (Distributed Management Task Force) CIM (Common Information Model) classes are the parent classes upon which WMI classes are built. WMI currently supports only the [CIM 2.x version schemas](Http://Go.Microsoft.Com/FWLink/p/?LinkID=309367).

 

This topic uses Managed Object Format (MOF) syntax. For more information about using this method, see [Calling a Method](https://msdn.microsoft.com/library/aa384832).

## Syntax


```mof
uint32 TakeOwnerShip();
```



## Parameters

This method has no parameters.

## Return value

Returns a value of 0 (zero) on success, and any other number to indicate an error.

<dl> <dt>

**0**
</dt> <dd>

Success.

</dd> <dt>

**2**
</dt> <dd>

Access denied.

</dd> <dt>

**8**
</dt> <dd>

Unspecified failure.

</dd> <dt>

**9**
</dt> <dd>

Invalid object.

</dd> <dt>

**10**
</dt> <dd>

Object already exists.

</dd> <dt>

**11**
</dt> <dd>

File system not NTFS.

</dd> <dt>

**12**
</dt> <dd>

Platform not Windows.

</dd> <dt>

**13**
</dt> <dd>

Drive not the same.

</dd> <dt>

**14**
</dt> <dd>

Directory not empty.

</dd> <dt>

**15**
</dt> <dd>

Sharing violation.

</dd> <dt>

**16**
</dt> <dd>

Invalid start file.

</dd> <dt>

**17**
</dt> <dd>

Privilege not held.

</dd> <dt>

**21**
</dt> <dd>

Invalid parameter.

</dd> </dl>

## Remarks

This method is currently not implemented by WMI. To use this method, you must implement it in your own provider.

This documentation is derived from the CIM class descriptions published by the DMTF. Microsoft may have made changes to correct minor errors, conform to Microsoft SDK documentation standards, or provide more information.

## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista<br/>                                                                |
| Minimum supported server<br/> | Windows Server 2008<br/>                                                          |
| Namespace<br/>                | Root\\CIMV2<br/>                                                                  |
| MOF<br/>                      | <dl> <dt>CIMWin32.mof</dt> </dl> |
| DLL<br/>                      | <dl> <dt>CIMWin32.dll</dt> </dl> |



## See also

<dl> <dt>

[CIM\_DeviceFile](takeownership-method-in-class-cim-devicefile.md)
</dt> <dt>

[**CIM\_DeviceFile**](cim-devicefile.md)
</dt> </dl>

 

 



