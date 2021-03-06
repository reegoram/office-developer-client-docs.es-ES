---
title: Propiedad canónica PidTagDefaultPostMessageClass
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDefaultPostMessageClass
api_type:
- HeaderDef
ms.assetid: 231c288f-547b-4463-9442-1499661b925e
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 0ab904625d3a23462a4fedf3b64f49c54b34ad28
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25401730"
---
# <a name="pidtagdefaultpostmessageclass-canonical-property"></a>Propiedad canónica PidTagDefaultPostMessageClass

  
  
**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
Contiene el nombre de un clase de mensaje del formulario personalizado.
  
|||
|:-----|:-----|
|Propiedades asociadas:  <br/> |PR_DEF_POST_MSGCLASS  <br/> |
|Identificador:  <br/> |0x36E5  <br/> |
|Tipo de datos:  <br/> |PT_STRING8  <br/> |
|Área:  <br/> |Contenedor MAPI  <br/> |
   
## <a name="remarks"></a>Comentarios

Si esta propiedad se establece en una carpeta, el valor debe contener exactamente con la clase base de mensaje (por ejemplo, "IPM. Contacto"para una carpeta de contactos o"IPM. Cita"para una carpeta de calendario), o comenzar con la clase de mensaje base (por ejemplo," IPM. Contact.MyContact").
  
## <a name="related-resources"></a>Recursos relacionados

### <a name="protocol-specifications"></a>Especificaciones de protocolo

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Proporciona referencias a las especificaciones del protocolo de Exchange Server relacionadas.
    
[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> Especifica las propiedades y operaciones para una cita, convocatoria de reunión y mensajes de respuesta.
    
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

