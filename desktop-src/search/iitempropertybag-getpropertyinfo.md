---
Description: Gets the information required to read or save the properties in the property bag. The IItemPropertyBag interface is supported only on Windows XP and Windows Server 2003, and should no longer be used.
ms.assetid: 1667b67d-9dd2-48a6-81dd-c8b06834cef0
title: IItemPropertyBagGetPropertyInfo method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IItemPropertyBag::GetPropertyInfo method

Gets the information required to read or save the properties in the property bag. The [**IItemPropertyBag**](iitempropertybag.md) interface is supported only on Windows XP and Windows Server 2003, and should no longer be used.

## Syntax


```C++
HRESULT GetPropertyInfo(
  [in]  ULONG    iProperty,
  [in]  ULONG    cProperties,
  [out] ITEMPROP *pPropBag,
  [out] ULONG    *pcProperties
);
```



## Parameters

<dl> <dt>

*iProperty* \[in\]
</dt> <dd>

The zero-based index of the first property for which information is requested.

</dd> <dt>

*cProperties* \[in\]
</dt> <dd>

The number of properties to get information for. This argument specifies the number of array elements in *pPropBag*.

</dd> <dt>

*pPropBag* \[out\]
</dt> <dd>

Pointer to an array of [**ITEMPROP**](/windows/win32/subsmgr/ns-subsmgr-_tagitemprop?branch=master) structures that receives the information for the properties.

</dd> <dt>

*pcProperties* \[out\]
</dt> <dd>

Receives a pointer to a **ULONG** variable that receives the number of properties for which information was retrieved.

</dd> </dl>

## Return value

If the method succeeds, it returns S\_OK. Otherwise, it returns an **HRESULT** error code.

## Remarks

The [**IItemPropertyBag**](iitempropertybag.md) interface is supported only on Windows XP and Windows Server 2003, and should no longer be used.

To preview attachments with a third-party protocol handler on computers running Windows XP or Windows Server 2003, it may be necessary to use the [**IItemPropertyBag**](iitempropertybag.md) interface and the following APIs: the [**ISearchProtocolUI**](-search-isearchprotocolui.md), [**IItemPreviewerExt**](-search-iitempreviewerext.md) and [**ISearchItem**](-search-isearchitem.md) interfaces, the [**LINKINFO**](-search-linkinfo.md) and [**ITEMPROP**](/windows/win32/subsmgr/ns-subsmgr-_tagitemprop?branch=master) structures, and the [**LINKTYPE**](-search-linktype.md) enumeration.

## Requirements



|                                     |                                                      |
|-------------------------------------|------------------------------------------------------|
| Minimum supported client<br/> | Windows XP with SP2 \[desktop apps only\]<br/> |
| Minimum supported server<br/> | Windows Server 2003 \[desktop apps only\]<br/> |
| Redistributable<br/>          | Windows Desktop Search (WDS) 3.0<br/>          |



## See also

<dl> <dt>

[**IItemPropertyBag**](iitempropertybag.md)
</dt> </dl>

 

 



