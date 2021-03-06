---
title: Propiedad canónica PidTagReplyRecipientEntries
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReplyRecipientEntries
api_type:
- COM
ms.assetid: a903fd22-a3f2-464f-99b0-c087e211b124
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 000132f052abb666ae844ec7d21b59c85ab43613
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25400967"
---
# <a name="pidtagreplyrecipiententries-canonical-property"></a>Propiedad canónica PidTagReplyRecipientEntries

  
  
**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
Contiene una matriz de tamaño de los identificadores de entrada para los destinatarios que van a obtener una respuesta.
  
|||
|:-----|:-----|
|Propiedades asociadas:  <br/> |PR_REPLY_RECIPIENT_ENTRIES  <br/> |
|Identificador:  <br/> |0x004F  <br/> |
|Tipo de datos:  <br/> |PT_BINARY  <br/> |
|Área:  <br/> |Sobres MAPI  <br/> |
   
## <a name="remarks"></a>Comentarios

Esta propiedad contiene una estructura [FLATENTRYLIST](flatentrylist.md) y no es una propiedad multivalor. 
  
Cuando esta propiedad no está presente, se envía una respuesta sólo para el usuario identificado por la propiedad **PR_SENDER_ENTRYID** ([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md)). Cuando se definen propiedades **PR_REPLY_RECIPIENT_NAMES** ([PidTagReplyRecipientNames](pidtagreplyrecipientnames-canonical-property.md)) y esto, la respuesta se envía a todos los destinatarios identificados por estas dos propiedades. Un proveedor de transporte usa estas propiedades para invalidar la lógica de respuesta habitual.
  
Si se establece esta propiedad o la propiedad **PR_REPLY_RECIPIENT_NAMES** , también debe establecerse la propiedad de otra. Estas propiedades deben contener el mismo número de destinatarios y que deben contienen en el mismo orden. Error al tener en cuenta estos requisitos puede generar resultados impredecibles. 
  
## <a name="related-resources"></a>Recursos relacionados

### <a name="protocol-specifications"></a>Especificaciones de protocolo

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Proporciona referencias a las especificaciones del protocolo de Exchange Server relacionadas.
    
[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> Especifica las propiedades y operaciones que se permiten en mensajes de correo electrónico.
    
[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)
  
> Convierte de las convenciones de correo electrónico estándar de Internet a objetos de mensaje.
    
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

