---
title: Example Using SSPI Authentication Encoding with BITS
description: You can use Security Support Provider Interface (SSPI) Authentication and Background Intelligent Transfer Service (BITS) methods to get the credentials from a user, encode the credentials, and set the encoded credentials on a BITS transfer job.
ms.assetid: 5c8a6df7-0056-463e-8d73-1695dc75e023
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Example: Using SSPI Authentication Encoding with BITS

You can use Security Support Provider Interface (SSPI) Authentication and Background Intelligent Transfer Service (BITS) methods to get the credentials from a user, encode the credentials, and set the encoded credentials on a BITS transfer job. Encoding is required to convert credentials structure into strings that can be passed to a BITS transfer job.

For more information about SSPI authentication and methods, see [SSPI](http://go.microsoft.com/fwlink/p/?linkid=162382).

The following procedure prompts for credentials from the user by using the Negotiate security package. The program creates an authentication identity structure and populates the structure with the encoded strings that represent the user name, domain, and password of the user. Then the program creates a BITS download job and sets the encoded user name and password as the credentials for the job. The program frees the authentication identity structure after it is no longer needed.

This example uses the header and implementation defined in [Example: Common Classes](common-classes.md).

**To use SSPI authentication encoding with BITS transfer jobs**

1.  Initialize COM parameters by calling the CCoInitializer function. For more information about the CCoInitializer function, see [Example: Common Classes](common-classes.md).
2.  Get pointers for the [**IBackgroundCopyManager**](/windows/win32/Bits/nn-bits-ibackgroundcopymanager?branch=master), [**IBackgroundCopyJob**](/windows/win32/Bits/nn-bits-ibackgroundcopyjob?branch=master), [**IBackgroundCopyJob2**](/windows/win32/Bits1_5/nn-bits1_5-ibackgroundcopyjob2?branch=master) interfaces. This example uses the [CComPtr Class](http://go.microsoft.com/fwlink/p/?linkid=162393) to manage COM interface pointers.
3.  Create a [CREDUI\_INFO](http://go.microsoft.com/fwlink/p/?linkid=162383) structure that contains information for customizing the appearance of the dialog box for the [SspiPromptForCredentials Function]( http://go.microsoft.com/fwlink/p/?linkid=162384). Then prompt for credentials from the user. For more information, see the [SspiPromptForCredentials Function]( http://go.microsoft.com/fwlink/p/?linkid=162384).
4.  Encode credential structure as strings that can be passed to a BITS transfer job by using the [SspiEncodeAuthIdentityAsStrings]( http://go.microsoft.com/fwlink/p/?linkid=162385) function.
5.  Prepare a [**BG\_AUTH\_CREDENTIALS**](/windows/win32/Bits1_5/ns-bits1_5-__midl_ibackgroundcopyjob2_0005?branch=master) structure.
6.  Initialize COM process security by calling [CoInitializeSecurity](http://go.microsoft.com/fwlink/p/?linkid=162390). BITS requires at least the IMPERSONATE level of impersonation. BITS fails with **E\_ACCESSDENIED** if the correct impersonation level is not set.
7.  Obtain the initial locator to BITS by calling the [CoCreateInstance]( http://go.microsoft.com/fwlink/p/?linkid=162386) function.
8.  Create a BITS transfer job by calling the [**IBackgroundCopyManager::CreateJob**](/windows/win32/Bits/nf-bits-ibackgroundcopymanager-createjob?branch=master) method.
9.  Get the identifier for the [**IBackgroundCopyJob2**](/windows/win32/Bits1_5/nn-bits1_5-ibackgroundcopyjob2?branch=master) interface, and call the **IBackgroundCopyJob::QueryInterface** method.
10. Populate the [**BG\_AUTH\_CREDENTIALS**](/windows/win32/Bits1_5/ns-bits1_5-__midl_ibackgroundcopyjob2_0005?branch=master) structure with the encoded user name and password strings, and set the authentication scheme to Negotiate (**BG\_AUTH\_SCHEME\_NEGOTIATE**).
11. Use the [**IBackgroundCopyJob2**](/windows/win32/Bits1_5/nn-bits1_5-ibackgroundcopyjob2?branch=master) pointer to make requests to BITS. This program uses the [**IBackgroundCopyJob2::SetCredentials**](/windows/win32/Bits1_5/nf-bits1_5-ibackgroundcopyjob2-setcredentials?branch=master) method to set the credentials for the BITS transfer job.
12. Add files, modify properties, or resume the BITS transfer job.
13. After the BITS transfer job is complete, remove the job from the queue by calling [**IBackgroundCopyJob::Complete**](/windows/win32/Bits/nf-bits-ibackgroundcopyjob-complete?branch=master).
14. Finally, free the authentication identity structure by calling the [SspiFreeAuthIdentity](http://go.microsoft.com/fwlink/p/?linkid=162387) function.

The following code example demonstrates how to use SSPI Authentication Encoding with BITS transfer jobs.


```C++
#define SECURITY_WIN32
#define _SEC_WINNT_AUTH_TYPES

#include <windows.h>
#include <ntsecapi.h>
#include <bits.h>
#include <sspi.h>
#include <wincred.h>
#include <iostream>
#include <atlbase.h>
#include "CommonCode.h"

void PromptForCredentials(PWSTR pwTargetName)
{
    HRESULT hr;
    
    // If CoInitializeEx fails, the exception is unhandled and the program terminates
    CCoInitializer coInitializer(COINIT_APARTMENTTHREADED);
    
    CComPtr<IBackgroundCopyManager> pQueueMgr;
    CComPtr<IBackgroundCopyJob> pJob;
    CComPtr<IBackgroundCopyJob2> pJob2;

    PSEC_WINNT_AUTH_IDENTITY_OPAQUE pAuthIdentityEx2 = NULL;
    DWORD dwFlags = 0;
    BOOL fSave = FALSE;
    BOOL bReturn = TRUE;

    CREDUI_INFO creduiInfo = { 0 };
    creduiInfo.cbSize = sizeof(creduiInfo);
    // Change the message text and caption to the actual text for your dialog.
    creduiInfo.pszMessageText = pwTargetName;
    creduiInfo.pszCaptionText = L"SSPIPFC title for the dialog box";

    try {
        // Prompt for credentials from user using Negotiate security package.
        DWORD dwRet = SspiPromptForCredentials(
            pwTargetName,
            &amp;creduiInfo,
            0,
            L"Negotiate", 
            NULL,
            &amp;pAuthIdentityEx2,
            &amp;fSave,
            dwFlags
            );

        if (SEC_E_OK != dwRet) 
        {
            // Prompt for credentials failed.
            throw MyException(dwRet, L"SspiPromptForCredentials");
        }

        if (NULL != pAuthIdentityEx2) 
        {
            GUID guidJob;
            BG_AUTH_CREDENTIALS authCreds;

            PCWSTR pwUserName = NULL;
            PCWSTR pwDomainName = NULL;
            PCWSTR pwPassword = NULL;

            // Encode credential structure as strings that can
            // be passed to a BITS job.
            SECURITY_STATUS secStatus = SspiEncodeAuthIdentityAsStrings(
                pAuthIdentityEx2,
                &amp;pwUserName,
                &amp;pwDomainName,
                &amp;pwPassword
                );

            if(SEC_E_OK != secStatus) 
            {
                // Encode authentication identity as strings.
                throw MyException(secStatus, L"SspiEncodeAuthIdentityAsStrings");   
            }

            // Show the encoded user name and domain name.
            wprintf(
                L"User Name: %s\nDomain Name: %s",
                pwUserName,
                pwDomainName
                );

            //The impersonation level must be at least RPC_C_IMP_LEVEL_IMPERSONATE.
            HRESULT hr = CoInitializeSecurity(
                NULL,
                -1,
                NULL,
                NULL,
                RPC_C_AUTHN_LEVEL_CONNECT,
                RPC_C_IMP_LEVEL_IMPERSONATE,
                NULL,
                EOAC_DYNAMIC_CLOAKING,
                0
                );
            
            if (FAILED(hr))
            {
                throw MyException(hr, L"CoInitializeSecurity");
            }

            // Connect to BITS.
            hr = CoCreateInstance(__uuidof(BackgroundCopyManager), NULL,
                CLSCTX_LOCAL_SERVER,
                __uuidof(IBackgroundCopyManager),
                (void**) &amp;pQueueMgr);

            if (FAILED(hr))
            {
                // Failed to connect.
                throw MyException(hr, L"CoCreateInstance");
            }

            // Create a job.
            hr = pQueueMgr->CreateJob(
                L"EncodeSample", 
                BG_JOB_TYPE_DOWNLOAD, 
                &amp;guidJob, 
                &amp;pJob
                );

            if(FAILED(hr))
            {   
                // Failed to create a BITS job.
                throw MyException(hr, L"CreateJob");
            }

            // Get IBackgroundCopyJob2 interface.
            hr = pJob->QueryInterface(__uuidof(IBackgroundCopyJob2), (void**)&amp;pJob2);
            if (FAILED(hr)) 
            {
                // Failed to get a reference to the IBackgroundCopyJob2 interface.
                throw MyException(hr, L"QueryInterface(IBackgroundCopyJob2)");
            }

            // Create a BITS authentication structure from the encoded strings.
            authCreds.Target = BG_AUTH_TARGET_SERVER;
            authCreds.Scheme = BG_AUTH_SCHEME_NEGOTIATE;
            authCreds.Credentials.Basic.UserName = (LPWSTR)pwUserName;
            authCreds.Credentials.Basic.Password = (LPWSTR)pwPassword;

            // Set the credentials for the job.
            hr = pJob2->SetCredentials(&amp;authCreds);
            if (FAILED(hr)) 
            {
                // Failed to set credentials.
                throw MyException(hr, L"SetCredentials");
            }

            // Modify the job's property values.
            // Add files to the job.
            // Activate (resume) the job in the transfer queue.

            // Remove the job from the transfer queue.
            hr = pJob->Complete();
            if (FAILED(hr)) 
            {
                // Failed to complete the job.
                throw MyException(hr, L"Complete");
            }
        }
    }
    catch(std::bad_alloc &amp;)
    {
        wprintf(L"Memory allocation failed");
        if (pJob != NULL)
        {
            pJob->Cancel();
        }
    }
    catch(MyException &amp;ex)
    {
        wprintf(L"Error %x occurred during operation", ex.Error);
        if (pJob != NULL)
        {
            pJob->Cancel();
        }
    }

    // Free the auth identity structure.
    if (NULL != pAuthIdentityEx2)
    {
        SspiFreeAuthIdentity(pAuthIdentityEx2);
        pAuthIdentityEx2 = NULL;
    }

    return;
}

void _cdecl _tmain(int argc, LPWSTR* argv)
{
    PromptForCredentials(L"Target");
}
```



## Related topics

<dl> <dt>

[SSPI](http://go.microsoft.com/fwlink/p/?linkid=162382)
</dt> <dt>

[**IBackgroundCopyManager**](/windows/win32/Bits/nn-bits-ibackgroundcopymanager?branch=master)
</dt> <dt>

[**IBackgroundCopyJob**](/windows/win32/Bits/nn-bits-ibackgroundcopyjob?branch=master)
</dt> <dt>

[**IBackgroundCopyJob2**](/windows/win32/Bits1_5/nn-bits1_5-ibackgroundcopyjob2?branch=master)
</dt> <dt>

[Example: Common Classes](common-classes.md)
</dt> </dl>

 

 



