---
title: Propiedad canónica PidTagOriginalSenderAddressType
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalSenderAddressType
api_type:
- COM
ms.assetid: bd777f19-cbb1-4497-8a0b-e05b491c6957
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: d593b5ae1c2341ae0972ba68bcf42dde64e9a2f1
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25401709"
---
# <a name="pidtagoriginalsenderaddresstype-canonical-property"></a>Propiedad canónica PidTagOriginalSenderAddressType

  
  
**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
Contiene el tipo de dirección del remitente de la primera versión de un mensaje, es decir, el mensaje antes de que se reenvía o se responde a.
  
|||
|:-----|:-----|
|Propiedades asociadas:  <br/> |PR_ORIGINAL_SENDER_ADDRTYPE, PR_ORIGINAL_SENDER_ADDRTYPE_A, PR_ORIGINAL_SENDER_ADDRTYPE_W  <br/> |
|Identificador:  <br/> |0 x 0066  <br/> |
|Tipo de datos:  <br/> |PT_STRING8, PT_UNICODE  <br/> |
|Área:  <br/> |General de mensajería  <br/> |
   
## <a name="remarks"></a>Comentarios

Estas propiedades son ejemplos de las propiedades de direcciones para el remitente original de un mensaje. En el primer envío del mensaje, la aplicación cliente debe establecer estas propiedades en el valor de **PR_SENDER_ADDRTYPE** ([PidTagSenderAddressType](pidtagsenderaddresstype-canonical-property.md)). Nunca se ha cambiado cuando el mensaje se reenvía o se responde a.
  
## <a name="related-resources"></a>Recursos relacionados

### <a name="protocol-specifications"></a>Especificaciones de protocolo

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Proporciona referencias a las especificaciones del protocolo de Exchange Server relacionadas.
    
[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> Especifica las propiedades y operaciones que se permiten en los objetos de mensajes de correo electrónico.
    
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

