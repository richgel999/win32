---
title: AddResourcesToResourcePool method of the CIM\_ResourcePoolConfigurationService class
description: Starts a job to add resources to a resource pool.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: 776d4256-25fa-4ae6-a62b-705d21cf9288
ms.prod: windows-server-dev
ms.technology:
- failover-cluster-hyperv
- windows-management-instrumentation
ms.tgt_platform: multiple
keywords:
- AddResourcesToResourcePool method
- AddResourcesToResourcePool method, CIM_ResourcePoolConfigurationService class
- CIM_ResourcePoolConfigurationService class, AddResourcesToResourcePool method
topic_type:
- apiref
api_name:
- CIM_ResourcePoolConfigurationService.AddResourcesToResourcePool
api_location:
- VMMS.exe
api_type:
- COM
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# AddResourcesToResourcePool method of the CIM\_ResourcePoolConfigurationService class

Starts a job to add resources to a resource pool.

## Syntax


```mof
uint32 AddResourcesToResourcePool(
  [in]  CIM_LogicalDevice REF HostResources[],
  [in]  CIM_ResourcePool  REF Pool,
  [out] CIM_ConcreteJob   REF Job
);
```



## Parameters

<dl> <dt>

*HostResources* \[in\]
</dt> <dd>

An array that contains references to the resources to add to the resource pool.

</dd> <dt>

*Pool* \[in\]
</dt> <dd>

The resource pool that receives the added resoures.

</dd> <dt>

*Job* \[out\]
</dt> <dd>

A reference to the job for the operation. When the job is finished this parameter can be set to **NULL**.

</dd> </dl>

## Return value

The possible return values:

<dl> <dt>

**Job Completed with No Error**
</dt> <dd>

0

The job completed successfully.

</dd> <dt>

**Not Supported**
</dt> <dd>

1

</dd> <dt>

**Unknown**
</dt> <dd>

2

</dd> <dt>

**Timeout**
</dt> <dd>

3

</dd> <dt>

**Failed**
</dt> <dd>

4

</dd> <dt>

**Invalid Parameter**
</dt> <dd>

5

</dd> <dt>

**In Use**
</dt> <dd>

6

</dd> <dt>

**Incorrect ResourceType for the Pool**
</dt> <dd>

7

</dd> <dt>

**DMTF Reserved**
</dt> <dd>

8 4095

</dd> <dt>

**Method Parameters Checked - Job Started**
</dt> <dd>

4096

</dd> <dt>

**Size Not Supported**
</dt> <dd>

4097

</dd> <dt>

**Method Reserved**
</dt> <dd>

4098 32767

</dd> <dt>

**Vendor Specific**
</dt> <dd>

32768 65535

</dd> </dl>

## Requirements



|                                     |                                                                                                        |
|-------------------------------------|--------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | None supported<br/>                                                                              |
| Minimum supported server<br/> | Windows Server 2016<br/>                                                                         |
| Namespace<br/>                | Root\\HyperVCluster\\v2<br/>                                                                     |
| MOF<br/>                      | <dl> <dt>WindowsHyperVCluster.V2.mof</dt> </dl> |
| DLL<br/>                      | <dl> <dt>VMMS.exe</dt> </dl>                    |



## See also

<dl> <dt>

[**CIM\_ResourcePoolConfigurationService**](cim-resourcepoolconfigurationservice.md)
</dt> </dl>

 

 




