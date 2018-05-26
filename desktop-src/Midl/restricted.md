---
title: restricted attribute
description: The \ restricted\ attribute specifies that a library, or member of a module, interface, or dispinterface cannot be called arbitrarily.
ms.assetid: ad1ae84f-77f4-4028-bd71-ff01414e474e
keywords:
- restricted attribute MIDL
topic_type:
- apiref
api_name:
- restricted
api_type:
- NA
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# restricted attribute

The **\[restricted\]** attribute specifies that a library, or member of a module, interface, or dispinterface cannot be called arbitrarily.

``` syntax
[
    restricted
    [, other-attributes]
] 
statement-type statement-name 
{
    definitions
};
```

## Parameters

<dl> <dt>

*other-attributes* 
</dt> <dd>

Zero or more MIDL attributes.

</dd> <dt>

*statement-type* 
</dt> <dd>

One of the following: [**library**](library.md), [**module**](module.md), [**interface**](interface.md), [**dispinterface**](dispinterface.md).

</dd> <dt>

*statement-name* 
</dt> <dd>

The identifier by which the software refers to this statement.

</dd> <dt>

*definitions* 
</dt> <dd>

MIDL language elements that define the contents of this statement.

</dd> </dl>

## Remarks

This attribute enables you to control access to elements of interfaces, libraries, modules, and dispinterfaces. For example, it can prevent a data item from being used by a macro programmer. You can apply this attribute to a member of a [**coclass**](coclass.md), independent of whether the member is a dispinterface or interface, and independent of whether the member is a sink (incoming) or source (outgoing). A member of a **coclass** cannot have both the **\[restricted\]** and **\[default\]** attributes.

### Flags

IMPLTYPEFLAG\_FRESTRICTED, FUNCFLAG\_FRESTRICTED

## Examples

``` syntax
[
    uuid(12345678-1234-1234-1234-123456789ABC), 
    version (1.0), 
    restricted
] 
library MyLibrary
{
    // Library definition statements.
};

[propget, restricted] HRESULT MyProc(void);
```

## See also

<dl> <dt>

[TYPEFLAGS](bf34cc90-f772-4562-9d18-7cf35aeed41e)
</dt> <dt>

[**library**](library.md)
</dt> <dt>

[**interface**](interface.md)
</dt> <dt>

[**dispinterface**](dispinterface.md)
</dt> <dt>

[**module**](module.md)
</dt> <dt>

[ODL File Syntax](df7aa86f-1453-4409-939e-788d469d611e)
</dt> <dt>

[ODL File Example](86d64a4f-08eb-422a-bb1d-dfa868094645)
</dt> <dt>

[Generating a Type Library With MIDL](generating-a-type-library-with-midl-2.md)
</dt> </dl>

 

 



