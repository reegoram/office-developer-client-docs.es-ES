---
title: IProxyStoreObjectUnwrapNoRef
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProxyStoreObject.UnwrapNoRef
api_type:
- COM
ms.assetid: 1122b6e0-e7e1-e68a-e090-435777343d04
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: ef9f506c1a95fec86c7f092b0299198e6149d3ba
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25382935"
---
# <a name="iproxystoreobjectunwrapnoref"></a>IProxyStoreObject::UnwrapNoRef

  
  
**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
Obtiene un puntero a un objeto de almacén de protocolo de acceso a mensajes de Internet (IMAP) no ajustado que proporciona acceso al archivo de carpetas personales (PST) subyacente sin invocar la sincronización y descarga de los elementos.
  
```cpp
HRESULT IProxyStoreObject::UnwrapNoRef (     LPVOID *ppvObject ); 
```

## <a name="parameters"></a>Parámetros

 _ppvObject_
  
> [out] Puntero a un [IMsgStore: IMAPIProp](imsgstoreimapiprop.md) objeto store que se no ajustado. 
    
## <a name="return-values"></a>Valores devueltos

S_OK
  
- La llamada se realizó correctamente y se ha devuelto un puntero a una interfaz no ajustado en _ppvObject_.
    
## <a name="remarks"></a>Comentarios

Sin primera apertura un almacén IMAP, obtener acceso a un mensaje en el almacén puede forzar la sincronización que intenta descargar el mensaje completo. Mediante el almacén no ajustado permite el acceso a los mensajes en su estado actual sin desencadenar una descarga.
  
Debido a que **UnwrapNoRef** no incrementa el recuento de referencias para este nuevo puntero al objeto de almacén no ajustado, después de llamar correctamente a **UnwrapNoRef**, se debe llamar a [IUnknown:: AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx) para mantener el recuento de referencia. 
  
## <a name="see-also"></a>Vea también



[IProxyStoreObject](iproxystoreobject.md)

