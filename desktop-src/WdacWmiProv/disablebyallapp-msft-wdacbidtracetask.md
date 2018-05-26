---
title: DisableByAllApp method of the MSFT\_WdacBidTraceTask class
description: Disables Built-in Diagnostics Tracing (BidTrace) for troubleshooting WDAC components.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: cf1d2197-9431-4340-8415-5b785966c047
ms.prod: windows-server-dev
ms.technology: windows-management-instrumentation
ms.tgt_platform: multiple
keywords:
- DisableByAllApp method
- DisableByAllApp method, MSFT_WdacBidTraceTask class
- MSFT_WdacBidTraceTask class, DisableByAllApp method
topic_type:
- apiref
api_name:
- MSFT_WdacBidTraceTask.DisableByAllApp
api_location:
- WdacWmiProv.dll
api_type:
- COM
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# DisableByAllApp method of the MSFT\_WdacBidTraceTask class

Disables Built-in Diagnostics Tracing (BidTrace) for troubleshooting WDAC components.

## Syntax


```mof
uint32 DisableByAllApp(
  [in]  boolean           PassThru,
  [in]  boolean           IncludeAllApplications,
  [in]  string            Platform,
  [out] MSFT_WdacBidTrace cmdletOutput[]
);
```



## Parameters

<dl> <dt>

*PassThru* \[in\]
</dt> <dd>

Passes the object created by this cmdlet through the pipeline. By default, this cmdlet does not pass any objects through the pipeline.

</dd> <dt>

*IncludeAllApplications* \[in\]
</dt> <dd>

Disable BidTrace for all applications.

</dd> <dt>

*Platform* \[in\]
</dt> <dd>

The platform architecture of the WDAC BidTrace setting. Possible values are '32-bit', '64-bit' or 'All'. The default is '32-bit' on a 32-bit process and '64-bit' on a 64-bit process. This is the platform architecture on the remote machine if this command is executed on a remote CIM session.

</dd> <dt>

*cmdletOutput* \[out\]
</dt> <dd>

The output is an array of CIM objects of type [**MSFT\_WdacBidTrace**](msft-wdacbidtrace.md), each of which represents a WDAC BidTrace setting.

</dd> </dl>

## Requirements



|                                     |                                                                                            |
|-------------------------------------|--------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 8<br/>                                                                       |
| Minimum supported server<br/> | Windows Server 2012<br/>                                                             |
| Namespace<br/>                | Root\\Microsoft\\Windows\\WDAC<br/>                                                  |
| MOF<br/>                      | <dl> <dt>WdacWmiProv.mof</dt> </dl> |
| DLL<br/>                      | <dl> <dt>WdacWmiProv.dll</dt> </dl> |



## See also

<dl> <dt>

[**MSFT\_WdacBidTraceTask**](msft-wdacbidtracetask.md)
</dt> <dt>

[**MSFT\_WdacBidTrace**](msft-wdacbidtrace.md)
</dt> </dl>

 

 




