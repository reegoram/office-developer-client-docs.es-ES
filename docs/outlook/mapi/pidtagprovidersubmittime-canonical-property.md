---
title: Propiedad canónica PidTagProviderSubmitTime
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagProviderSubmitTime
api_type:
- COM
ms.assetid: 9e5161d9-fefe-4a12-b7f7-5600f1d2e95b
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: e08b56fcfea38bf65e8628acfa481716554e2c01
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571615"
---
# <a name="pidtagprovidersubmittime-canonical-property"></a>Propiedad canónica PidTagProviderSubmitTime

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Contiene la fecha y hora que había pasado de un proveedor de transporte de un mensaje a su sistema de mensajería subyacente.
  
|||
|:-----|:-----|
|Propiedades asociadas:  <br/> |PR_PROVIDER_SUBMIT_TIME  <br/> |
|Identificador:  <br/> |0x0048  <br/> |
|Tipo de datos:  <br/> |PT_SYSTIME  <br/> |
|Área:  <br/> |Sobres MAPI  <br/> |
   
## <a name="remarks"></a>Comentarios

Esta propiedad se establece por el proveedor de transporte saliente en el momento en que se envía un mensaje.
  
Esta propiedad corresponde a un atributo de cada mensaje X.400 envelope de envío. 
  
## <a name="related-resources"></a>Recursos relacionados

### <a name="header-files"></a>Archivos de encabezado

Mapidefs.h
  
> Proporciona definiciones de tipo de datos.
    
Mapitags.h
  
> Contiene las definiciones de las propiedades que aparecen como nombres alternativos.
    
## <a name="see-also"></a>Recursos adicionales



[Propiedades MAPI](mapi-properties.md)
  
[Propiedades MAPI canónicas](mapi-canonical-properties.md)
  
[Asignar nombres de propiedad canónicos a nombres MAPI](mapping-canonical-property-names-to-mapi-names.md)
  
[Asignar nombres MAPI a los nombres de propiedad canónico](mapping-mapi-names-to-canonical-property-names.md)

