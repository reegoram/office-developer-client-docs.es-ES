---
title: Propiedad canónica PidTagReportTag
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReportTag
api_type:
- COM
ms.assetid: 581bf372-8705-4617-aaa4-a1d761eb9b58
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 870fbf2228206253261124907d6bd420f95fb7c1
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25384846"
---
# <a name="pidtagreporttag-canonical-property"></a>Propiedad canónica PidTagReportTag

  
  
**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
Contiene un valor binario de etiqueta que se debe copiar el sistema de mensajería para cualquier informe generado para el mensaje. 
  
|||
|:-----|:-----|
|Propiedades asociadas:  <br/> |PR_REPORT_TAG  <br/> |
|Identificador:  <br/> |0x0031  <br/> |
|Tipo de datos:  <br/> |PT_BINARY  <br/> |
|Área:  <br/> |Sobres MAPI  <br/> |
   
## <a name="remarks"></a>Comentarios

Esta propiedad, al igual que la propiedad **PR_SUBJECT_IPM** ([PidTagSubjectMessageId](pidtagsubjectmessageid-canonical-property.md)), se usa para correlacionar un informe con el mensaje original. 
  
## <a name="related-resources"></a>Recursos relacionados

### <a name="protocol-specifications"></a>Especificaciones de protocolo

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Proporciona referencias a las especificaciones del protocolo de Exchange Server relacionadas.
    
[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> Especifica las propiedades y operaciones que se permiten en mensajes de correo electrónico.
    
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

