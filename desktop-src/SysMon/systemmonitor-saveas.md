---
title: SystemMonitor.SaveAs method
description: Saves the counter values in the graph view to a log file.
ms.assetid: 34824c54-d8f4-4c2b-b417-aa0914c7164b
keywords:
- SaveAs method SysMon
- SaveAs method SysMon , SystemMonitor object
- SystemMonitor object SysMon , SaveAs method
topic_type:
- apiref
api_name:
- SystemMonitor.SaveAs
api_location:
- Sysmon.ocx
api_type:
- COM
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# SystemMonitor.SaveAs method

Saves the counter values in the graph view to a log file.

## Syntax


```VB
SystemMonitor.SaveAs( _
  ByVal fileName As String, _
  ByVal fileType As SysmonFileType _
)
```



## Parameters

<dl> <dt>

*fileName* \[in\]
</dt> <dd>

File path of the log file. You can specify the path as an absolute, relative, or UNC path. The log file name extension must be either .tsv or .htm. If a folder in the path does not exist, SYSMON will create it. If the file exists, the file is overwritten. SYSMON applies the default ACLs from the parent directory.

</dd> <dt>

*fileType* \[in\]
</dt> <dd>

Format of the counter data saved to the log file. You can specify either [**SysmonFileType.sysmonFileHtml**](/windows/desktop/api/ISysmon/ne-isysmon-__midl___midl_itf_sysmon_0000_0000_0001) or **SysmonFileType.sysmonFileTsv**.

</dd> </dl>

## Return value

This method does not return a value.

## Remarks

Only the counter data visible in the graph view is saved (for the actual number of data points saved, see [**SystemMonitor.DataPointCount**](systemmonitor-datapointcount.md)).

## Requirements



|                                     |                                                                                       |
|-------------------------------------|---------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                        |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/>                                  |
| DLL<br/>                      | <dl> <dt>Sysmon.ocx</dt> </dl> |



## See also

<dl> <dt>

[**SystemMonitor**](systemmonitor.md)
</dt> <dt>

[**SystemMonitor.Relog**](systemmonitor-relog.md)
</dt> </dl>

 

 




