---
Description: Create the best Direct3D 10 device that represents the display adapter. If a Direct3D 10.1-compatible device can be created, it will be possible to acquire an ID3D10Device1 Interface pointer from the returned device interface pointer.
ms.assetid: 1af8f4e5-a59e-403a-95d2-069b91bad93e
title: D3DX10CreateDevice function
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# D3DX10CreateDevice function

Create the best Direct3D 10 device that represents the display adapter. If a Direct3D 10.1-compatible device can be created, it will be possible to acquire an [**ID3D10Device1 Interface**](/windows/win32/D3D10_1/nn-d3d10_1-id3d10device1?branch=master) pointer from the returned device interface pointer.

## Syntax


```C++
HRESULT D3DX10CreateDevice(
  _In_  IDXGIAdapter      *pAdapter,
  _In_  D3D10_DRIVER_TYPE DriverType,
  _In_  HMODULE           Software,
  _In_  UINT              Flags,
  _Out_ ID3D10Device      **ppDevice
);
```



## Parameters

<dl> <dt>

*pAdapter* \[in\]
</dt> <dd>

Type: **[**IDXGIAdapter**](direct3ddxgi.idxgiadapter)\***

Pointer to the display adapter (see the [**IDXGIAdapter**](direct3ddxgi.idxgiadapter) interface) when creating a hardware device; otherwise set this parameter to **NULL**. If **NULL** is specified when creating a hardware device, Direct3D will use the first adapter enumerated by the [**IDXGIFactory**](direct3ddxgi.idxgifactory) interface.

</dd> <dt>

*DriverType* \[in\]
</dt> <dd>

Type: **[**D3D10\_DRIVER\_TYPE**](/windows/win32/D3D10misc/ne-d3d10misc-d3d10_driver_type?branch=master)**

The device-driver type (see the [**D3D10\_DRIVER\_TYPE**](/windows/win32/D3D10misc/ne-d3d10misc-d3d10_driver_type?branch=master) enumeration). The driver type determines the type of device you will create.

</dd> <dt>

*Software* \[in\]
</dt> <dd>

Type: **[**HMODULE**](winprog.windows_data_types)**

A handle to a loaded module that implements a software driver (such as D3D10Ref.dll). To get a handle, call the [GetModuleHandle](http://msdn2.microsoft.com/en-us/library/ms683199.aspx) function.

</dd> <dt>

*Flags* \[in\]
</dt> <dd>

Type: **[**UINT**](winprog.windows_data_types)**

Device creation flags (see the [**D3D10\_CREATE\_DEVICE\_FLAG**](/windows/win32/D3D10/ne-d3d10-d3d10_create_device_flag?branch=master) enumeration) that enable [API layers](d3d10-graphics-programming-guide-api-features-layers.md). These flags can be bitwise OR'd together.

</dd> <dt>

*ppDevice* \[out\]
</dt> <dd>

Type: **[**ID3D10Device**](/windows/win32/D3D10/nn-d3d10-id3d10device?branch=master)\*\***

Address of a pointer to the device created (see the [**ID3D10Device**](/windows/win32/D3D10/nn-d3d10-id3d10device?branch=master) interface).

</dd> </dl>

## Return value

Type: **[**HRESULT**](455d07e9-52c3-4efb-a9dc-2955cbfd38cc)**

This function returns one of the following [Direct3D 10 Return Codes](d3d10-graphics-reference-returnvalues.md).

## Remarks

This function attempts to create the best device for the hardware. First, the function attempts to create a 10.1 device. If a 10.1 device cannot be created, the function attempts to create a 10.0 device. If neither device is successfully created, the function returns E\_FAIL.

If your application needs to create only a 10.1 device, or a 10.0 device only, use the following functions instead:

-   Use the [**D3D10CreateDevice**](/windows/win32/D3D10Misc/nf-d3d10misc-d3d10createdevice?branch=master) function to create a Direct3D 10.0 device only.
-   Use the [**D3D10CreateDevice1**](/windows/win32/D3D10_1/nf-d3d10_1-d3d10createdevice1?branch=master) function to create a Direct3D 10.1 device only.
-   Use the [**D3DX10GetFeatureLevel1**](d3dx10getfeaturelevel1.md) function to get an [**ID3D10Device1**](/windows/win32/D3D10_1/nn-d3d10_1-id3d10device1?branch=master) interface pointer from an [**ID3D10Device**](/windows/win32/D3D10/nn-d3d10-id3d10device?branch=master) interface pointer.

A Direct3D 10.1 device can only be created on computers running Windows Vista Service Pack 1 or later, and with Direct3D 10.1-compatible hardware installed. However, it is legal to call this function on computers running any version of Windows that has the D3DX10 DLL installed.

## Requirements



|                   |                                                                                         |
|-------------------|-----------------------------------------------------------------------------------------|
| Header<br/> | <dl> <dt>D3DX10Core.h</dt> </dl> |



## See also

<dl> <dt>

[General Purpose Functions](d3d10-graphics-reference-d3dx10-functions-general-purpose.md)
</dt> </dl>

 

 



