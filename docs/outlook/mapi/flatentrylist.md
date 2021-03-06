---
title: FLATENTRYLIST
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FLATENTRYLIST
api_type:
- COM
ms.assetid: b465d015-9b62-4986-b0df-118121f60602
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 371d0305f8f00e66704bae03f93857c7275b6a10
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589822"
---
# <a name="flatentrylist"></a>FLATENTRYLIST

**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Contiene una matriz de estructuras [FLATENTRY](flatentry.md) . 
  
|||
|:-----|:-----|
|Archivo de encabezado:  <br/> |Mapidefs.h  <br/> |
|Macros relacionadas:  <br/> |[CbFLATENTRYLIST](cbflatentrylist.md), [CbNewFLATENTRYLIST](cbnewflatentrylist.md) <br/> |
   
```cpp
typedef struct
{
  ULONG cEntries;
  ULONG cbEntries;
  BYTE abEntries[MAPI_DIM];
} FLATENTRYLIST, FAR *LPFLATENTRYLIST;

```

## <a name="members"></a>Members

**cEntries**
  
> Recuento de las estructuras **FLATENTRY** en la matriz descritos por el miembro **abEntries** . 
    
**cbEntries**
  
> Número de bytes de la matriz descritos por **abEntries**. 
    
**abEntries**
  
> Matriz de bytes que contiene una o más estructuras **FLATENTRY** , organizado de un extremo a extremo. 
    
## <a name="remarks"></a>Comentarios

En la matriz **abEntries** , cada estructura **FLATENTRY** se alinea en un límite alineado con naturalidad. Bytes adicionales se incluyen como relleno para realizar la alineación natural seguro entre los dos estructuras **FLATENTRY** . La primera estructura **FLATENTRY** en la matriz siempre se alinea correctamente debido a que el desplazamiento del miembro **abEntries** es 8. Para calcular el desplazamiento de la estructura siguiente, utilice el tamaño de la primera entrada que se redondea hacia arriba hasta el próximo múltiplo de 4. Utilice la macro [CbFLATENTRY](cbflatentry.md) para calcular el tamaño de una estructura **FLATENTRY** . 
  
Por ejemplo, la segunda estructura **FLATENTRY** se inicia en una posición de desplazamiento que consta del desplazamiento de la primera entrada y la longitud de la primera entrada redondeada a los siguientes cuatro bytes. La longitud de la primera entrada es la longitud de su miembro **cb** más la longitud de su miembro **abEntry** . 
  
El ejemplo de código siguiente indica cómo calcular los desplazamientos en una estructura **FLATENTRYLIST** . Se supone que _lpFlatEntry_ es un puntero a la primera estructura de la lista. 
  
```cpp
(offsetof(lpFlatEntry->ab) // for example, 4
+ lpFlatEntry->cb // size of lpFlatEntry->ab 
+ 4) & ~3 // round to next 4 byte boundary
```

## <a name="see-also"></a>Recursos adicionales

- [FLATENTRY](flatentry.md)
- [Propiedad canónica PidTagReplyRecipientEntries](pidtagreplyrecipiententries-canonical-property.md)
- [Estructuras MAPI](mapi-structures.md)

