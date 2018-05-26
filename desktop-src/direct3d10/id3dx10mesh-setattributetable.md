---
Description: Sets the attribute table for a mesh and the number of entries stored in the table.
ms.assetid: 629fd31b-d88a-4650-82ed-ab7c40690986
title: ID3DX10MeshSetAttributeTable method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# ID3DX10Mesh::SetAttributeTable method

Sets the attribute table for a mesh and the number of entries stored in the table.

## Syntax


```C++
HRESULT SetAttributeTable(
  [in] const D3DX10_ATTRIBUTE_RANGE *pAttribTable,
  [in]       UINT                   cAttribTableSize
);
```



## Parameters

<dl> <dt>

*pAttribTable* \[in\]
</dt> <dd>

Type: **const [**D3DX10\_ATTRIBUTE\_RANGE**](d3dx10-attribute-range.md)\***

Pointer to an array of D3DX10\_ATTRIBUTE\_RANGE structures, representing the entries in the mesh attribute table.

</dd> <dt>

*cAttribTableSize* \[in\]
</dt> <dd>

Type: **[**UINT**](winprog.windows_data_types)**

Number of attributes in the mesh attribute table.

</dd> </dl>

## Return value

Type: **[**HRESULT**](455d07e9-52c3-4efb-a9dc-2955cbfd38cc)**

The return value is one of the values listed in [Direct3D 10 Return Codes](d3d10-graphics-reference-returnvalues.md).

## Remarks

If an application keeps track of the information in an attribute table, and rearranges the table as a result of changes to attributes or faces, this method allows the application to update the attribute tables instead of calling ID3DX10Mesh::Optimize again.

## Requirements



|                    |                                                                                       |
|--------------------|---------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3DX10.h</dt> </dl>   |
| Library<br/> | <dl> <dt>D3DX10.lib</dt> </dl> |



## See also

<dl> <dt>

[ID3DX10Mesh](id3dx10mesh.md)
</dt> <dt>

[D3DX Interfaces](d3d10-graphics-reference-d3dx10-interfaces.md)
</dt> </dl>

 

 



