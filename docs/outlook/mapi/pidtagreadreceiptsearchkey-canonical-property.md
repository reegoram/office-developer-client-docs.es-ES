---
title: Propiedad canónica PidTagReadReceiptSearchKey
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReadReceiptSearchKey
api_type:
- COM
ms.assetid: a0ea5628-1393-4ab8-bc34-a58cf130db51
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: aa92e224f10fd652078b965c8e3a0b5ab59cc388
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25398734"
---
# <a name="pidtagreadreceiptsearchkey-canonical-property"></a>Propiedad canónica PidTagReadReceiptSearchKey

  
  
**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
Contiene una clave de búsqueda para el usuario de mensajería a la que el sistema de mensajería debe dirigir un informe de lectura para un mensaje.
  
|||
|:-----|:-----|
|Propiedades asociadas:  <br/> |PR_READ_RECEIPT_SEARCH_KEY  <br/> |
|Identificador:  <br/> |0x0053  <br/> |
|Tipo de datos:  <br/> |PT_BINARY  <br/> |
|Área:  <br/> |Sobres MAPI  <br/> |
   
## <a name="remarks"></a>Comentarios

Esta propiedad se omite a menos que la propiedad **PR_READ_RECEIPT_REQUESTED de MAPI** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) está establecida en TRUE.
  
Si una aplicación cliente desea recibir informes de lectura propiamente dicha, puede deje sin establecer esta propiedad o establecer a la clave de búsqueda contenida en la propiedad **PR_SENDER_SEARCH_KEY** ([PidTagSenderSearchKey](pidtagsendersearchkey-canonical-property.md)) en tiempo de envío de mensaje.
  
## <a name="related-resources"></a>Recursos relacionados

### <a name="protocol-specifications"></a>Especificaciones de protocolo

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Proporciona referencias a las especificaciones del protocolo de Exchange Server relacionadas.
    
[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> Especifica las propiedades y operaciones que se permiten en mensajes de correo electrónico.
    
### <a name="header-files"></a>Archivos de encabezado

Mapidef.h
  
> Proporciona definiciones de tipo de datos.
    
Mapitags.h
  
> Contiene las definiciones de las propiedades que aparecen como nombres alternativos.
    
## <a name="see-also"></a>Vea también



[Propiedades MAPI](mapi-properties.md)
  
[Propiedades MAPI canónicas](mapi-canonical-properties.md)
  
[Asignar nombres de propiedad canónicos a nombres MAPI](mapping-canonical-property-names-to-mapi-names.md)
  
[Asignar nombres MAPI a los nombres de propiedad canónico](mapping-mapi-names-to-canonical-property-names.md)

