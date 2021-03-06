---
title: Propiedad canónica PidTagStatus
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagStatus
api_type:
- COM
ms.assetid: 8b947660-eafe-47e1-9595-bd3ab7d455bf
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: de2342ef4d3e9d06f198e06dc19c65b7b144624f
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25387912"
---
# <a name="pidtagstatus-canonical-property"></a>Propiedad canónica PidTagStatus

  
  
**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
Contiene una máscara de bits de 32 bits de marcadores que definen el estado de la carpeta.
  
|||
|:-----|:-----|
|Propiedades asociadas:  <br/> |PR_STATUS  <br/> |
|Identificador:  <br/> |0x360B  <br/> |
|Tipo de datos:  <br/> |PT_LONG  <br/> |
|Área:  <br/> |Contenedor MAPI  <br/> |
   
## <a name="remarks"></a>Comentarios

Esta propiedad para las carpetas es análoga a la propiedad **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) para los mensajes. Sus indicadores se proporcionan para la aplicación de cliente sólo y no afectan el almacén de mensajes. Los clientes pueden usar u omitir estas opciones de configuración. El cliente también puede definir sus propios valores para los bits definidos por el cliente de esta propiedad.
  
La máscara de bits se pueden establecer uno o varios de los siguientes indicadores:
  
FLDSTATUS_DELMARKED 
  
> La carpeta está marcada para su eliminación. La aplicación cliente establece esta marca.
    
FLDSTATUS_HIDDEN 
  
> La carpeta está oculta.
    
FLDSTATUS_HIGHLIGHTED 
  
> La carpeta está resaltada, por ejemplo, se muestra en orden inverso vídeo.
    
FLDSTATUS_TAGGED 
  
> La carpeta está etiquetada.
    
Los proveedores de almacén de mensajes establecen esta propiedad en una carpeta a uno o varios de estos valores y los clientes interpretan el estado según corresponda para sus aplicaciones. Por ejemplo, un cliente puede utilizar el estado de la carpeta para diferenciar entre las carpetas en una tabla de jerarquías, mostrar carpetas con el mismo estado de la misma manera. Resaltado de las carpetas se pueden mostrar en las carpetas de vídeos, con etiqueta inversas y las carpetas marcadas para eliminación que se pueden mostrar con un icono significativo y se pueden ocultar las carpetas ocultas.
  
Bits 16 a 31 ("0 x 10000" a través de "0 x 80000000") de esta propiedad están disponibles para su uso por la aplicación de cliente IPM. Todos los demás bits están reservados para su uso por MAPI; los no definidos en la lista anterior deben inicialmente se establece en cero y no se modifica.
  
## <a name="related-resources"></a>Recursos relacionados

### <a name="protocol-specifications"></a>Especificaciones de protocolo

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Proporciona referencias a las especificaciones del protocolo de Exchange Server relacionadas.
    
[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> Controla los objetos de mensaje y los datos adjuntos.
    
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

