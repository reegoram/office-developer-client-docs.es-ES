---
title: IMAPITableQuerySortOrder
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.QuerySortOrder
api_type:
- COM
ms.assetid: 7b4ca523-0703-417c-8586-c4324c200020
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: 48ca692779fb53cab386d8a18b5f0a50e11d531c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569438"
---
# <a name="imapitablequerysortorder"></a>IMAPITable::QuerySortOrder

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Recupera el criterio de ordenación actual para una tabla.
  
```cpp
HRESULT QuerySortOrder(
LPSSortOrderSet FAR * lppSortCriteria
);
```

## <a name="parameters"></a>Parámetros

 _lppSortCriteria_
  
> [out] Puntero a un puntero a la estructura de [SSortOrderSet](ssortorderset.md) que contiene el criterio de ordenación actual. 
    
## <a name="return-value"></a>Valor devuelto

S_OK 
  
> El criterio de ordenación actual se devolvió correctamente.
    
MAPI_E_BUSY 
  
> Otra operación está en curso que impide que la operación de recuperación de ordenación orden de inicio. Debe ser permite la operación en curso para llevar a cabo o se debe detener.
    
## <a name="remarks"></a>Comentarios

El método **IMAPITable::QuerySortOrder** recupera el criterio de ordenación actual para una tabla. Criterios de ordenación se describen con una estructura [SSortOrderSet](ssortorderset.md) . 
  
- El miembro **cSorts** de la estructura **SSortOrderSet** se puede establecer en cero si: 
    
- La tabla no está ordenada.
    
- No hay ninguna información acerca de cómo se ordena la tabla.
    
- La estructura de **SSortOrderSet** no es adecuada para describir el criterio de ordenación. 
    
## <a name="notes-to-implementers"></a>Notas para los implementadores

Si se realiza una llamada al método [SortTable](imapitable-sorttable.md) con una estructura **SSortOrderSet** que contiene cero columnas en el criterio de ordenación, quite el criterio de ordenación actual y aplicar el orden de forma predeterminada, si hay alguno. En llamadas posteriores a **QuerySortOrder**, puede elegir si se debe devolver cero o más columnas de la clave de ordenación. Puede devolver más columnas que se encuentran en la vista actual.
  
Para obtener más información acerca de la ordenación, vea [Ordenar y la categorización](sorting-and-categorization.md).
  
## <a name="see-also"></a>Recursos adicionales



[IMAPITable::SortTable](imapitable-sorttable.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[SSortOrderSet](ssortorderset.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)

