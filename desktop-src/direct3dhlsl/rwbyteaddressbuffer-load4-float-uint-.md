---
title: Load4(uint,uint) function
description: Gets four values and returns status of the operation.
ms.assetid: 10C21836-3CE4-4AE9-82F4-C8BBDE19CA69
keywords:
- Load4 function HLSL
topic_type:
- apiref
api_name:
- Load4
api_type:
- NA
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Load4(uint,uint) function

Gets four values and returns status of the operation.

## Syntax


```C++
uint4 Load4(
  _In_  uint Location,
  _Out_ uint Status
);
```



## Parameters

<dl> <dt>

*Location* \[in\]
</dt> <dd>

Type: **uint**

The location of the buffer.

</dd> <dt>

*Status* \[out\]
</dt> <dd>

Type: **uint**

The status of the operation. You can't access the status directly; instead, pass the status to the [**CheckAccessFullyMapped**](checkaccessfullymapped.md) intrinsic function. **CheckAccessFullyMapped** returns **TRUE** if all values from the corresponding **Sample**, **Gather**, or **Load** operation accessed mapped tiles in a [tiled resource](https://msdn.microsoft.com/library/windows/desktop/dn312084#tile). If any values were taken from an unmapped tile, **CheckAccessFullyMapped** returns **FALSE**.

</dd> </dl>

## Return value

Type: **uint4**

Four values.

## Remarks

This function is supported for the following types of shaders:



| Vertex | Hull | Domain | Geometry | Pixel | Compute |
|--------|------|--------|----------|-------|---------|
|        |      |        |          | x     | x       |



 

## See also

<dl> <dt>

[Load4 methods](rwbyteaddressbuffer-load4.md)
</dt> </dl>

 

 



