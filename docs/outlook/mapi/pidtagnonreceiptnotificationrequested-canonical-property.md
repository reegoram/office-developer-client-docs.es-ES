---
title: Propiedad canónica PidTagNonReceiptNotificationRequested
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagNonReceiptNotificationRequested
api_type:
- HeaderDef
ms.assetid: 747f7ba8-42d3-4be3-9908-269e9a347c7f
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 896cfa2bf8a1b33fd6dee09649853b71618f31be
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582787"
---
# <a name="pidtagnonreceiptnotificationrequested-canonical-property"></a>Propiedad canónica PidTagNonReceiptNotificationRequested

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Contiene TRUE si desea que un remitente del mensaje notificación de no recepción para un destinatario especificado.
  
|||
|:-----|:-----|
|Propiedades asociadas:  <br/> |PR_NON_RECEIPT_NOTIFICATION_REQUESTED  <br/> |
|Identificador:  <br/> |0x0C06  <br/> |
|Tipo de datos:  <br/> |PT_BOOLEAN  <br/> |
|Área:  <br/> |Exchange  <br/> |
   
## <a name="remarks"></a>Comentarios

Si esta propiedad contiene FALSE y la propiedad **PR_READ_RECEIPT_REQUESTED de MAPI** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) contiene TRUE, el proveedor de servicios puede invalidar la propiedad **PR_NON_RECEIPT_NOTIFICATION_REQUESTED** y generar un informe de no entrega. 
  
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

