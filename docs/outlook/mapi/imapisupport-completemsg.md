---
title: IMAPISupportCompleteMsg
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.CompleteMsg
api_type:
- COM
ms.assetid: e7932433-abe0-4341-95e0-91b37c848145
description: '�ltima modificaci�n: s�bado, 23 de julio de 2011'
ms.openlocfilehash: db28d9684f1bb679ce36f99346f4ecc67a1a93e6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2018
ms.locfileid: "19817483"
---
# <a name="imapisupportcompletemsg"></a>IMAPISupport::CompleteMsg

  
  
**Se aplica a**: Outlook 
  
Realiza procesamiento posterior en un mensaje. 
  
```cpp
HRESULT CompleteMsg(
  ULONG ulFlags,
  ULONG cbEntryID,
  LPENTRYID lpEntryID
);
```

## <a name="parameters"></a>Par�metros

 _ulFlags_
  
> [entrada] Reservado; debe ser cero.
    
 _cbEntryID_
  
> [entrada] El número de bytes en el identificador de entrada indicado por el parámetro _lpEntryID_ . 
    
 _lpEntryID_
  
> [entrada] Un puntero al identificador de entrada del mensaje para procesar.
    
## <a name="return-value"></a>Valor devuelto

S_OK 
  
> El procesamiento posterior realizada correctamente.
    
## <a name="remarks"></a>Notas

El método **IMAPISupport::CompleteMsg** se implementa para objetos de soporte técnico de proveedor de almacén de mensajes y se denomina sólo por los proveedores de almacén de mensajes que estén asociados estrechamente con los proveedores de transporte. Los proveedores de almacén acoplado llame a **IMAPISupport::CompleteMsg** para indicar a la cola MAPI para postprocess un mensaje. 
  
## <a name="notes-to-callers"></a>Notas para los llamadores

Llamar a **CompleteMsg** sólo cuando estrechamente con un proveedor de transporte, puede administrar todos los destinatarios del mensaje y da alguna de las siguientes condiciones: 
  
- El mensaje se preprocesa.
    
- El mensaje requiere procesamiento posterior por la cola de MAPI.
    
## <a name="see-also"></a>Ver también



[IMAPISupport: IUnknown](imapisupportiunknown.md)
