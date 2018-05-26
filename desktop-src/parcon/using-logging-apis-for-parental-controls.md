---
Description: Using Logging APIs for Parental Controls
ms.assetid: 6c38a634-53ba-4e76-83bf-1a3f36efb0bc
title: Using Logging APIs for Parental Controls
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Using Logging APIs for Parental Controls

### Activity Reporting (Logging)

The WpcEvent.h header file contains definitions of the fields for each predefined activity event type and the custom type. This sample code shows the steps for logging an instant messaging conversation invitation event using the ETW publishing API:


```C++
#include <windows.h>
#include <evntprov.h>
#include <wpcevent.h>

#pragma comment(lib, "advapi32.lib")

#define BYTELEN(x) ((wcslen(x) + 1) * sizeof(WCHAR))

void main()
{
    REGHANDLE hWpc = 0;

    // Register
    ULONG res = EventRegister(&amp;WPCPROV, NULL, NULL, &amp;hWpc);

    // Log an event
    PCWSTR pcszAppName = L"SuperIM";
    PCWSTR pcszAppVersion = L"7.0";
    PCWSTR pcszAccountName = L"Kate";
    PCWSTR pcszConvID = L"102";
    PCWSTR pcszRequestingIP = L"192.168.2.100";
    PCWSTR pcszSender = L"imperson@isp.com";
    const DWORD dwReason = WPCFLAG_ISBLOCKED_NOTBLOCKED;
    const DWORD dwRecipCount = 1;
    PCWSTR pcszRecipient = L"otherim@isp.com";

    EVENT_DATA_DESCRIPTOR eventData[WPC_ARGS_CONVERSATIONINITEVENT_CARGS];

    EventDataDescCreate(&amp;eventData[WPC_ARGS_CONVERSATIONINITEVENT_APPNAME],
        (const PVOID)pcszAppName, (ULONG)BYTELEN(pcszAppName));

    EventDataDescCreate(&amp;eventData[WPC_ARGS_CONVERSATIONINITEVENT_APPVERSION],
        (const PVOID)pcszAppVersion,(ULONG)BYTELEN(pcszAppVersion));

    EventDataDescCreate(
        &amp;eventData[WPC_ARGS_CONVERSATIONINITEVENT_ACCOUNTNAME], 
        (const PVOID)pcszAccountName, (ULONG)BYTELEN(pcszAccountName));

    EventDataDescCreate(&amp;eventData[WPC_ARGS_CONVERSATIONINITEVENT_CONVID], 
        (const PVOID)pcszConvID, (ULONG)BYTELEN(pcszConvID));

    EventDataDescCreate(
        &amp;eventData[WPC_ARGS_CONVERSATIONINITEVENT_REQUESTINGIP], 
        (const PVOID)pcszRequestingIP, (ULONG)BYTELEN(pcszRequestingIP));

    EventDataDescCreate(&amp;eventData[WPC_ARGS_CONVERSATIONINITEVENT_SENDER],
        (const PVOID)pcszSender, (ULONG)BYTELEN(pcszSender));

    EventDataDescCreate(&amp;eventData[WPC_ARGS_CONVERSATIONINITEVENT_REASON],
        (const PVOID)&amp;dwReason, sizeof(dwReason));

    EventDataDescCreate(&amp;eventData[WPC_ARGS_CONVERSATIONINITEVENT_RECIPCOUNT],
        (const PVOID)&amp;dwRecipCount, sizeof(dwRecipCount));

    EventDataDescCreate(&amp;eventData[WPC_ARGS_CONVERSATIONINITEVENT_RECIPIENT],
        (const PVOID)pcszRecipient, (ULONG)BYTELEN(pcszRecipient));


    ULONG lRet = EventWrite(hWpc, &amp;WPCEVENT_IM_INVITATION, ARRAYSIZE(eventData), eventData);

    // Unregister
    EventUnregister(hWpc);
}
```



### Custom Logging

For an application to extend the events logged outside the set of predefined events or the one custom type, you will need to define a provider for that in the application manifest. The WPC default channel can then be imported and application-defined events can then be logged.

### Logging Rights

The WPC logging channel is controlled by [*access control list*](https://msdn.microsoft.com/library/windows/desktop/ms721532#-security-access-control-list-gly) (ACL) to provide full access for administrators only. Non-administrator accounts may write to the channel but have no read or delete access. Access to the channel is by using the ETW API.

### Parental Controls Logging Provider Details

The WPC provider is named Microsoft.com/Windows/ParentalControls with GUID {01090065-B467-4503-9B28-533766761087}. The default local logging channel is Microsoft.com/Windows/ParentalControls/LocalEvents.

Log files are stored in the Windows\\System32\\Wpc\\Logs folder.

### Notification of Impending Time Limits Logout

The Parental Controls system will fire a warning event at 15 minutes and again at 1 minute before logout of a controlled user based on time restrictions. Applications can subscribe to these events, especially when they are running in DirectX full-screen mode where standard Windows notifications are not displayed. Sample code is provided that shows how to subscribe to the events, register a callback function, and receive the events.

## Related topics

<dl> <dt>

[Parental Controls Extensibility Features Overview](parental-controls-extensibility-features-overview.md)
</dt> <dt>

[**EVENT\_DATA\_DESCRIPTOR**](https://msdn.microsoft.com/library/windows/desktop/aa363753)
</dt> <dt>

[**EventDataDescCreate**](https://msdn.microsoft.com/library/windows/desktop/aa363723)
</dt> <dt>

[**WPC\_ARGS\_CONVERSATIONINITEVENT**](/windows/win32/Wpcevent/ne-wpcevent-tagwpc_args_conversationinitevent?branch=master)
</dt> </dl>

 

 


