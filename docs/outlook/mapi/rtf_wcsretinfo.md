---
title: RTF_WCSRETINFO
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 62561d8d-33cb-e482-7fa0-132afe2b464a
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: bf8cf115c6188b5058717437c470e11797ff5b9a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564965"
---
# <a name="rtfwcsretinfo"></a>RTF_WCSRETINFO

**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Esta estructura proporciona información acerca de una secuencia en formato nativo devuelto desde descomprimir el cuerpo de un mensaje que se encapsula en el formato comprimido de texto enriquecido (RTF).
  
## <a name="quick-info"></a>Información rápida

```cpp
typedef struct { 
    ULONG size;    
    ULONG ulStreamFlags; 
} RTF_WCSRETINFO;
```

## <a name="members"></a>Members

_size_
  
> El tamaño de la estructura **RTF_WCSRETINFO** en número de bytes. 
    
_ulStreamFlags_
  
> Esto es un valor que indica el formato del cuerpo nativo. Este valor sólo es válida si el indicador **MAPI_NATIVE_BODY** se pasa en el parámetro _ulFlags_ de la estructura [RTF_WCSINFO](rtf_wcsinfo.md) que se pasa a la función [WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md) . Esto puede ser uno de los siguientes valores: 
    
|||
|:-----|:-----|
|MAPI_NATIVE_BODY_TYPE_RTF  <br/> |Este valor solo se usa si _ulFlags_ incluye la marca **MAPI_NATIVE_BODY** , y el cuerpo es RTF.  <br/> |
|MAPI_NATIVE_BODY_TYPE_PLAIN_TEXT  <br/> |Este valor solo se usa si _ulFlags_ incluye la marca **MAPI_NATIVE_BODY** , y el cuerpo tiene formato de texto sin formato.  <br/> |
|MAPI_NATIVE_BODY_TYPE_HTML  <br/> |Este valor solo se usa si _ulFlags_ incluye la marca **MAPI_NATIVE_BODY** , y el cuerpo tiene formato de lenguaje de marcado de hipertexto (HTML).  <br/> |
   
## <a name="see-also"></a>Recursos adicionales

- [WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md)

