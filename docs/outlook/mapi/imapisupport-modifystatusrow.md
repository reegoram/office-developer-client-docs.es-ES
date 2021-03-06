---
title: IMAPISupportModifyStatusRow
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.ModifyStatusRow
api_type:
- COM
ms.assetid: a304ca8f-e404-4535-be76-0b673f2061a0
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: 06a5c9de5c0ce4c0f936791086a731a55510a124
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592146"
---
# <a name="imapisupportmodifystatusrow"></a>IMAPISupport::ModifyStatusRow

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Modifica la tabla de estado al agregar una fila nueva o modificar una fila existente.
  
```cpp
HRESULT ModifyStatusRow(
ULONG cValues,
LPSPropValue lpColumnVals,
ULONG ulFlags
);
```

## <a name="parameters"></a>Parámetros

 _cValues_
  
> [entrada] El número de propiedades que se deben incluir en la fila de la tabla de estado nuevo o modificado. 
    
 _lpColumnVals_
  
> [entrada] Un puntero a una matriz de valores de propiedad que se describen las propiedades que se incluirán como columnas en la fila de la tabla de estado nuevo o modificado.
    
 _ulFlags_
  
> [entrada] Una máscara de bits de indicadores que controla cómo se procesa la información que define la fila de la tabla de estado. Se puede establecer la marca siguiente:
    
STATUSROW_UPDATE 
  
> Dirige MAPI para combinar las propiedades incluidas en la matriz indicada por _lpColumnVals_ con una fila de tabla de estado existente, en lugar de en una nueva fila. 
    
## <a name="return-value"></a>Valor devuelto

S_OK 
  
> La tabla de estado se ha actualizado correctamente.
    
## <a name="remarks"></a>Comentarios

El método **IMAPISupport::ModifyStatusRow** se implementa para todos los objetos de soporte técnico de proveedor de servicio. Proveedores de servicios de llamar a **ModifyStatusRow** en tiempo de inicio de sesión para agregar una fila a la tabla de estado y en otros momentos durante la sesión para actualizar la fila. **ModifyStatusRow** proporciona MAPI con la información necesaria para crear la tabla de estado. 
  
## <a name="notes-to-callers"></a>Notas para los llamadores

Establecer la marca STATUSROW_UPDATE cuando se llama a **ModifyStatusRow** para realizar cambios en las propiedades de la fila de tabla de estado existente. Al hacerlo, informa a MAPI que se transfieren sólo las columnas que se va a cambiar en el parámetro _lpColumnVals_ . 
  
Los clientes pueden usar la información en la tabla de estado para tener acceso a su objeto de estado. 
  
Para obtener una lista completa de las columnas que se deben incluir en la fila de la tabla de estado, vea [Las tablas de estado](status-tables.md).
  
## <a name="see-also"></a>Recursos adicionales



[IMAPISupport: IUnknown](imapisupportiunknown.md)

