---
title: IConverterSessionSetSaveFormat
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IConverterSession.SetCharSet
api_type:
- COM
ms.assetid: e5308a94-5191-2109-a881-b4f4a7ff1c61
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: f1a4834fc600cc93eeb7fc96563723326c7f2169
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2018
ms.locfileid: "19817176"
---
# <a name="iconvertersessionsetsaveformat"></a>IConverterSession::SetSaveFormat

**Hace referencia a**: Outlook 
  
Establece el formato en el que el convertidor devolverá una secuencia MIME en [IConverterSession::MAPIToMIMEStm](iconvertersession-mapitomimestm.md).
  
```cpp
HRESULT IConverterSession::SetSaveFormat ( 
     MIMESAVETYPE mstSaveFormat 
);
```

## <a name="parameters"></a>Parámetros

_mstSaveFormat_
  
> [entrada] Dar formato a la operación de guardar que se usará para una secuencia MIME. Para obtener más información, vea el tipo de enumeración [MIMESAVETYPE](http://msdn.microsoft.com/en-us/library/ms715128%28VS.85%29.aspx).
    
  - **SAVE_RFC1521**: uso MIME, que es el valor predeterminado.      
  - **SAVE_RFC822**: utilizar uuencode.
    
## <a name="return-values"></a>Valores devueltos

S_OK
  
> La llamada tuvo éxito.
    
## <a name="mfcmapi-reference"></a>Referencia MFCMAPI

MFCMAPI c�digo de ejemplo, vea la siguiente tabla.
  
|**Archivo**|**Funci�n**|**Comentario**|
|:-----|:-----|:-----|
|MapiMime.cpp  <br/> |ImportEMLToIMessage  <br/> |MFCMAPI utiliza MimeToMAPI para convertir un archivo EML en un mensaje MAPI.  <br/> |
|MapiMime.cpp  <br/> |ExportIMessageToEML  <br/> |MFCMAPI utiliza MAPIToMIMEStm para convertir un mensaje MAPI en un archivo EML.  <br/> |
   
## <a name="see-also"></a>Vea también

- [IConverterSession : IUnknown](iconvertersessioniunknown.md)
- [IConverterSession::MAPIToMIMEStm](iconvertersession-mapitomimestm.md)
- [IConverterSession::MIMEToMAPI](iconvertersession-mimetomapi.md)
- [IConverterSession::SetAdrBook](iconvertersession-setadrbook.md)
- [IConverterSession::SetCharSet](iconvertersession-setcharset.md)
- [IConverterSession::SetEncoding](iconvertersession-setencoding.md)
- [IConverterSession::SetTextWrapping](iconvertersession-settextwrapping.md)
- [Constantes MAPI](mapi-constants.md)
