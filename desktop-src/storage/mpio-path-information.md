---
title: MPIO\_PATH\_INFORMATION structure
description: The MPIO\_PATH\_INFORMATION structure represents a top-level view of all the paths that are under MPIO control. To query the path information, the request must be sent to the MPIO control object by using its WMI instance name.
ms.assetid: 12383ae0-69c8-4546-9560-08aa4a50de8e
keywords:
- MPIO_PATH_INFORMATION structure Storage Devices
- PMPIO_PATH_INFORMATION structure pointer Storage Devices
topic_type:
- apiref
api_name:
- MPIO_PATH_INFORMATION
api_location:
- mpiowmi.h
api_type:
- HeaderDef
ms.date: 05/31/2018
ms.topic: structure
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# MPIO\_PATH\_INFORMATION structure

The MPIO\_PATH\_INFORMATION structure represents a top-level view of all the paths that are under MPIO control. To query the path information, the request must be sent to the MPIO control object by using its WMI instance name.

## Syntax


```C++
typedef struct _MPIO_PATH_INFORMATION {
  ULONG                    NumberPaths;
  ULONG                    Pad;
  MPIO_ADAPTER_INFORMATION PathList[1];
} MPIO_PATH_INFORMATION, *PMPIO_PATH_INFORMATION;
```



## Members

<dl> <dt>

**NumberPaths**
</dt> <dd>

An unsigned 32-bitfield that represents the total number of paths that MPIO is aware of.

</dd> <dt>

**Pad**
</dt> <dd>

Should be zero.

</dd> <dt>

**PathList**
</dt> <dd>

An array that returns information about each of the paths. The number of elements in the array is given by *NumberPaths* and each element of the array represents an instance of an MPIO\_ADAPTER\_INFORMATION structure.

</dd> </dl>

## Requirements



|                   |                                                                                                          |
|-------------------|----------------------------------------------------------------------------------------------------------|
| Header<br/> | <dl> <dt>Mpiowmi.h (include Mpiowmi.h)</dt> </dl> |



 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bstorage\storage%5D:%20MPIO_PATH_INFORMATION%20structure%20%20RELEASE:%20%283/29/2018%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")




