---
title: Propiedad canónica PidLidAppointmentEndWhole
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentEndWhole
api_type:
- COM
ms.assetid: f6fd33d6-04fb-4801-a004-fb80a14ca79d
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: eaff90de919c1bdc04983bce32a2aa808ae56013
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25389613"
---
# <a name="pidlidappointmentendwhole-canonical-property"></a>Propiedad canónica PidLidAppointmentEndWhole

  
  
**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
Representa la fecha y hora en que finaliza una cita.
  
|||
|:-----|:-----|
|Propiedades asociadas:  <br/> |dispidApptEndWhole  <br/> |
|Conjunto de propiedades:  <br/> |PSETID_Appointment  <br/> |
|Identificador de tipo Long (LID):  <br/> |0x0000820E  <br/> |
|Tipo de datos:  <br/> |PT_SYSTIME  <br/> |
|Área:  <br/> |Calendario  <br/> |
   
## <a name="remarks"></a>Comentarios

Esta propiedad corresponde a la propiedad **dispidApptEndWhole** de la cita en el modelo de objetos de Microsoft Office Outlook. 
  
Especifica la fecha de finalización y la hora para el evento; debe ser en hora Universal coordinada (UTC) y debe ser mayor que el valor de la propiedad **dispidApptStartWhole** ([PidLidAppointmentStartWhole](pidlidappointmentstartwhole-canonical-property.md)). Para una serie periódica, la propiedad **dispidApptEndWhole** es la fecha de finalización y la hora de la primera instancia según el patrón de periodicidad. 
  
## <a name="related-resources"></a>Recursos relacionados

### <a name="protocol-specifications"></a>Especificaciones de protocolo

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Proporciona definiciones de conjunto de propiedades y las referencias a las especificaciones del protocolo de Exchange Server relacionadas.
    
[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> Especifica las propiedades y operaciones para una cita, convocatoria de reunión y mensajes de respuesta.
    
### <a name="header-files"></a>Archivos de encabezado

Mapidefs.h
  
> Proporciona definiciones de tipo de datos.
    
## <a name="see-also"></a>Vea también



[Propiedades MAPI](mapi-properties.md)
  
[Propiedades MAPI canónicas](mapi-canonical-properties.md)
  
[Asignar nombres de propiedad canónicos a nombres MAPI](mapping-canonical-property-names-to-mapi-names.md)
  
[Asignar nombres MAPI a los nombres de propiedad canónico](mapping-mapi-names-to-canonical-property-names.md)

