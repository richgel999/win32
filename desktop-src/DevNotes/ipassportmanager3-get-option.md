---
Description: Retrieves the value of a specific Microsoft .NET Passport sign-in option.
ms.assetid: a38ffed3-a45b-4bac-8101-3e09f34f3891
title: IPassportManager3get\_Option method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IPassportManager3::get\_Option method

Retrieves the value of a specific Microsoft .NET Passport sign-in option.

> [!Note]  
> The **get\_Option** method belongs to the [**IPassportManager3**](_PASSPORT.NET_IPassportManager3_Interface) interface. This topic supplements the initial documentation.

 

## Syntax


```C++
HRESULT get_Option(
  [in]  BSTR    name,
  [out] VARIANT *pVal
);
```



## Parameters

<dl> <dt>

*name* \[in\]
</dt> <dd>

The sign-in option to be retrieved. Currently, the only supported option is "iMode".

</dd> <dt>

*pVal* \[out\]
</dt> <dd>

A pointer to a **VARIANT** (VT\_BOOL) that receives the value of the option. This value can be True or False.

</dd> </dl>

## Return value

Returns S\_OK when the method succeeds.

## Remarks

This method ships with older versions of the Passport SDK.

 

 


