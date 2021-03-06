---
title: IMAPIOfflineMgrAdvise
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIOfflineMgr.Advise
api_type:
- COM
ms.assetid: 784b6218-548d-817a-caaa-cf9be6bc3d2f
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: e0c8c4c6251581506c7bdd78c009bb12e8291c81
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586938"
---
# <a name="imapiofflinemgradvise"></a>IMAPIOfflineMgr::Advise

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Registra un cliente para recibir las devoluciones de llamada en un objeto sin conexión.
  
```cpp
HRESULT COfflineObj::Advise( 
      ULONG ulFlags, 
      MAPIOFFLINE_ADVISEINFO* pAdviseInfo, 
      ULONG* pulAdviseToken 
);
```

## <a name="parameters"></a>Par�metros

 _ulFlags_
  
>  [entrada] Marcas que modifican el comportamiento. Se admite el valor MAPIOFFLINE_ADVISE_DEFAULT. 
    
 _pAdviseInfo_
  
> [entrada] Información sobre el tipo de devolución de llamada, cuándo se debe recibir una devolución de llamada, una interfaz de devolución de llamada para el autor de la llamada y otros detalles. También contiene un símbolo (token) de cliente que utiliza Outlook en el envío de las devoluciones de llamada de la notificación posterior al autor de llamada de cliente.
    
 _pulAdviseToken_
  
> [out] Un token de advise devuelve al autor de la llamada de cliente para cancelar la devolución de llamada para el objeto posteriormente.
    
## <a name="return-value"></a>Valor devuelto

S_OK
  
> La llamada tuvo éxito.
    
E_INVALIDARG
  
> Se ha especificado un parámetro no válido.
    
E_NOINTERFACE
  
> La interfaz de devolución de llamada especificada en *pAdviseInfo* no es válida. 
    
## <a name="remarks"></a>Comentarios

Al abrir un objeto sin conexión con **[HrOpenOfflineObj](hropenofflineobj.md)**, un cliente obtiene un objeto sin conexión que admite **IMAPIOfflineMgr**. El cliente puede comprobar para los tipos de devoluciones de llamada admitidos por el objeto utilizando **[IMAPIOffline::GetCapabilities](imapioffline-getcapabilities.md)**. El cliente puede determinar el tipo y otros detalles acerca de la devolución de llamada que desea y, a continuación, llame a **IMAPIOfflineMgr::Advise** para registrarse y para recibir esas devoluciones de llamada sobre el objeto. 
  
## <a name="see-also"></a>Recursos adicionales



[IMAPIOffline::GetCapabilities](imapioffline-getcapabilities.md)
  
[IMAPIOfflineMgr::Unadvise](imapiofflinemgr-unadvise.md)


[Constantes MAPI](mapi-constants.md)
  
[HrOpenOfflineObj](hropenofflineobj.md)

