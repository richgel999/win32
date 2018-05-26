---
title: GetPortAttributesByWWN\_OUT structure
description: The GetPortAttributesByWWN\_OUT structure is used to report the output parameter data of the GetPortAttributesByWWN WMI method to the WMI client.
ms.assetid: 9a4d04de-2c44-4f13-ac6f-32e2fe879e4e
keywords:
- GetPortAttributesByWWN_OUT structure Storage Devices
- PGetPortAttributesByWWN_OUT structure pointer Storage Devices
topic_type:
- apiref
api_name:
- GetPortAttributesByWWN_OUT
api_location:
- hbapiwmi.h
api_type:
- HeaderDef
ms.date: 05/31/2018
ms.topic: structure
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# GetPortAttributesByWWN\_OUT structure

The GetPortAttributesByWWN\_OUT structure is used to report the output parameter data of the [**GetPortAttributesByWWN**](https://msdn.microsoft.com/library/windows/hardware/ff554965) WMI method to the WMI client.

## Syntax


```C++
typedef struct _GetPortAttributesByWWN_OUT {
  ULONG                         HBAStatus;
  MSFC_HBAPortAttributesResults PortAttributes;
} GetPortAttributesByWWN_OUT, *PGetPortAttributesByWWN_OUT;
```



## Members

<dl> <dt>

**HBAStatus**
</dt> <dd>

Contains a value associated with the WMI class qualifier [HBA\_STATUS](https://msdn.microsoft.com/library/windows/hardware/ff557233) that indicates the result of an HBA query operation.

</dd> <dt>

**PortAttributes**
</dt> <dd>

Contains a structure of type [**MSFC\_HBAPortAttributesResults**](msfc-hbaportattributesresults.md) that holds the port attributes to be reported.

</dd> </dl>

## Remarks

The WMI tool suite generates a declaration of the GetPortAttributesByWWN\_OUT structure in *Hbapiwmi.h* when it compiles the [MSFC\_HBAAdapterMethods WMI Class](https://msdn.microsoft.com/library/windows/hardware/ff562506).

## Requirements



|                   |                                                                                                            |
|-------------------|------------------------------------------------------------------------------------------------------------|
| Header<br/> | <dl> <dt>Hbapiwmi.h (include Hbapiwmi.h)</dt> </dl> |



## See also

<dl> <dt>

[**GetPortAttributesByWWN**](https://msdn.microsoft.com/library/windows/hardware/ff554965)
</dt> <dt>

[HBA\_STATUS](https://msdn.microsoft.com/library/windows/hardware/ff557233)
</dt> <dt>

[**MSFC\_HBAPortAttributesResults**](msfc-hbaportattributesresults.md)
</dt> </dl>

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bstorage\storage%5D:%20GetPortAttributesByWWN_OUT%20structure%20%20RELEASE:%20%283/29/2018%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")





