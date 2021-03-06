---
title: IMAPISupportGetSvcConfigSupportObj
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.GetSvcConfigSupportObj
api_type:
- COM
ms.assetid: 56c3bdae-a3a8-4334-b6d2-a89c6820d72e
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: 1c48ceefa84658b236b8dfa4e10df18c175d920e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22595163"
---
# <a name="imapisupportgetsvcconfigsupportobj"></a>IMAPISupport::GetSvcConfigSupportObj

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Crea un objeto de soporte técnico del servicio de mensajes.
  
```cpp
HRESULT GetSvcConfigSupportObj(
  ULONG ulFlags,
  LPMAPISUP FAR * lppSvcSupport
);
```

## <a name="parameters"></a>Par�metros

 _ulFlags_
  
> [entrada] Reservado; debe ser cero.
    
 _lppSvcSupport_
  
> [out] Un puntero a un puntero al nuevo objeto de soporte técnico de servicio del mensaje.
    
## <a name="return-value"></a>Valor devuelto

S_OK 
  
> Se ha creado correctamente el objeto de configuración de soporte técnico.
    
## <a name="remarks"></a>Comentarios

El método **IMAPISupport::GetSvcConfigSupportObj** se implementa para todos los objetos de soporte técnico. Proveedores de servicios de llamar a **GetSvcConfigSupportObj** para crear un objeto de soporte técnico de configuración que se pase a una función de punto de entrada de servicio de mensaje. 
  
Una función de punto de entrada de servicio de mensajes se basa en el prototipo [MSGSERVICEENTRY](msgserviceentry.md) y se llama a los métodos de la interfaz [IMsgServiceAdmin](imsgserviceadminiunknown.md) . Una función de punto de entrada de servicio de mensajes permite servicios de mensajes configurar ellos mismos o realizar otras acciones cuando se cambia el perfil. Punto de entrada de servicio de mensaje funciones pueden admitir los cambios de configuración mediante la presentación de una hoja de propiedades o a través de una matriz de valores de propiedad que se pasa al método [IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md) . 
  
## <a name="see-also"></a>Recursos adicionales



[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)
  
[IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)
  
[IMsgServiceAdmin::CreateMsgService](imsgserviceadmin-createmsgservice.md)
  
[IProfAdmin : IUnknown](iprofadminiunknown.md)
  
[MSGSERVICEENTRY](msgserviceentry.md)
  
[IMAPISupport: IUnknown](imapisupportiunknown.md)

