---
title: FBadProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- FBadProp
api_type:
- HeaderDef
ms.assetid: 929330c8-e6f2-4adf-a36e-fba18fa055d4
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 2fbff399e088edaf3ad864f0ec7fecda3af6bc8e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578853"
---
# <a name="fbadprop"></a>FBadProp

  
  
**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
Valida una propiedad especificada. 
  
|||
|:-----|:-----|
|Archivo de encabezado:  <br/> |Mapival.h  <br/> |
|Implementado por:  <br/> |MAPI  <br/> |
|Llamado por:  <br/> |Proveedores de servicios  <br/> |
   
```cpp
ULONG FBadProp(
  LPSPropValue lpprop
);
```

## <a name="parameters"></a>Parámetros

 _lpprop_
  
> [entrada] Una estructura [SPropValue](spropvalue.md) que define la propiedad que se va a validar. 
    
## <a name="return-value"></a>Valor devuelto

TRUE 
  
> La propiedad especificada no es válida. 
    
FALSE 
  
> La propiedad especificada es válida.
    
## <a name="remarks"></a>Comentarios

Un proveedor de servicios puede llamar a la función **FBadProp** por diversos motivos, por ejemplo, para prepararse para una llamada al método [IMAPIProp::SetProps](imapiprop-setprops.md) que establece una propiedad. **FBadProp** valida la propiedad especificada según el tipo de propiedad. Por ejemplo, si la propiedad es booleana, **FBadProp** se asegura de que el valor es TRUE o FALSE. Si la propiedad es binaria, **FBadProp** comprueba el puntero y el tamaño y se asegura de que se asigna correctamente. 
  
## <a name="see-also"></a>Vea también



[FBadPropTag](fbadproptag.md)

