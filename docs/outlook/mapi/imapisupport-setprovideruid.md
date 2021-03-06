---
title: IMAPISupportSetProviderUID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.SetProviderUID
api_type:
- COM
ms.assetid: 58855843-9a2b-4e5d-9332-b1bfad8b45e4
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: df842e633f1586d6d77441126d51b2ce44ec3beb
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589073"
---
# <a name="imapisupportsetprovideruid"></a>IMAPISupport::SetProviderUID

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Registra una estructura [MAPIUID](mapiuid.md) que representa el proveedor de servicios de forma exclusiva. 
  
```cpp
HRESULT SetProviderUID(
LPMAPIUID lpProviderID,
ULONG ulFlags
);
```

## <a name="parameters"></a>Parámetros

 _lpProviderID_
  
> [entrada] Un puntero a la estructura **MAPIUID** que identifica el proveedor de almacenamiento de mensaje o de la libreta de direcciones. 
    
 _ulFlags_
  
> Reservado; debe ser cero.
    
## <a name="return-value"></a>Valor devuelto

S_OK 
  
> La estructura **MAPIUID** se ha registrado correctamente. 
    
## <a name="remarks"></a>Comentarios

El método **IMAPISupport::SetProviderUID** se implementa para dirección libreta de direcciones y el mensaje de proveedor compatibilidad con objetos de almacén. Estos proveedores de llamar a **SetProviderUID** para registrar un identificador único que se describen en la estructura **MAPIUID** que señala a _lpProviderID_. Proveedores de incluyen este identificador en todos los identificadores de entrada que se crean. 
  
MAPI utiliza la estructura **MAPIUID** cuando envían los mensajes salientes a la cola MAPI y para determinar el proveedor adecuado para el tratamiento de las solicitudes de cliente. Por ejemplo, cuando un cliente llama al método de [IMAPISession::OpenEntry](imapisession-openentry.md) , MAPI examina la parte **MAPIUID** del identificador de entrada, asigna al proveedor de que se pasa a **SetProviderUID**y llama a su proveedor **OpenEntry** . 
  
## <a name="notes-to-callers"></a>Notas para los llamadores

Llamar a **SetProviderUID** en tiempo de inicio de sesión para registrar la estructura **MAPIUID** . MAPI permite dirección libreta de direcciones y el mensaje de los proveedores de almacén registrar varios identificadores. Cuando realiza varias llamadas a **SetProviderUID**, agrega siempre la estructura **MAPIUID** a conjunto del proveedor de estructuras **MAPIUID** , incluso si la **MAPIUID** es un duplicado. **SetProviderUID** no se puede quitar un **MAPIUID**. 
  
## <a name="see-also"></a>Recursos adicionales



[MAPIUID](mapiuid.md)
  
[IMAPISupport: IUnknown](imapisupportiunknown.md)

