---
title: Propiedad canónica PidTagSearchRecipientEmailBcc
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d9561d13-8d52-500c-5369-15a2cf5c92c3
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 5b0db4b3bc7903aae74fa7275d3e27e22d628514
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25387751"
---
# <a name="pidtagsearchrecipientemailbcc-canonical-property"></a>Propiedad canónica PidTagSearchRecipientEmailBcc

  
  
**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
Contiene una cadena Unicode que se está realizando la consulta en la lista de direcciones de correo electrónico o nombres para mostrar de los destinatarios en la línea **CCO** de los mensajes no enviados en el almacén. 
  
## 

|||
|:-----|:-----|
|Propiedades asociadas:  <br/> |PR_SEARCH_RECIP_EMAIL_BCC_W  <br/> |
|Identificador:  <br/> |0x0EA8  <br/> |
|Tipo de propiedad:  <br/> |PT_UNICODE  <br/> |
|Access:  <br/> |Búsqueda  <br/> |
   
## <a name="remarks"></a>Comentarios

Esta propiedad sólo es relevante para los mensajes en el almacén de que no se ha enviado, debido a que los mensajes que se han enviado o recibido no contienen información de CCO.
  
> [!NOTE]
> Esta etiqueta de restricción de MAPI, usada para buscar direcciones de correo electrónico o nombres para mostrar a los que se van a enviar el mensaje como una copia oculta, no es posible que se define en el archivo de encabezado descargables que tiene actualmente. Puede agregar a su código con el siguiente valor: >`#define PR_SEARCH_RECIP_EMAIL_BCC_W PROP_TAG(PT_UNICODE, 0x0EA8)`
  
## <a name="related-resources"></a>Recursos relacionados

### <a name="protocol-specifications"></a>Especificaciones de protocolo

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Proporciona referencias a las especificaciones de protocolo de Microsoft Exchange Server relacionadas.
    
[[MS-OXOSRCH]](https://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)
  
> Especifica las propiedades y operaciones para manipular la configuración de la lista de carpetas de búsqueda.
    
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

