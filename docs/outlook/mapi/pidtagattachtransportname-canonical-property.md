---
title: Propiedad canónica PidTagAttachTransportName
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachTransportName
api_type:
- HeaderDef
ms.assetid: 701fca52-0f96-4019-80cd-c0ccd059ff9b
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: bd3a22bf55d03f3a9f06bf5c19650407bcc5627d
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25400519"
---
# <a name="pidtagattachtransportname-canonical-property"></a>Propiedad canónica PidTagAttachTransportName

  
  
**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
Contiene el nombre de un archivo de datos adjuntos modificado para que se puede asociar con mensajes TNEF. 
  
|||
|:-----|:-----|
|Propiedades asociadas:  <br/> |PR_ATTACH_TRANSPORT_NAME, PR_ATTACH_TRANSPORT_NAME_A, PR_ATTACH_TRANSPORT_NAME_W  <br/> |
|Identificador:  <br/> |0x370C  <br/> |
|Tipo de datos:  <br/> |PT_STRING8, PT_UNICODE  <br/> |
|Área:  <br/> |Datos adjuntos del mensaje  <br/> |
   
## <a name="remarks"></a>Comentarios

TNEF y el proveedor de transporte usan estas propiedades. Normalmente, no están disponibles para las aplicaciones cliente. 
  
Estas propiedades se usan con frecuencia por TNEF cuando el sistema de mensajería subyacente no es compatible con los nombres de archivo proporcionado. Por ejemplo, se utilizan cuando el usuario asocia a varios archivos con el mismo nombre, como archivos de cinco denominado CONFIG. PREDETERMINADO DEL SISTEMA El proveedor de transporte debe modificar los nombres para asegurarse de que son únicos. Cada nombre modificado aparece en su adjunto **PR_ATTACH_TRANSPORT_NAME** y propiedades asociadas. 
  
## <a name="related-resources"></a>Recursos relacionados

### <a name="protocol-specifications"></a>Especificaciones de protocolo

[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> Controla los objetos de mensaje y los datos adjuntos.
    
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

