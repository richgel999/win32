---
title: ScsiReadCapacity\_OUT structure
description: The ScsiReadCapacity\_OUT structure is used to report the output data of the ScsiReadCapacity WMI method to the WMI client.
ms.assetid: bf295061-42d6-4f2e-a39e-9bac440b0d93
keywords:
- ScsiReadCapacity_OUT structure Storage Devices
- PScsiReadCapacity_OUT structure pointer Storage Devices
topic_type:
- apiref
api_name:
- ScsiReadCapacity_OUT
api_location:
- Hbapiwmi.h
api_type:
- HeaderDef
ms.date: 05/31/2018
ms.topic: structure
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# ScsiReadCapacity\_OUT structure

The ScsiReadCapacity\_OUT structure is used to report the output data of the [**ScsiReadCapacity**](https://msdn.microsoft.com/library/windows/hardware/ff564880) WMI method to the WMI client.

## Syntax


```C++
typedef struct _ScsiReadCapacity_OUT {
  ULONG HBAStatus;
  ULONG ResponseBufferSize;
  ULONG SenseBufferSize;
  UCHAR ScsiStatus;
  UCHAR ResponseBuffer[1];
  UCHAR SenseBuffer[1];
} ScsiReadCapacity_OUT, *PScsiReadCapacity_OUT;
```



## Members

<dl> <dt>

**HBAStatus**
</dt> <dd>

Contains a value associated with the WMI class qualifier [HBA\_STATUS](https://msdn.microsoft.com/library/windows/hardware/ff557233) that indicates the result of an HBA query operation.

</dd> <dt>

**ResponseBufferSize**
</dt> <dd>

Indicates the size in bytes of the buffer that will hold the results of the read capacity command.

</dd> <dt>

**SenseBufferSize**
</dt> <dd>

Indicates the size in bytes of the buffer that will hold the SCSI sense data that results from the read capacity command.

</dd> <dt>

**ScsiStatus**
</dt> <dd>

Contains the status of the SCSI read capacity command.

</dd> <dt>

**ResponseBuffer**
</dt> <dd>

Contains the results of the SCSI read capacity command.

</dd> <dt>

**SenseBuffer**
</dt> <dd>

Contains the SCSI sense data that results from the SCSI read capacity command.

</dd> </dl>

## Remarks

The WMI tool suite generates a declaration of the ScsiReadCapacity\_OUT structure in *Hbapiwmi.h* when it compiles the [MSFC\_HBAAdapterMethods WMI Class](https://msdn.microsoft.com/library/windows/hardware/ff562506).

## Requirements



|                   |                                                                                                            |
|-------------------|------------------------------------------------------------------------------------------------------------|
| Header<br/> | <dl> <dt>Hbapiwmi.h (include Hbapiwmi.h)</dt> </dl> |



## See also

<dl> <dt>

[HBA\_STATUS](https://msdn.microsoft.com/library/windows/hardware/ff557233)
</dt> <dt>

[**ScsiReadCapacity**](https://msdn.microsoft.com/library/windows/hardware/ff564880)
</dt> </dl>

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bstorage\storage%5D:%20ScsiReadCapacity_OUT%20structure%20%20RELEASE:%20%283/29/2018%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")





