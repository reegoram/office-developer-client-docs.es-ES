---
title: Propiedad canónica PidLidLogDuration
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidLogDocumentSaved
api_type:
- COM
ms.assetid: 012a3f6e-fd16-4dc9-845d-2bf4cebeaa42
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 6f25c1a72882f9236d56532b7259f51512734945
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25400345"
---
# <a name="pidlidlogduration-canonical-property"></a>Propiedad canónica PidLidLogDuration

  
  
**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
Representa la duración, en minutos, de un mensaje de diario.
  
|||
|:-----|:-----|
|Propiedades asociadas:  <br/> |dispidLogDuration  <br/> |
|Conjunto de propiedades:  <br/> |PSETID_Log  <br/> |
|Identificador de tipo Long (LID):  <br/> |0x00008707  <br/> |
|Tipo de datos:  <br/> |PT_LONG  <br/> |
|Área:  <br/> |Journal  <br/> |
   
## <a name="remarks"></a>Comentarios

La duración, en minutos, de la actividad que debe ser la diferencia entre las propiedades de **dispidLogStart** ([PidLidLogStart](pidlidlogstart-canonical-property.md)) y **dispidLogEnd** ([PidLidLogEnd](pidlidlogend-canonical-property.md)).
  
## <a name="related-resources"></a>Recursos relacionados

### <a name="protocol-specifications"></a>Especificaciones de protocolo

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Proporciona definiciones de conjunto de propiedades y las referencias a las especificaciones del protocolo de Exchange Server relacionadas.
    
[[MS-OXOJRNL]](https://msdn.microsoft.com/library/2aa04fd2-0f36-4ce4-9178-c0fc70aa8d43%28Office.15%29.aspx)
  
> Especifica las propiedades y operaciones que se permiten para diarios.
    
### <a name="header-files"></a>Archivos de encabezado

Mapidefs.h
  
> Proporciona definiciones de tipo de datos.
    
## <a name="see-also"></a>Vea también



[Propiedades MAPI](mapi-properties.md)
  
[Propiedades MAPI canónicas](mapi-canonical-properties.md)
  
[Asignar nombres de propiedad canónicos a nombres MAPI](mapping-canonical-property-names-to-mapi-names.md)
  
[Asignar nombres MAPI a los nombres de propiedad canónico](mapping-mapi-names-to-canonical-property-names.md)

