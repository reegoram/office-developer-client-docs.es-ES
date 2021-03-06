---
title: IMAPISupportDoSentMail
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.DoSentMail
api_type:
- COM
ms.assetid: 4bb65c2a-9926-42da-9161-47836e8de40a
description: '�ltima modificaci�n: s�bado, 23 de julio de 2011'
ms.openlocfilehash: 82490dbe597ebd3f7198aa7e0c904a10202ecd77
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568213"
---
# <a name="imapisupportdosentmail"></a>IMAPISupport::DoSentMail

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Procesa un mensaje enviado.
  
```cpp
HRESULT DoSentMail(
  ULONG ulFlags,
  LPMESSAGE lpMessage
);
```

## <a name="parameters"></a>Par�metros

 _ulFlags_
  
> [entrada] Reservado; debe ser cero.
    
 _lpMessage_
  
> [entrada] Un puntero al mensaje abierto para el que se debe generar un mensaje en la carpeta designada para contener los elementos enviados.
    
## <a name="return-value"></a>Valor devuelto

S_OK 
  
> La llamada se ha realizado correctamente y devuelva el valor esperado o los valores.
    
## <a name="remarks"></a>Comentarios

The **IMAPISupport::DoSentMail** method is implemented for message store provider support objects. Message store providers call **DoSentMail** from their implementation of the [IMsgStore::FinishedMsg](imsgstore-finishedmsg.md) method, which is called by the MAPI spooler when it has finished processing a message. **FinishedMsg** unlocks the message, ensures that the message's reference count is 1, and calls **DoSentMail**.
  
 **DoSentMail** realiza las tareas siguientes: 
  
- Comprueba el mensaje para la propiedad **PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) determinar si se debe eliminar el mensaje después de enviarlo.
    
- Determina la ubicaci�n de la carpeta Elementos enviados.
    
- Inicia el enlace del mensaje de procesamiento para los enlaces definidos en la carpeta Elementos enviados.
    
- Mueve el mensaje a la carpeta Elementos enviados, la carpeta Elementos eliminados, o a otra carpeta.
    
- Libera el mensaje.
    
## <a name="see-also"></a>Vea tambi�n



[IMsgStore::FinishedMsg](imsgstore-finishedmsg.md)
  
[Propiedad can�nico de PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)
  
[IMAPISupport: IUnknown](imapisupportiunknown.md)

