---
title: IMSProviderCompareStoreIDs
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSProvider.CompareStoreIDs
api_type:
- COM
ms.assetid: c3e3cfaa-9c4a-482a-9411-9c4ab01d312f
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: 57b8438d655b3bc5b708fd7ed6734554a3a23ac4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585993"
---
# <a name="imsprovidercomparestoreids"></a>IMSProvider::CompareStoreIDs

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Compara dos mensajes almacén de los identificadores de entrada para determinar si hacen referencia al mismo objeto de almacenamiento.
  
```cpp
HRESULT CompareStoreIDs(
  ULONG cbEntryID1,
  LPENTRYID lpEntryID1,
  ULONG cbEntryID2,
  LPENTRYID lpEntryID2,
  ULONG ulFlags,
  ULONG FAR * lpulResult
);
```

## <a name="parameters"></a>Parámetros

 _cbEntryID1_
  
> [entrada] El tamaño, en bytes, del identificador de entrada indicada por el parámetro _lpEntryID1_ _._
    
 _lpEntryID1_
  
> [entrada] Un puntero para el primer identificador de entrada que se va a comparar.
    
 _cbEntryID2_
  
> [entrada] El tamaño, en bytes, del identificador de entrada indicada por el parámetro _lpEntryID2_ _._
    
 _lpEntryID2_
  
> [entrada] Un puntero para el segundo identificador de entrada que se va a comparar.
    
 _ulFlags_
  
> [entrada] Reservado; debe ser cero.
    
 _lpulResult_
  
> [out] Un puntero al resultado devuelto de la comparación. TRUE si los identificadores de dos entrada hacen referencia al mismo objeto; en caso contrario, es FALSE.
    
## <a name="return-value"></a>Valor devuelto

S_OK 
  
> La llamada se ha realizado correctamente y devuelva el valor esperado o los valores.
    
## <a name="remarks"></a>Comentarios

MAPI llama al método de **IMSProvider::CompareStoreIDs** cuando se procesa una llamada al método [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md) . **CompareStoreIDs** se llama en este momento para determinar qué sección de perfil, si hay alguna, está asociado con el almacén de mensajes que se ha abierto. Puede realizar una llamada **CompareStoreIDs** cuando no hay almacenes de mensaje están abiertos para un proveedor de almacén determinado. Además, también llamadas MAPI **CompareStoreIDs** cuando se procesa una llamada de proveedor de almacenamiento para el método [IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md) . 
  
Los identificadores de entrada que se comparan por **CompareStoreIDs** son ambos para el actual almacenan la biblioteca de vínculos dinámicos (DLL) del proveedor y son ambos identificadores de entrada de almacén no ajustado. Para obtener más información acerca de los identificadores de almacén de entrada de ajuste, consulte [IMAPISupport::WrapStoreEntryID](imapisupport-wrapstoreentryid.md).
  
Comparación de los identificadores de entrada es útil porque un objeto puede tener más de un identificador de entrada válido. Esto puede suceder, por ejemplo, después de instalar una nueva versión de un proveedor de almacén de mensajes. 
  
## <a name="see-also"></a>Recursos adicionales



[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)
  
[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)
  
[IMAPISupport::WrapStoreEntryID](imapisupport-wrapstoreentryid.md)
  
[IMSProvider : IUnknown](imsprovideriunknown.md)

