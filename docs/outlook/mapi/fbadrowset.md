---
title: FBadRowSet
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FBadRowSet
api_type:
- COM
ms.assetid: 3890dd50-e6ca-4859-bada-f6752ab61d41
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: e86e9fbf4901b5944775886f38db1ba12c4b122d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590963"
---
# <a name="fbadrowset"></a>FBadRowSet

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Valida todas las filas de tabla incluidas en un conjunto de filas de la tabla.
  
|||
|:-----|:-----|
|Archivo de encabezado:  <br/> |Mapival.h  <br/> |
|Se implementa mediante:  <br/> |MAPI  <br/> |
|Llamado por:  <br/> |Proveedores de servicios  <br/> |
   
```cpp
BOOL FBadRowSet(
  LPSRowSet lpRowSet
);
```

## <a name="parameters"></a>Parámetros

 _lpRowSet_
  
> [entrada] Puntero a una estructura [SRowSet](srowset.md) que identifica el conjunto que se va a validar de filas. Si el puntero es NULL, la estructura no es válida. 
    
## <a name="return-value"></a>Valor devuelto

TRUE 
  
> Una fila del conjunto de filas especificado no es válida o el propio conjunto de filas no es válido. 
    
FALSE 
  
> Las filas del conjunto de fila especificada y el propio conjunto de filas son válidas.
    
## <a name="see-also"></a>Recursos adicionales



[FBadRow](fbadrow.md)

