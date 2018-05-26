---
Description: All processes (applications or DLLs) that call Winsock functions must initialize the use of the Windows Sockets DLL before making other Winsock functions calls. This also makes certain that Winsock is supported on the system.
ms.assetid: 300858d8-bed3-4a3c-abb5-2cecd100e5d7
title: Initializing Winsock
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Initializing Winsock

All processes (applications or DLLs) that call Winsock functions must initialize the use of the Windows Sockets DLL before making other Winsock functions calls. This also makes certain that Winsock is supported on the system.

**To initialize Winsock**

1.  Create a [**WSADATA**](/windows/win32/winsock/ns-winsock-wsadata?branch=master) object called wsaData.
    ```C++
    WSADATA wsaData;
    ```

    

2.  Call [**WSAStartup**](/windows/win32/winsock/nf-winsock-wsastartup?branch=master) and return its value as an integer and check for errors.
    ```C++
    int iResult;

    // Initialize Winsock
    iResult = WSAStartup(MAKEWORD(2,2), &amp;wsaData);
    if (iResult != 0) {
        printf("WSAStartup failed: %d\n", iResult);
        return 1;
    }
    ```

    

The [**WSAStartup**](/windows/win32/winsock/nf-winsock-wsastartup?branch=master) function is called to initiate use of WS2\_32.dll.

The [**WSADATA**](/windows/win32/winsock/ns-winsock-wsadata?branch=master) structure contains information about the Windows Sockets implementation. The MAKEWORD(2,2) parameter of [**WSAStartup**](/windows/win32/winsock/nf-winsock-wsastartup?branch=master) makes a request for version 2.2 of Winsock on the system, and sets the passed version as the highest version of Windows Sockets support that the caller can use.

Next Step for a Client: [Creating a Socket for the Client](creating-a-socket-for-the-client.md)

Next Step for a Server: [Creating a Socket for the Server](creating-a-socket-for-the-server.md)

## Related topics

<dl> <dt>

[Getting Started With Winsock](getting-started-with-winsock.md)
</dt> <dt>

[Creating a Basic Winsock Application](creating-a-basic-winsock-application.md)
</dt> </dl>

 

 


