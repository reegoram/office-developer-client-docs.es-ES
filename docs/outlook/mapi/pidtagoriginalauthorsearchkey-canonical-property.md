---
title: Propiedad canónica PidTagOriginalAuthorSearchKey
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalAuthorSearchKey
api_type:
- COM
ms.assetid: 4a10cf99-c5e6-4a24-b531-3aebb7800bfe
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 225c0813139a74b735b5b8a3d5a729e630cd3511
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563341"
---
# <a name="pidtagoriginalauthorsearchkey-canonical-property"></a>Propiedad canónica PidTagOriginalAuthorSearchKey

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Contiene la clave de búsqueda del autor de la primera versión de un mensaje, es decir, el mensaje antes de que se reenvía o se responde a.
  
|||
|:-----|:-----|
|Propiedades asociadas:  <br/> |PR_ORIGINAL_AUTHOR_SEARCH_KEY  <br/> |
|Identificador:  <br/> |0x0056  <br/> |
|Tipo de datos:  <br/> |PT_BINARY  <br/> |
|Área:  <br/> |Servidor  <br/> |
   
## <a name="remarks"></a>Comentarios

Esta propiedad es una de las propiedades de dirección para el autor de un mensaje. En el primer envío del mensaje, la aplicación cliente debe establecer esta propiedad en el valor de la propiedad de[PidTagSenderSearchKey](pidtagsendersearchkey-canonical-property.md) **PR_SENDER_SEARCH_KEY**. Nunca se ha cambiado cuando el mensaje se reenvía o se responde a. 
  
Permitir que las propiedades autor original para la conservación de la información desde fuera del dominio de mensajería local. Cuando un mensaje llega desde otro dominio de mensajería, como desde Internet, estas propiedades proporcionan una forma de garantizar que no se pierda la información original.
  
## <a name="related-resources"></a>Recursos relacionados

### <a name="header-files"></a>Archivos de encabezado

Mapidefs.h
  
> Proporciona definiciones de tipo de datos.
    
Mapitags.h
  
> Contiene las definiciones de propiedades que se muestran como propiedades asociadas.
    
## <a name="see-also"></a>Recursos adicionales



[Propiedades MAPI](mapi-properties.md)
  
[Propiedades MAPI canónicas](mapi-canonical-properties.md)
  
[Asignar nombres de propiedad canónicos a nombres MAPI](mapping-canonical-property-names-to-mapi-names.md)
  
[Asignar nombres MAPI a los nombres de propiedad canónico](mapping-mapi-names-to-canonical-property-names.md)

