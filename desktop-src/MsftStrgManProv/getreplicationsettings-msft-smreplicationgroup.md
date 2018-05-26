---
title: GetReplicationSettings method of the MSFT\_SMReplicationGroup class
description: Retrieves the replication settings for a replication group.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: 19963f70-cf9d-4721-b321-8298aac84deb
ms.prod: windows-server-dev
ms.technology: windows-management-instrumentation
ms.tgt_platform: multiple
keywords:
- GetReplicationSettings method
- GetReplicationSettings method, MSFT_SMReplicationGroup class
- MSFT_SMReplicationGroup class, GetReplicationSettings method
topic_type:
- apiref
api_name:
- MSFT_SMReplicationGroup.GetReplicationSettings
api_location:
- StorageService.dll
api_type:
- COM
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# GetReplicationSettings method of the MSFT\_SMReplicationGroup class

Retrieves the replication settings for a replication group.

## Syntax


```mof
UInt32 GetReplicationSettings(
  [out]           MSFT_SMReplicationSettings REF ReplicationSettings,
  [in, optional]  String                         username,
  [in, optional]  String                         password,
  [out]           MSFT_SMJob                 REF Job,
  [out, optional] MSFT_SMExtendedStatus          ExtendedStatus
);
```



## Parameters

<dl> <dt>

*ReplicationSettings* \[out\]
</dt> <dd>

A reference to the object that represents the replication settings.

</dd> <dt>

*username* \[in, optional\]
</dt> <dd>

The username used to authenticate the SMI-S provider.

</dd> <dt>

*password* \[in, optional\]
</dt> <dd>

The password used to authenticate the SMI-S provider.

</dd> <dt>

*Job* \[out\]
</dt> <dd>

If this operation is asynchronous, when this method returns, this parameter contains a reference to the object that represents the job; otherwise this parameter is set to **NULL**.

</dd> <dt>

*ExtendedStatus* \[out, optional\]
</dt> <dd>

When this method returns, this parameter contains a [**MSFT\_SMExtendedStatus**](msft-smextendedstatus.md) object that contains detailed status information about the results of this operation.

</dd> </dl>

## Return value

Returns "0" on success, otherwise returns a WMI error code.

## Requirements



|                                     |                                                                                               |
|-------------------------------------|-----------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | None supported<br/>                                                                     |
| Minimum supported server<br/> | Windows Server 2016<br/>                                                                |
| Namespace<br/>                | Root\\Microsoft\\Windows\\Storage\\SM<br/>                                              |
| MOF<br/>                      | <dl> <dt>MsftStrgMan.mof</dt> </dl>    |
| DLL<br/>                      | <dl> <dt>StorageService.dll</dt> </dl> |



## See also

<dl> <dt>

[**MSFT\_SMReplicationGroup**](msft-smreplicationgroup.md)
</dt> </dl>

 

 




