---
title: IABLogonUnadvise
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABLogon.Unadvise
api_type:
- COM
ms.assetid: 3e506b29-c7e3-40d6-a08b-22fa87088c2d
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: 3fbf8b423cfd4206a0143b5639c85dbcacce2fae
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570985"
---
# <a name="iablogonunadvise"></a>IABLogon::Unadvise

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Cancela las notificaciones que se han configurado previamente con una llamada al método [IABLogon::Advise](iablogon-advise.md) . 
  
```cpp
HRESULT Unadvise(
  ULONG ulConnection
);
```

## <a name="parameters"></a>Parámetros

 _ulConnection_
  
> [entrada] El número de conexión asociado con un registro activo de notificación. Una llamada anterior a **Advise** debe haber devuelve el valor de _ulConnection_.
    
## <a name="return-value"></a>Valor devuelto

S_OK 
  
> El registro de notificación se canceló correctamente.
    
## <a name="remarks"></a>Comentarios

MAPI llama al método de **Unadvise** para cancelar el registro de una notificación para un contenedor, usuario o el objeto de lista de distribución de mensajería. 
  
## <a name="notes-to-implementers"></a>Notas para los implementadores

La implementación de **Unadvise** dependen de si se admite la notificación con ayuda de MAPI o de forma manual. Si MAPI proporciona el soporte técnico, llame al método [IMAPISupport::Unsubscribe](imapisupport-unsubscribe.md) para cancelar el registro. Si otro subproceso está en proceso de llamar al método [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) del receptor de notificaciones, se puede retrasar hasta que se ha devuelto **OnNotify** . 
  
Para obtener más información sobre el proceso de notificación, vea [Notificación de evento de MAPI](event-notification-in-mapi.md). Para obtener información acerca de cómo usar el [IMAPISupport: IUnknown](imapisupportiunknown.md) métodos para admitir la notificación, vea [Compatibilidad con notificación de evento](supporting-event-notification.md).
  
## <a name="see-also"></a>Recursos adicionales



[IABLogon::Advise](iablogon-advise.md)
  
[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IABLogon : IUnknown](iablogoniunknown.md)

