---
title: IMAPITableUnadvise
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.Unadvise
api_type:
- COM
ms.assetid: 19f0dad9-9704-4bbe-a689-9531e7198351
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 7de4d3c58d5eeefcf9a82235333da5db4703bc8d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592979"
---
# <a name="imapitableunadvise"></a>IMAPITable::Unadvise

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Cancela el envío de notificaciones configuradas previamente con una llamada al método [IMAPITable::Advise](imapitable-advise.md) . 
  
```cpp
HRESULT Unadvise(
ULONG_PTR ulConnection
);
```

## <a name="parameters"></a>Parámetros

 _ulConnection_
  
> [entrada] El número de la conexión de registro devuelto por una llamada a [IMAPITable::Advise](imapitable-advise.md).
    
## <a name="return-value"></a>Valor devuelto

S_OK 
  
> La llamada ha sido correcta.
    
## <a name="remarks"></a>Comentarios

Use el método **IMAPITable::Unadvise** para liberar el puntero al objeto receptor advise pasado en el parámetro _lpAdviseSink_ en la llamada anterior a **IMAPITable::Advise**, con lo que se cancela un registro de la notificación. Como parte de descartar el puntero al objeto receptor advise, se llama al método del objeto **IUnknown:: Release** . Por lo general, se llama a **versión** durante la llamada **Unadvise** , pero si es otro subproceso en el proceso de llamar al método [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) para el receptor de notificaciones, la llamada de la **versión** se retrasa hasta el **OnNotify** Devuelve el método. 
  
Para obtener más información sobre el proceso de notificación, vea [Notificación de evento de MAPI](event-notification-in-mapi.md). Para obtener información específica acerca de la notificación de la tabla, vea [Acerca de las notificaciones de tabla](about-table-notifications.md). Para obtener información acerca del uso de los métodos **IMAPISupport** para admitir la notificación, vea [Compatibilidad con notificación de evento](supporting-event-notification.md).
  
## <a name="mfcmapi-reference"></a>Referencia MFCMAPI

MFCMAPI c�digo de ejemplo, vea la siguiente tabla.
  
|**Archivo**|**Funci�n**|**Comentario**|
|:-----|:-----|:-----|
|ContentsTableListCtrl.cpp  <br/> |CContentsTableListCtrl::NotificationOff  <br/> |MFCMAPI utiliza el método **IMAPITable::Unadvise** para cancelar las notificaciones para la tabla.  <br/> |
   
## <a name="see-also"></a>Recursos adicionales



[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IMAPITable::Advise](imapitable-advise.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)


[MFCMAPI como un ejemplo de c�digo](mfcmapi-as-a-code-sample.md)

