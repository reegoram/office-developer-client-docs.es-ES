---
title: Propiedad canónica PidLidTaskStartDate
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskStartDate
api_type:
- COM
ms.assetid: fe87eb3d-21d1-45bb-b848-e141ce1be6a0
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 3bc475292e47a9ad8dd9565e17640ef95e7b3c76
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25383530"
---
# <a name="pidlidtaskstartdate-canonical-property"></a>Propiedad canónica PidLidTaskStartDate

  
  
**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
La fecha cuando el usuario espera para comenzar la tarea.
  
|||
|:-----|:-----|
|Propiedades asociadas:  <br/> |dispidTaskStartDate  <br/> |
|Conjunto de propiedades:  <br/> |PSETID_Task  <br/> |
|Identificador de tipo Long (LID):  <br/> |0x00008104  <br/> |
|Tipo de datos:  <br/> |PT_SYSTIME  <br/> |
|Área:  <br/> |Task  <br/> |
   
## <a name="remarks"></a>Comentarios

Si el valor de esta propiedad se deja sin establecer, la tarea no tiene una fecha de inicio. Un valor de "0x5AE980E0" (1,525,252,320) también significa que la tarea no tiene una fecha de inicio. Si la tarea tiene una fecha de inicio, el valor debe tener un componente de hora de la medianoche, y también se deben establecer las propiedades de **dispidCommonStart** ([PidLidCommonStart](pidlidcommonstart-canonical-property.md)) y **dispidTaskDueDate** ([PidLidTaskDueDate](pidlidtaskduedate-canonical-property.md)).
  
Esta propiedad se comparte con la especificación de protocolo informativo marcar y especificación del protocolo Task-Related objeto que se encuentra en [[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx).
  
## <a name="related-resources"></a>Recursos relacionados

### <a name="protocol-specifications"></a>Especificaciones de protocolo

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Proporciona definiciones de conjunto de propiedades y las referencias a las especificaciones del protocolo de Exchange Server relacionadas.
    
[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)
  
> Especifica las propiedades y operaciones que se permiten en los contactos y las listas de distribución personal.
    
### <a name="header-files"></a>Archivos de encabezado

Mapidefs.h
  
> Proporciona definiciones de tipo de datos.
    
## <a name="see-also"></a>Vea también



[Propiedad can�nico de PidLidTaskDueDate](pidlidtaskduedate-canonical-property.md)
  
[Propiedad can�nico de PidLidCommonStart](pidlidcommonstart-canonical-property.md)


[Propiedades MAPI](mapi-properties.md)
  
[Propiedades MAPI canónicas](mapi-canonical-properties.md)
  
[Asignar nombres de propiedad canónicos a nombres MAPI](mapping-canonical-property-names-to-mapi-names.md)
  
[Asignar nombres MAPI a los nombres de propiedad canónico](mapping-mapi-names-to-canonical-property-names.md)

