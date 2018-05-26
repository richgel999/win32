---
title: Address
description: Provides the address for the IPv6 Tunnel Address resource.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: 642DF70D-A602-40BB-8D72-C374F18CB29A
ms.prod: windows-server-dev
ms.technology: failover-clustering
ms.tgt_platform: multiple
keywords:
- Address Failover Cluster
topic_type:
- apiref
api_name:
- Address
api_type:
- NA
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# Address

Provides the address for the [IPv6 Tunnel Address](ipv6-tunnel-address.md) [resource](resources.md). The following table summarizes the attributes of the **Address** property.



| Attribute | Value                                                            |
|-----------|------------------------------------------------------------------|
| Data type | Null-terminated Unicode string                                   |
| Access    | [Read-only](read-only-properties.md)                            |
| Status    | Required                                                         |
| Structure | [**CLUSPROP\_SZ**](/windows/previous-versions/ClusAPI/?branch=master)                              |
| Maximum   | None (but see [Maximum Property Size](maximum-string-size.md).) |
| Default   | **NULL**                                                         |



 

## Requirements



|                                     |                                |
|-------------------------------------|--------------------------------|
| Minimum supported client<br/> | None supported<br/>      |
| Minimum supported server<br/> | Windows Server 2012<br/> |



## See also

<dl> <dt>

[IPv6 Tunnel Address Private Properties](ipv6-tunnel-address-private-properties.md)
</dt> <dt>

[**CLUSPROP\_SZ**](/windows/previous-versions/ClusAPI/?branch=master)
</dt> <dt>

[**CLUSPROP\_SZ\_DECLARE**](/windows/previous-versions/ClusAPI/nf-clusapi-clusprop_sz_declare?branch=master)
</dt> </dl>

 

 




