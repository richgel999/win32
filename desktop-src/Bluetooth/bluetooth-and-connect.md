---
title: Bluetooth and connect
description: Bluetooth uses the connect function to connect to a target Bluetooth device, using a previously created Bluetooth socket.
ms.assetid: f9ab3934-7698-4f5e-8194-cca86685a4f8
keywords:
- Bluetooth Bluetooth
- connect Bluetooth
- Bluetooth and connect Bluetooth
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Bluetooth and connect

Bluetooth uses the [**connect**](https://msdn.microsoft.com/library/windows/desktop/ms737625) function to connect to a target Bluetooth device, using a previously created Bluetooth socket. The *name* parameter of the **connect** function, which is a [**SOCKADDR\_BTH**](/windows/win32/Ws2bth/ns-ws2bth-_sockaddr_bth?branch=master) structure, must specify a target Bluetooth device. Two mechanisms are used to identify the target device:

-   The [**SOCKADDR\_BTH**](/windows/win32/Ws2bth/ns-ws2bth-_sockaddr_bth?branch=master) structure can directly specify the port number to which a connect is requested. This mechanism requires the application to perform its own SDP queries prior to attempting a [**connect**](https://msdn.microsoft.com/library/windows/desktop/ms737625) operation.
-   The [**SOCKADDR\_BTH**](/windows/win32/Ws2bth/ns-ws2bth-_sockaddr_bth?branch=master) structure can specify the unique service class ID of the service to which it wants to connect. If the peer device has more than one port that corresponds to the service class ID, the [**connect**](https://msdn.microsoft.com/library/windows/desktop/ms737625) function call connects to the first valid service. This mechanism can be used without prior SDP queries.

When using the [**SOCKADDR\_BTH**](/windows/win32/Ws2bth/ns-ws2bth-_sockaddr_bth?branch=master) structure with the [**connect**](https://msdn.microsoft.com/library/windows/desktop/ms737625) function, the following requirements apply:

-   The **btAddr** member must be a valid remote radio address.
-   For the **serviceClassId** member, if the port member is zero, the system attempts to use **serviceClassId** to resolve the remote port corresponding to the service. The service class is a normalized 128-bit GUID, defined by the Bluetooth specification. Common GUIDs are defined by the Bluetooth Assigned Numbers document. Alternatively, a unique GUID may be used for a domain-specific application.
-   The **port** member must be a valid remote port, or zero if the **serviceClassId** member is specified.

The following table lists the result codes for Bluetooth and the [**connect**](https://msdn.microsoft.com/library/windows/desktop/ms737625) function.

| Error/error\#                    | Description                                                                        |
|----------------------------------|------------------------------------------------------------------------------------|
| WSAEISCONN10056<br/>       | The [**connect**](https://msdn.microsoft.com/library/windows/desktop/ms737625) function called for already connected socket. |
| WSAEACCES10013<br/>        | Connecting application requested authentication, but authentication failed.        |
| WSAENOBUFS10055<br/>       | Unrecoverable out-of-memory error.                                                 |
| WSAEADDRINUSE10048<br/>    | The port/channel number requested is in use.                                       |
| WSAETIMEDOUT10060<br/>     | The I/O timed out at the Bluetooth radio level (PAGE\_TIMEOUT).                    |
| WSAEDISCON10101<br/>       | The RFCOMM channel disconnected by remote peer.                                    |
| WSAECONNRESET10054<br/>    | The RFCOMM multiplexor (session) disconnected by remote peer.                      |
| WSAECONNABORTED10053<br/>  | Socket shut down by application.                                                   |
| WSAENETUNREACH10051<br/>   | Error other than time-out at L2CAP or Bluetooth radio level.                       |
| WSAEHOSTDOWN10064<br/>     | The RFCOMM received DM response.                                                   |
| WSAENETDOWN10050<br/>      | Unexpected network error.                                                          |
| WSAESHUTDOWN10058<br/>     | The L2CAP channel disconnected by remote peer.                                     |
| WSAEADDRNOTAVAIL10049<br/> | Bluetooth port/channel or device address not valid.                                |
| WSAEINVAL10022<br/>        | Plug and Play, driver-stack event, or other error caused failure.                  |



 

## Related topics

<dl> <dt>

[Windows Sockets](https://msdn.microsoft.com/library/windows/desktop/ms740673)
</dt> <dt>

[**connect**](https://msdn.microsoft.com/library/windows/desktop/ms737625)
</dt> <dt>

[**SOCKADDR\_BTH**](/windows/win32/Ws2bth/ns-ws2bth-_sockaddr_bth?branch=master)
</dt> </dl>

 

 




