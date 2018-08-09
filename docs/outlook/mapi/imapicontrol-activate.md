---
title: IMAPIControlActivate
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIControl.Activate
api_type:
- COM
ms.assetid: 2b641030-2429-4217-a648-0a9f3d1a1b29
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: fb6cd23acdb81af250e7e6dfe6facf7226850363
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2018
ms.locfileid: "19817200"
---
# <a name="imapicontrolactivate"></a>IMAPIControl::Activate

  
  
**Hace referencia a**: Outlook 
  
Realiza una tarea como mostrar un cuadro de diálogo o iniciar una operación de programación cuando un usuario de la aplicación cliente hace clic en el control de botón.
  
```cpp
HRESULT Activate(
  ULONG ulFlags,
  ULONG_PTR ulUIParam
);
```

## <a name="parameters"></a>Par�metros

 _ulFlags_
  
> [entrada] Reservado; debe ser cero.
    
 _ulUIParam_
  
> [entrada] Identificador de la ventana principal del cuadro de diálogo en el que aparece el control de botón.
    
## <a name="return-value"></a>Valor devuelto

S_OK 
  
> El control botón se activó correctamente.
    
## <a name="remarks"></a>Comentarios

El método **IMAPIControl::Activate** realiza tareas siguiendo hacer clic en un usuario el control de botón. Una vez que se produce el clic, como parte del procesamiento de la tabla para mostrar, MAPI realiza una llamada a **Activar** después de la primera llamada [IMAPIControl::GetState](imapicontrol-getstate.md) para determinar si está habilitado el botón. 
  
Para obtener más información acerca de cómo implementar **Activar** y la otra [IMAPIControl: IUnknown](imapicontroliunknown.md) métodos, vea [Implementación de objeto de Control](control-object-implementation.md).
  
## <a name="see-also"></a>Vea también



[IMAPIControl::GetState](imapicontrol-getstate.md)
  
[IMAPIControl : IUnknown](imapicontroliunknown.md)
