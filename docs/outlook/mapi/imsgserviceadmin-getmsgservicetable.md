---
title: IMsgServiceAdminGetMsgServiceTable
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgServiceAdmin.GetMsgServiceTable
api_type:
- COM
ms.assetid: 064dd5ca-0108-4045-b17b-0bb29cb93346
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 5d8e91490cc39c3f259d35a923bb3bcbb2bf6011
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568171"
---
# <a name="imsgserviceadmingetmsgservicetable"></a>IMsgServiceAdmin::GetMsgServiceTable

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Proporciona acceso a la tabla de servicio de mensajes, una lista de los servicios de mensaje en el perfil.
  
```cpp
HRESULT GetMsgServiceTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a>Par�metros

 _ulFlags_
  
> [entrada] Siempre es NULL.
    
 _lppTable_
  
> [out] Un puntero a un puntero a la tabla de mensajes de servicio.
    
## <a name="return-value"></a>Valor devuelto

S_OK 
  
> La tabla de mensajes de servicio se devolvió correctamente.
    
## <a name="remarks"></a>Comentarios

El método **IMsgServiceAdmin::GetMsgServiceTable** proporciona acceso a la tabla de servicio de mensajes, una tabla que mantiene MAPI que se enumera los servicios de mensaje instalados actualmente en el perfil de sesión. Para obtener una lista completa de las columnas en la tabla de servicios de mensaje, vea [Tabla de mensajes de servicio](message-service-tables.md).
  
En la tabla de servicio del mensaje es estática. Después de que un cliente se han concedido acceso a él, mensaje subsiguientes servicio incorporaciones o eliminaciones no afectará a él. Si no hay ningún servicio de mensaje en el perfil actual, **GetMsgServiceTable** devuelve un objeto table con cero filas. 
  
## <a name="mfcmapi-reference"></a>Referencia MFCMAPI

MFCMAPI c�digo de ejemplo, vea la siguiente tabla.
  
|**Archivo**|**Funci�n**|**Comentario**|
|:-----|:-----|:-----|
|MsgServiceTableDlg.cpp  <br/> |CMsgServiceTableDlg::OnRefreshView  <br/> |MFCMAPI utiliza el método **IMsgServiceAdmin::GetMsgServiceTable** para cargar en la tabla de servicios en un perfil para representar en la vista.  <br/> |
   
## <a name="see-also"></a>Recursos adicionales



[IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)
  
[IMsgServiceAdmin::DeleteMsgService](imsgserviceadmin-deletemsgservice.md)
  
[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)


[MFCMAPI como un ejemplo de c�digo](mfcmapi-as-a-code-sample.md)

