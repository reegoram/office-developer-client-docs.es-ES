---
title: IMSLogonCompareEntryIDs
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSLogon.CompareEntryIDs
api_type:
- COM
ms.assetid: 481812d6-8e94-4510-b288-55501dd5757c
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: c5b2d7db745cc270c0be7ee2184e86c6a4f97aad
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594302"
---
# <a name="imslogoncompareentryids"></a>IMSLogon::CompareEntryIDs

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Compara dos identificadores de entrada para determinar si hacen referencia al mismo objeto. MAPI hace referencia esta llamada a un proveedor de servicio únicamente si los identificadores únicos (UID) en ambos identificadores de entrada que se va a comparar son resueltos por dicho proveedor.
  
```cpp
HRESULT CompareEntryIDs(
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

Los proveedores de almacén de mensajes implementan el método **IMSLogon::CompareEntryIDs** para comparar dos identificadores de entrada para una entrada determinada en un almacén de mensajes para determinar si hacen referencia al mismo objeto. Si los identificadores de dos entrada hacer referencia al mismo objeto, **CompareEntryIDs** establece el parámetro _lpulResult_ en TRUE; Si hacen referencia a objetos diferentes, **CompareEntryIDs** establece _lpulResult_ en FALSE. 
  
 **CompareEntryIDs** es útil porque un objeto puede tener más de un identificador de entrada válido. Esto puede suceder, por ejemplo, después de instalar una nueva versión de un proveedor de almacén de mensajes. 
  
## <a name="see-also"></a>Recursos adicionales



[IMSLogon : IUnknown](imslogoniunknown.md)

