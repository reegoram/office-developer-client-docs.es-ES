---
title: Propiedad canónica PidTagNull
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagNull
api_type:
- HeaderDef
ms.assetid: 192cdab8-c615-47b9-9f04-a1414eaf0c77
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 55db507055692c9e929b0125abf719d8c03ac967
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2018
ms.locfileid: "19819793"
---
# <a name="pidtagnull-canonical-property"></a>Propiedad canónica PidTagNull

  
  
**Hace referencia a**: Outlook 
  
Representa un valor null o la configuración de una propiedad o se reserva espacio de matriz.
  
|||
|:-----|:-----|
|Propiedades asociadas:  <br/> |PR_NULL  <br/> |
|Identificador:  <br/> |0x0000  <br/> |
|Tipo de datos:  <br/> |PT_NULL  <br/> |
|Área:  <br/> |Common  <br/> |
   
## <a name="remarks"></a>Comentarios

Esta propiedad se usa para reservar espacio en las matrices de estructuras [SPropValue](spropvalue.md) . Se usa en una matriz de estructuras de [elemento SPropTagArray](sproptagarray.md) para indicar al método para reservar espacio en la matriz devuelta de estructuras **SPropValue** . Esto permite que las propiedades calculadas que deben rellenarse una manera económica. 
  
Para obtener más información, vea [Información general sobre el tipo de propiedad MAPI](mapi-property-type-overview.md).
  
## <a name="related-resources"></a>Recursos relacionados

### <a name="protocol-specifications"></a>Especificaciones de protocolo

[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> Especifica las propiedades y operaciones que se permiten en los contactos y las listas de distribución personal.
    
### <a name="header-files"></a>Archivos de encabezado

Mapidefs.h
  
> Proporciona definiciones de tipo de datos.
    
Mapitags.h
  
> Contiene las definiciones de propiedades que se muestran como propiedades asociadas.
    
## <a name="see-also"></a>Vea también



[Propiedades MAPI](mapi-properties.md)
  
[Propiedades MAPI canónicas](mapi-canonical-properties.md)
  
[Asignar nombres de propiedad canónicos a nombres MAPI](mapping-canonical-property-names-to-mapi-names.md)
  
[Asignar nombres MAPI a los nombres de propiedad canónico](mapping-mapi-names-to-canonical-property-names.md)
