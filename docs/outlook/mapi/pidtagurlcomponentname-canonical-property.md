---
title: Propiedad canónica PidTagUrlComponentName
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagUrlComponentName
api_type:
- COM
ms.assetid: a21906f9-5408-41ba-a89b-273ab60eeef3
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 26a9d432d98c546aefa8f511ba2c4c9bb26cfd80
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25400337"
---
# <a name="pidtagurlcomponentname-canonical-property"></a>Propiedad canónica PidTagUrlComponentName

  
  
**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
El nombre del componente de dirección URL para un mensaje. 
  
|||
|:-----|:-----|
|Propiedades asociadas:  <br/> |PR_URL_COMP_NAME, PR_URL_COMP_NAME_A, PR_URL_COMP_NAME_W  <br/> |
|Identificador:  <br/> |0x10F3  <br/> |
|Tipo de datos:  <br/> |PT_STRING8, PT_UNICODE  <br/> |
|Área:  <br/> |General de mensajería  <br/> |
   
## <a name="remarks"></a>Comentarios

Estas propiedades deben ser únicas dentro de una carpeta. Si no se conjunto cuando se crea el mensaje, el almacén de mensajes debe establecer estas propiedades en función de diversas propiedades del mensaje, según la clase de mensaje. Por ejemplo, el **IPM. Nota** y **IPM. Cita** mensajes deben tienen esta propiedad establecida en función de la propiedad **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) y la **IPM. Contacto** mensajes deben tener esta propiedad establece en función de la propiedad **dispidFileUnder** ([PidLidFileUnder](pidlidfileunder-canonical-property.md)). Para la mayoría de clases de mensaje, esta propiedad debe basarse en la propiedad **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)).
  
## <a name="related-resources"></a>Recursos relacionados

### <a name="protocol-specifications"></a>Especificaciones de protocolo

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Proporciona referencias a las especificaciones del protocolo de Exchange Server relacionadas.
    
[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> Controla los objetos de mensaje y los datos adjuntos.
    
[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)
  
> Codifica y descodifica los objetos de mensaje y datos adjuntos a una representación de secuencia eficaz.
    
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

