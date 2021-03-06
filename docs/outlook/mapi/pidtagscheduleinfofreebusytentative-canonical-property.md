---
title: Propiedad canónica PidTagScheduleInfoFreeBusyTentative
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagScheduleInfoFreeBusyTentative
api_type:
- COM
ms.assetid: 28453d29-30c5-405b-84d2-5bb5f281756c
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 18bc41d9038113b5b813f1cfd02d90b8e982703c
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25385119"
---
# <a name="pidtagscheduleinfofreebusytentative-canonical-property"></a>Propiedad canónica PidTagScheduleInfoFreeBusyTentative

  
  
**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
Contiene los bloques de veces para que el estado de disponibilidad es provisional.
  
|||
|:-----|:-----|
|Propiedades asociadas:  <br/> |PR_SCHDINFO_FREEBUSY_TENTATIVE  <br/> |
|Identificador:  <br/> |0x6852  <br/> |
|Tipo de datos:  <br/> |PT_MV_BINARY  <br/> |
|Área:  <br/> |Libre/ocupado  <br/> |
   
## <a name="remarks"></a>Comentarios

Esta propiedad tiene tantos valores como el número de valores en **PR_SCHDINFO_MONTHS_TENTATIVE** ([PidTagScheduleInfoMonthsTentative](pidtagscheduleinfomonthstentative-canonical-property.md)). Cada valor binario representa un mes y se corresponde con el valor en el mismo índice en **PR_SCHDINFO_MONTHS_TENTATIVE**. Los valores binarios se ordenan en el mismo orden que los valores de **PR_SCHDINFO_MONTHS_TENTATIVE**.
  
Cada valor binario tiene uno o más bloques de 4 bytes y cada uno de ellos contiene la hora de inicio en los dos primeros bytes y la hora de finalización de la segunda de dos bytes en formato "little-endian". La hora de inicio es el número de minutos entre la medianoche de la hora Universal coordinada (UTC) del primer día del mes y la hora de inicio del evento en UTC. La hora de finalización es el número de minutos entre la medianoche UTC del primer día del mes y la hora de finalización del evento en UTC. Los bloques de 4 bytes se ordenan en orden ascendente.
  
Bloques consecutivos o superposición de tiempo se combinan en un bloque con la hora de inicio como la hora de inicio de la primer bloque y la hora de finalización como la hora de finalización del último bloque. Si un evento es repartido por varios meses o años, el evento se divide en varios bloques, uno para cada mes. Si no hay ningún evento provisional en el intervalo de publicación, a continuación, esta propiedad y **PR_SCHDINFO_MONTHS_TENTATIVE** no se deben establecer o se deben eliminar si ya existen. De lo contrario, se debe establecer esta propiedad. 
  
## <a name="related-resources"></a>Recursos relacionados

### <a name="protocol-specifications"></a>Especificaciones de protocolo

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Proporciona referencias a las especificaciones del protocolo de Exchange Server relacionadas.
    
[[MS-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)
  
> Publica la disponibilidad de un usuario o recurso.
    
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

