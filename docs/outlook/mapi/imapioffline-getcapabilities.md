---
title: IMAPIOfflineGetCapabilities
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIOffline.GetCapabilities
api_type:
- COM
ms.assetid: aa8dc48b-9e1c-8da0-9579-10b7174e99de
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: 699e77479e0d09e7549c0d2741d5ba54ecc8ce33
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572035"
---
# <a name="imapiofflinegetcapabilities"></a>IMAPIOffline::GetCapabilities

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Obtiene las condiciones para la que se admiten las devoluciones de llamada por un objeto sin conexión.
  
```cpp
HRESULT GetCapabilities( 
    ULONG *pulCapabilities 
);
```

## <a name="parameters"></a>Parámetros

 _pulCapablities_
  
> [out] Una máscara de bits de los siguientes indicadores de capacidad:
    
MAPIOFFLINE_CAPABILITY_OFFLINE
  
> El objeto sin conexión es capaz de proporcionar notificaciones sin conexión.
    
MAPIOFFLINE_CAPABILITY_ONLINE
  
> El objeto sin conexión es capaz de proporcionar notificaciones en línea.
    
## <a name="remarks"></a>Comentarios

Al abrir un objeto sin conexión mediante **[HrOpenOfflineObj](hropenofflineobj.md)**, puede consultar un cliente en [IMAPIOfflineMgr](imapiofflinemgrimapioffline.md) para obtener un puntero a una interfaz **IMAPIOffline** y llame a **IMAPIOffline::GetCapabilities** para averiguar las devoluciones de llamada compatibles por el objeto. El cliente, a continuación, puede optar por configurar las devoluciones de llamada mediante **IMAPIOfflineMgr**.
  
Tenga en cuenta que, dependiendo del servidor de correo para un objeto sin conexión, un objeto que admite las devoluciones de llamada para navegar por Internet no necesariamente admite las devoluciones de llamada para trabajar sin conexión.
  
Tenga en cuenta también, mientras que un objeto sin conexión, es posible que admitan las devoluciones de llamada para que los cambios que no sea en línea o sin conexión, la API de estado sin conexión admite sólo los cambios en línea o sin conexión y los clientes deben comprobar para sólo estas capacidades.
  
## <a name="see-also"></a>Recursos adicionales



[IMAPIOffline::GetCurrentState](imapioffline-getcurrentstate.md)
  
[IMAPIOffline::SetCurrentState](imapioffline-setcurrentstate.md)
  
[IMAPIOfflineMgr : IMAPIOffline](imapiofflinemgrimapioffline.md)


[Constantes MAPI](mapi-constants.md)
  
[HrOpenOfflineObj](hropenofflineobj.md)

