---
title: IMAPIFormMgrGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormMgr.GetLastError
api_type:
- COM
ms.assetid: 5d908771-ec16-444d-a9b6-44cc75a4d715
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: 15208ac0bf07b0f0e67284af98b543676c1b3dd6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579350"
---
# <a name="imapiformmgrgetlasterror"></a>IMAPIFormMgr::GetLastError

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Devuelve una estructura [MAPIERROR](mapierror.md) que contiene información sobre el error anterior generado por el objeto de administrador de formulario. 
  
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
  
> Las cadenas en la estructura **MAPIERROR** devuelta en el parámetro _lppMAPIError_ están en formato Unicode. Si no está establecido el indicador MAPI_UNICODE., las cadenas están en formato ANSI. 
    
 _lppMAPIError_
  
> [out] Un puntero a un puntero a la estructura **MAPIERROR** devuelta que contiene información de versión, el componente y el contexto para el error. Este parámetro puede establecerse en NULL si no hay ninguna estructura **MAPIERROR** para devolver. 
    
## <a name="return-value"></a>Valor devuelto

S_OK 
  
> La llamada se ha realizado correctamente y devuelva el valor esperado o los valores.
    
MAPI_E_BAD_CHARWIDTH 
  
> Se ha establecido el indicador MAPI_UNICODE y **GetLastError** no es compatible con Unicode, o bien, no se ha establecido MAPI_UNICODE y **GetLastError** admite sólo Unicode. 
    
## <a name="remarks"></a>Comentarios

El método **IMAPIFormMgr::GetLastError** proporciona información acerca de una llamada de método anteriores que no se pudo. Los autores de llamadas pueden proporcionar a sus usuarios con información detallada sobre el error mediante la inclusión de los datos de la estructura **MAPIERROR** en un cuadro de diálogo. 
  
## <a name="notes-to-callers"></a>Notas para los llamadores

Puede usar la estructura **MAPIERROR** indicada por el parámetro _lppMAPIError_ si MAPI proporciona uno sólo si **GetLastError** devuelve S_OK. En ocasiones, MAPI no puede determinar qué era el último error o no tiene nada más para informar sobre el error. En esta situación, se devuelve NULL en _lppMAPIError_ en su lugar. 
  
Para obtener más información acerca del método **GetLastError** , vea [Uso de errores extendido](mapi-extended-errors.md).
  
## <a name="see-also"></a>Recursos adicionales



[MAPIERROR](mapierror.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMAPIFormMgr : IUnknown](imapiformmgriunknown.md)

