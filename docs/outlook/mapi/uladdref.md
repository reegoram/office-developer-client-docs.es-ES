---
title: UlAddRef
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.UlAddRef
api_type:
- COM
ms.assetid: 9b897cbc-90b2-4c60-b5f1-dc78e7e7952d
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: baf45fa33ca085f51a6f9c20f72ec1fd1545ad79
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592377"
---
# <a name="uladdref"></a>UlAddRef

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Proporciona una manera alternativa para invocar el método OLE **IUnknown:: AddRef**. 
  
|||
|:-----|:-----|
|Archivo de encabezado:  <br/> |Mapidefs.h  <br/> |
|Se implementa mediante:  <br/> |MAPI  <br/> |
|Llamado por:  <br/> |Las aplicaciones cliente y los proveedores de servicios  <br/> |
   
```cpp
ULONG UlAddRef(
  LPVOID punk
);
```

## <a name="parameters"></a>Parámetros

 _pUnk_
  
> [entrada] Puntero a una interfaz derivada de la interfaz **IUnknown** , en otras palabras cualquier interfaz MAPI. 
    
## <a name="return-value"></a>Valor devuelto

S_OK 
  
> La llamada se ha realizado correctamente y devuelva el valor esperado o los valores. 
    
MAPI_E_CALL_FAILED 
  
> Un error de origen desconocido o inesperado no puede completar la operación.
    
## <a name="remarks"></a>Comentarios

 **UlAddRef** devuelve el valor devuelto por el método **IUnknown:: AddRef** , que es el nuevo valor del recuento de referencias para la interfaz. El valor es distinto de cero. 
  
Para obtener más información acerca de **IUnknown:: AddRef**, vea [implementación de la interfaz IUnknown](implementing-the-iunknown-interface.md). 
  

