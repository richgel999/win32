---
Description: Builds a matrix that scales along the x-axis, the y-axis, and the z-axis.
ms.assetid: 1804bf41-26de-4be1-ad62-7a871d7408e6
title: D3DXMatrixScaling function
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# D3DXMatrixScaling function

Builds a matrix that scales along the x-axis, the y-axis, and the z-axis.

## Syntax


```C++
D3DXMATRIX* D3DXMatrixScaling(
  _Inout_ D3DXMATRIX *pOut,
  _In_    FLOAT      sx,
  _In_    FLOAT      sy,
  _In_    FLOAT      sz
);
```



## Parameters

<dl> <dt>

*pOut* \[in, out\]
</dt> <dd>

Type: **[**D3DXMATRIX**](direct3d9.d3dxmatrix)\***

Pointer to the [**D3DXMATRIX**](d3d10-d3dxmatrix.md) structure that is the result of the operation.

</dd> <dt>

*sx* \[in\]
</dt> <dd>

Type: **[**FLOAT**](winprog.windows_data_types)**

Scaling factor that is applied along the x-axis.

</dd> <dt>

*sy* \[in\]
</dt> <dd>

Type: **[**FLOAT**](winprog.windows_data_types)**

Scaling factor that is applied along the y-axis.

</dd> <dt>

*sz* \[in\]
</dt> <dd>

Type: **[**FLOAT**](winprog.windows_data_types)**

Scaling factor that is applied along the z-axis.

</dd> </dl>

## Return value

Type: **[**D3DXMATRIX**](direct3d9.d3dxmatrix)\***

Pointer to the scaling transformation D3DXMATRIX.

## Remarks

The return value for this function is the same value returned in the pOut parameter. In this way, the D3DXMatrixScaling function can be used as a parameter for another function.

## Requirements



|                    |                                                                                         |
|--------------------|-----------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3DX10Math.h</dt> </dl> |
| Library<br/> | <dl> <dt>D3DX10.lib</dt> </dl>   |



## See also

<dl> <dt>

[Math Functions](d3d10-graphics-reference-d3dx10-functions-math.md)
</dt> </dl>

 

 



