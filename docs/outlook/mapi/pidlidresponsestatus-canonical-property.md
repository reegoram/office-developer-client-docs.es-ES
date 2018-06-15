---
title: Propiedad canónico PidLidResponseStatus
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidResponseStatus
api_type:
- COM
ms.assetid: e56142fd-204b-497e-83b9-59f9acda6cb4
description: '�ltima modificaci�n: lunes, 9 de marzo de 2015'
ms.openlocfilehash: 0bfa3a01613c49b122e92e4ac281e5b20b5f07ae
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2018
ms.locfileid: "19818893"
---
# <a name="pidlidresponsestatus-canonical-property"></a>Propiedad canónico PidLidResponseStatus

  
  
**Se aplica a**: Outlook 
  
Especifica el estado de respuesta de un asistente.
  
|||
|:-----|:-----|
|Propiedades asociadas:  <br/> |dispidResponseStatus  <br/> |
|Conjunto de propiedades:  <br/> |PSETID_Appointment  <br/> |
|Identificador de tipo Long (LID):  <br/> |0x00008218  <br/> |
|Tipo de datos:  <br/> |PT_LONG  <br/> |
|Área:  <br/> |Reuniones  <br/> |
   
## <a name="remarks"></a>Notas

El estado de la respuesta debe ser uno de los valores en la tabla siguiente.
  
|**Estado de la respuesta**|**Valor**|**Descripción**|
|:-----|:-----|:-----|
|respNone  <br/> |0x00000000  <br/> |No hay respuesta es necesaria para este objeto. Este es el caso de objetos de citas y objetos de respuesta de la reunión.  <br/> |
|respOrganized  <br/> |0x00000001  <br/> |Al que pertenece el organizador de esta reunión.  <br/> |
|respTentative  <br/> |0x00000002  <br/> |Este valor en la reunión del asistente indica que el asistente ha aceptado provisionalmente la convocatoria de reunión.  <br/> |
|respAccepted  <br/> |0 x 00000003  <br/> |Este valor en t de reunión del asistente indica que el asistente ha aceptado la convocatoria de reunión.  <br/> |
|respDeclined  <br/> |0 x 00000004  <br/> |Este valor en la reunión del asistente indica que el asistente ha rechazado la convocatoria de reunión.  <br/> |
|respNotResponded  <br/> |0 x 00000005  <br/> |Este valor en la reunión del asistente indica que el asistente no ha respondido. Este valor se encuentra en la convocatoria de reunión, la actualización de la reunión y la cancelación de la reunión.  <br/> |
   
## <a name="related-resources"></a>Recursos relacionados

### <a name="protocol-specifications"></a>Especificaciones de protocolo

[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Proporciona definiciones de conjunto de propiedades y las referencias a las especificaciones del protocolo de Exchange Server relacionadas.
    
[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> Especifica las propiedades y operaciones para una cita, convocatoria de reunión y mensajes de respuesta.
    
### <a name="header-files"></a>Archivos de encabezado

Mapidefs.h
  
> Proporciona definiciones de tipo de datos.
    
## <a name="see-also"></a>Ver también



[Propiedades MAPI](mapi-properties.md)
  
[Propiedades MAPI canónicas](mapi-canonical-properties.md)
  
[Asignación de nombres de propiedad canónico a nombres de MAPI](mapping-canonical-property-names-to-mapi-names.md)
  
[Asignación de nombres MAPI para nombres canónicos (propiedad)](mapping-mapi-names-to-canonical-property-names.md)
