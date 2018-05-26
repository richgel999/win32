---
Description: Retrieves the number of Attribute objects in the collection.
ms.assetid: d5f9db7d-52a2-4feb-8d35-902caf536510
title: Attributes.Count property
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Attributes.Count property

\[CAPICOM is a 32-bit only component that is available for use in the following operating systems: Windows Server 2008, Windows Vista, Windows XP. Instead, use the [**CryptographicAttributeObjectCollection Class**](T:System.Security.Cryptography.CryptographicAttributeObjectCollection) in the [**System.Security.Cryptography**](frlrfSystemSecurityCryptography) namespace.\]

The **Count** property retrieves the number of [**Attribute**](attribute.md) objects in the collection.

This property is read-only.

## Syntax


```VB
Attributes.Count As Long
```



## Property value

The number of [**Attribute**](attribute.md) objects in the collection. Each **Attribute** object represents a single attribute in the collection.

## Remarks

The **Count** property can be used to specify the last [**Attribute**](attribute.md) object in the collection when retrieving a specific **Attribute** object by using the [**Attributes.Item**](attributes-item.md) property.

## Requirements



|                                  |                                                                                        |
|----------------------------------|----------------------------------------------------------------------------------------|
| End of client support<br/> | Windows Vista<br/>                                                               |
| End of server support<br/> | Windows Server 2008<br/>                                                         |
| Redistributable<br/>       | CAPICOM 2.0 or later on Windows Server 2003 and Windows XP<br/>                  |
| DLL<br/>                   | <dl> <dt>Capicom.dll</dt> </dl> |



## See also

<dl> <dt>

[**Attributes**](attributes.md)
</dt> </dl>

 

 



