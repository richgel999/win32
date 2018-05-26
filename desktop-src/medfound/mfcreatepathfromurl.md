---
Description: Converts a file URL to a Microsoft MS-DOS path.
ms.assetid: c35988ad-6cf8-41ec-bee9-e3bb982310ee
title: MFCreatePathFromURL function
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# MFCreatePathFromURL function

\[This API is not supported and may be altered or unavailable in the future. Instead, applications should call [**PathCreateFromUrl**](shell.PathCreateFromUrl).\]

Converts a file URL to a Microsoft MS-DOS path.

## Syntax


```C++
HRESULT MFCreatePathFromURL(
  _In_opt_ LPCWSTR pwszFileURL,
  _Out_    LPWSTR  *ppwszFilePath
);
```



## Parameters

<dl> <dt>

*pwszFileURL* \[in, optional\]
</dt> <dd>

A null-terminated string that contains the URL. The maximum length of the string is **INTERNET\_MAX\_URL\_LENGTH**.

</dd> <dt>

*ppwszFilePath* \[out\]
</dt> <dd>

Receives a null-terminated string that contains the URL. The caller must free the string by calling [**CoTaskMemFree**](com.cotaskmemfree).

</dd> </dl>

## Return value

The function returns an **HRESULT**. Possible values include, but are not limited to, those in the following table.



| Return code                                                                                  | Description                                                                                                 |
|----------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------|
| <dl> <dt>**S\_OK**</dt> </dl>         | The function succeeded. <br/>                                                                         |
| <dl> <dt>**E\_INVALIDARG**</dt> </dl> | Invalid argument. The string given in the *pwszFileURL* parameter cannot be converted to a path.<br/> |



 

## Remarks

This function has no associated import library. To call this function, you must use the [**LoadLibrary**](base.loadlibrary) and [**GetProcAddress**](base.getprocaddress) functions to dynamically link to Mfplat.dll.

## Requirements



|                                     |                                                                                       |
|-------------------------------------|---------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                        |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/>                                  |
| DLL<br/>                      | <dl> <dt>Mfplat.dll</dt> </dl> |



## See also

<dl> <dt>

[Media Foundation Functions](media-foundation-functions.md)
</dt> </dl>

 

 



