---
title: Recuperar el cuerpo del mensaje en formato RTF comprimido y convertir en su formato nativo
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 9408da71-4abf-60cf-5412-58c5ceeb2205
description: '�ltima modificaci�n: lunes, 25 de junio de 2012'
ms.openlocfilehash: c07eebf11b4e61d91f492206498558154e6ddef3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2018
ms.locfileid: "19817013"
---
# <a name="retrieve-body-of-message-in-compressed-rtf-and-convert-to-its-native-format"></a>Recuperar el cuerpo del mensaje en formato RTF comprimido y convertir en su formato nativo

**Hace referencia a**: Outlook 
  
En este ejemplo de código en Microsoft C++ se muestra cómo usar la función exportada de Microsoft Outlook 2010 o Microsoft Outlook 2013 [WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md) para obtener acceso al cuerpo de un mensaje que se encapsula en RTF comprimido y obtener el cuerpo en su formato nativo. 
  
```cpp
//These are definitions for the WrapCompressedRTFStreamEx function. 
typedef HRESULT (STDMETHODCALLTYPE WRAPCOMPRESSEDRTFSTREAMEX) ( 
    LPSTREAM lpCompressedRTFStream, CONST RTF_WCSINFO * pWCSInfo, LPSTREAM * lppUncompressedRTFStream, RTF_WCSRETINFO * pRetInfo); 
typedef WRAPCOMPRESSEDRTFSTREAMEX *LPWRAPCOMPRESSEDRTFSTREAMEX; 
 
HRESULT TestWrapCompressedRTFStreamEx(LPMESSAGE lpMsg) 
{ 
    HRESULT         hRes = S_OK; 
    LPSTREAM        lpCompressed = NULL; 
    LPSTREAM        lpUncompressed = NULL; 
    char            szBody[1024] = {0}; 
    ULONG           ulRead = 0; 
    RTF_WCSINFO     wcsinfo = {0}; 
    RTF_WCSRETINFO  retinfo = {0}; 
    LPSPropValue    lpPropCPID = NULL; 
 
    retinfo.size = sizeof(RTF_WCSRETINFO); 
 
    wcsinfo.size = sizeof(RTF_WCSINFO); 
    wcsinfo.ulFlags = MAPI_NATIVE_BODY; 
    wcsinfo.ulOutCodePage = 0; 
 
    // Retrieve the value of the Internet code page. 
    // Pass this value to the WrapCompressedRTFStreamEx function. 
    // If the property is not found, the default is 0. 
    if(SUCCEEDED(hRes = HrGetOneProp(lpMsg, PR_INTERNET_CPID, &lpPropCPID))) 
    { 
        wcsinfo.ulInCodePage = lpPropCPID->Value.l; 
    } 
 
    // Open the compressed RTF stream. 
    if(SUCCEEDED(hRes = lpMsg->OpenProperty(PR_RTF_COMPRESSED, 
                                         &IID_IStream, 
                                         STGM_READ | STGM_DIRECT, 
                                         0, 
                                         (LPUNKNOWN*)&lpCompressed))) 
    { 
 
        // Notice that the WrapCompressedRTFStreamEx function has been loaded 
        // by using the GetProcAddress function into pfnWrapEx. 
 
        // Call the WrapCompressedRTFStreamEx function. 
        if(SUCCEEDED(hRes = pfnWrapEx(lpCompressed, 
                                   &wcsinfo, 
                                   &lpUncompressed, 
                                   &retinfo))) 
        { 
 
            printf("Body's native type is: "); 
 
            // Check what the native body type is. 
            switch(retinfo.ulStreamFlags) 
            { 
            case MAPI_NATIVE_BODY_TYPE_RTF: 
                printf("MAPI_NATIVE_BODY_TYPE_RTF\n"); 
                break; 
            case MAPI_NATIVE_BODY_TYPE_HTML: 
                printf("MAPI_NATIVE_BODY_TYPE_HTML\n"); 
                break; 
            case MAPI_NATIVE_BODY_TYPE_PLAINTEXT: 
                printf("MAPI_NATIVE_BODY_TYPE_PLAINTEXT\n"); 
                break; 
            default: 
                printf("UNKNOWN\n"); 
            } 
 
            // Read the first 1,000 characters out of the stream. 
            if(SUCCEEDED(hRes = lpUncompressed->Read(szBody, 1024, &ulRead))) 
            { 
                printf("First %d characters of the native body stream:\n%s\n", ulRead, szBody); 
            } 
        } 
    } 
 
    MAPIFreeBuffer(lpPropCPID); 
    if(lpUncompressed)lpUncompressed->Release(); 
    if(lpCompressed)lpCompressed->Release(); 
 
    return hRes; 
} 

```

