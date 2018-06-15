---
title: Propiedad canónico PidLidTaskOrdinal
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskOrdinal
api_type:
- COM
ms.assetid: 1021860e-4c40-4c22-aa68-b568d046aaf7
description: '�ltima modificaci�n: lunes, 9 de marzo de 2015'
ms.openlocfilehash: 033bc038988373b11f3eac863a256717624999f9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2018
ms.locfileid: "19818979"
---
# <a name="pidlidtaskordinal-canonical-property"></a>Propiedad canónico PidLidTaskOrdinal

  
  
**Se aplica a**: Outlook 
  
Proporciona ayuda para las tareas de ordenación personalizadas.
  
|||
|:-----|:-----|
|Propiedades asociadas:  <br/> |dispidTaskOrdinal  <br/> |
|Conjunto de propiedades:  <br/> |PSETID_Task  <br/> |
|Identificador de tipo Long (LID):  <br/> |0x00008123  <br/> |
|Tipo de datos:  <br/> |PT_LONG  <br/> |
|Área:  <br/> |Tarea  <br/> |
   
## <a name="remarks"></a>Notas

Esta propiedad se puede dejar sin establecer. Si se establece, su valor debe ser mayor que "0x800186A0" (-2,147,383,648) y menor que "0x7FFE7960" (2,147,383,648) y debe ser único entre las tareas en la misma carpeta.
  
Cada vez que el cliente establece esta propiedad en un número menor que el valor negativo del valor actual de la propiedad **PR_ORDINAL_MOST** ([PidTagOrdinalMost](pidtagordinalmost-canonical-property.md)) de la carpeta, el cliente también debe actualizar **PR_ORDINAL_MOST** en la carpeta. 
  
La propiedad **PR_ORDINAL_MOST** de la carpeta proporciona una manera eficaz para determinar un valor único entre tareas en la misma carpeta. 
  
## <a name="related-resources"></a>Recursos relacionados

### <a name="protocol-specifications"></a>Especificaciones de protocolo

[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Proporciona definiciones de conjunto de propiedades y las referencias a las especificaciones del protocolo de Exchange Server relacionadas.
    
[[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)
  
> Define varios objetos que modelar el equivalente electrónico de tareas, asignaciones de tareas y actualizaciones de tareas. 
    
### <a name="header-files"></a>Archivos de encabezado

Mapidefs.h
  
> Proporciona definiciones de tipo de datos.
    
## <a name="see-also"></a>Ver también



[Propiedades MAPI](mapi-properties.md)
  
[Propiedades MAPI canónicas](mapi-canonical-properties.md)
  
[Asignación de nombres de propiedad canónico a nombres de MAPI](mapping-canonical-property-names-to-mapi-names.md)
  
[Asignación de nombres MAPI para nombres canónicos (propiedad)](mapping-mapi-names-to-canonical-property-names.md)
