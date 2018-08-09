---
title: Propiedad canónica PidTagAttachFlags
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachFlags
api_type:
- HeaderDef
ms.assetid: 47e01131-f399-43cb-9815-aba69638c3fb
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: b934f9694061e17118be35e3fabeeff3bbc61a37
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2018
ms.locfileid: "19819221"
---
# <a name="pidtagattachflags-canonical-property"></a>Propiedad canónica PidTagAttachFlags

  
  
**Hace referencia a**: Outlook 
  
Contiene una máscara de bits de indicadores para los datos adjuntos. 
  
|||
|:-----|:-----|
|Propiedades asociadas:  <br/> |PR_ATTACH_FLAGS  <br/> |
|Identificador:  <br/> |0x3714  <br/> |
|Tipo de datos:  <br/> |PT_LONG  <br/> |
|Área:  <br/> |Datos adjuntos del mensaje  <br/> |
   
## <a name="remarks"></a>Comentarios

Esta propiedad se utiliza para compatibilidad con MHTML. 
  
La máscara de bits **PR_ATTACH_FLAGS** se pueden establecer uno o varios de los siguientes indicadores: 
  
ATT_INVISIBLE_IN_HTML 
  
> Indica que este archivo adjunto no está disponible para las aplicaciones de representación de HTML y se debe omitir en Extensiones multipropósito extensiones de correo Internet (MIME) de procesamiento. 
    
ATT_INVISIBLE_IN_RTF 
  
> Indica que este archivo adjunto no está disponible para las aplicaciones de representación en formato de texto enriquecido (RTF) y se debe omitir por MAPI.
    
Si la propiedad **PR_ATTACH_FLAGS** es cero o está ausente, los datos adjuntos están que va a procesar todas las aplicaciones. 
  
## <a name="related-resources"></a>Recursos relacionados

### <a name="protocol-specifications"></a>Especificaciones de protocolo

[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> Controla los objetos de mensaje y los datos adjuntos.
    
### <a name="header-files"></a>Archivos de encabezado

Mapidefs.h
  
> Proporciona definiciones de tipo de datos.
    
Mapitags.h
  
> Contiene las definiciones de las propiedades que aparecen como nombres alternativos.
    
## <a name="see-also"></a>Vea también



[Propiedades MAPI](mapi-properties.md)
  
[Propiedades MAPI canónicas](mapi-canonical-properties.md)
  
[Asignar nombres de propiedad canónicos a nombres MAPI](mapping-canonical-property-names-to-mapi-names.md)
  
[Asignar nombres MAPI a los nombres de propiedad canónico](mapping-mapi-names-to-canonical-property-names.md)
