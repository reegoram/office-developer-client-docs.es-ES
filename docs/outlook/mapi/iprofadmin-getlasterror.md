---
title: IProfAdminGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProfAdmin.GetLastError
api_type:
- COM
ms.assetid: bb161d7b-ae5b-4f8e-a506-8346ac5e583d
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: 65bf7debcae1367ccad9e109242fd4a72839a94e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584929"
---
# <a name="iprofadmingetlasterror"></a>IProfAdmin::GetLastError

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Devuelve una estructura [MAPIERROR](mapierror.md) que contiene información sobre el error anterior que se produjeron en un objeto de administración de perfiles. 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a>Parámetros

 _hResult_
  
> [entrada] Un tipo de datos HRESULT que contiene el valor de error generado en la llamada al método anterior.
    
 _ulFlags_
  
> [entrada] Una máscara de bits de indicadores que controla el tipo de cadenas devueltas. Se puede establecer la marca siguiente:
    
MAPI_UNICODE. 
  
> Las cadenas en la estructura [MAPIERROR](mapierror.md) devuelta en el parámetro _lppMAPIError_ están en formato Unicode. Si no está establecido el indicador MAPI_UNICODE., las cadenas están en formato ANSI. 
    
 _lppMAPIError_
  
> [out] Un puntero a un puntero a la estructura **MAPIERROR** que contiene información de versión, el componente y el contexto para el error. El parámetro _lppMAPIError_ se puede establecer en NULL si no hay ninguna estructura **MAPIERROR** para devolver. 
    
## <a name="return-value"></a>Valor devuelto

S_OK 
  
> La llamada se ha realizado correctamente y devuelva el valor esperado o los valores.
    
MAPI_E_BAD_CHARWIDTH 
  
> Se ha establecido el indicador MAPI_UNICODE y la implementación no es compatible con Unicode, o bien, no se ha establecido MAPI_UNICODE y la implementación admite sólo Unicode.
    
## <a name="remarks"></a>Comentarios

El método **IProfAdmin::GetLastError** recupera información sobre el último error devuelto desde una llamada al método para el objeto de administración de perfiles. 
  
## <a name="notes-to-callers"></a>Notas para los llamadores

Puede usar la estructura **MAPIERROR** , si MAPI proporciona uno, indicada por el sólo de si de parámetro _lppMAPIError_ **GetLastError** devuelve S_OK. En ocasiones, MAPI no puede determinar qué era el último error o no tiene nada más para informar sobre el error. En esta situación, se devuelve un puntero a NULL en _lppMAPIError_. 
  
Para liberar toda la memoria asignada por MAPI para la estructura **MAPIERROR** , llame a la función [MAPIFreeBuffer](mapifreebuffer.md) . 
  
Para obtener más información acerca del método **GetLastError** , vea [Uso de errores extendido](mapi-extended-errors.md).
  
## <a name="see-also"></a>Recursos adicionales



[MAPIERROR](mapierror.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IProfAdmin : IUnknown](iprofadminiunknown.md)

