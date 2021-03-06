---
title: RTF_WCSINFO
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 0c94501e-0ec7-e836-33a7-adcf5a61b375
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 2dd9f002401f8de52a9ad187b7e5850d47caf8a7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22587386"
---
# <a name="rtfwcsinfo"></a>RTF_WCSINFO

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Esta estructura permite especificar información para descomprimir el cuerpo de un mensaje en el formato comprimido de texto enriquecido (RTF) y, opcionalmente, devuelva la secuencia de cuerpo en su formato nativo.
  
## <a name="quick-info"></a>Información rápida

```cpp
typedef struct { 
    ULONG size; 
    ULONG ulFlags; 
    ULONG ulInCodePage; 
    ULONG ulOutCodePage; 
} RTF_WCSINFO;

```

## <a name="members"></a>Members

 _size_
  
> El tamaño de la estructura **RTF_WCSINFO** en número de bytes. 
    
 _ulFlags_
  
> Esto es la máscara de bits de indicadores de opción para la función [WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md) . Los indicadores de opción compatibles son: 
    
|||
|:-----|:-----|
|MAPI_MODIFY  <br/> |Esto indica si el cliente intenta crear una interfaz de la secuencia ajustada que se devuelve.  <br/> |
|STORE_UNCOMPRESSED_RTF  <br/> |Esto indica si se supone que el RTF descomprimido se escriben en la secuencia que señala el puntero _lpCompressedRTFStream_ de la función [WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md) .  <br/> |
|MAPI_NATIVE_BODY  <br/> |Esto indica si la secuencia descomprimida también se convierte en el cuerpo nativo antes de devolver la secuencia. Esta marca no se puede combinar con la marca **MAPI_MODIFY** .  <br/> |
   
 _ulInCodePage_
  
> Éste es el valor de la página de código del mensaje. Normalmente, este valor se obtiene de la [Propiedad canónico PidTagInternetCodepage](pidtaginternetcodepage-canonical-property.md) en el mensaje. Este valor sólo se utiliza cuando se pasa el indicador **MAPI_NATIVE_BODY** en _ulFlags_. De lo contrario, se omite este valor.
    
 _ulOutCodePage_
  
> Éste es el valor de la página de código de la secuencia devuelta descomprimido que desee. Si se establece en un valor distinto de cero, la función [WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md) convierte la secuencia a la página de código especificado. Si se establece en un valor de cero, MAPI decide qué página de códigos para usar. Este valor solo se usa cuando se pasa el indicador **MAPI_NATIVE_BODY** en _ulFlags_y el formato del cuerpo no es RTF. De lo contrario, se omite este valor.
    
## <a name="see-also"></a>Recursos adicionales



[WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md)

