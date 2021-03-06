---
title: SCommentRestriction
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SCommentRestriction
api_type:
- COM
ms.assetid: 07631ae1-981e-4c8e-a30b-1213904fe079
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 84fb79b1922669db9c8e5d518a833a6866f11cea
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589185"
---
# <a name="scommentrestriction"></a>SCommentRestriction

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Describe una restricción de comentario, que se usa para realizar anotaciones en una restricción. 
  
|||
|:-----|:-----|
|Archivo de encabezado:  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SCommentRestriction
{
  ULONG          cValues;
  LPSRestriction lpRes;
  LPSPropValue   lpProp;
} SCommentRestriction;

```

## <a name="members"></a>Members

 **cValues**
  
> Recuento de valores de propiedad en la matriz indicada por el miembro **lpProp** . 
    
 **lpRes**
  
> Puntero a una estructura [SRestriction](srestriction.md) . 
    
 **lpProp**
  
> Puntero a una matriz de estructuras [SPropValue](spropvalue.md) , cada uno con la etiqueta de la propiedad y el valor de una propiedad con nombre. 
    
## <a name="remarks"></a>Comentarios

La estructura **SCommentRestriction** asocia un objeto junto con un conjunto de propiedades con nombre. Restricciones de comentario son a diferencia de otras restricciones debido a que no se evalúan. Es decir, se tendrán en cuenta en el método [IMAPITable:: Restrict](imapitable-restrict.md) . No hay ningún efecto en las filas devueltas por el método [IMAPITable:: QueryRows](imapitable-queryrows.md) después de que se ha realizado una llamada **IMAPITable:: Restrict** . 
  
La estructura de **SCommentRestriction** puede usarse para mantener la información específica de la aplicación con una restricción de cuando se guarda en el disco. Por ejemplo, un cliente de guardar el nombre de una propiedad con nombre que se usa en una restricción de propiedad puede hacerlo en una estructura **SCommentRestriction** . Guardar un nombre de propiedad no es posible en una restricción de propiedad debido a que la estructura [SPropertyRestriction](spropertyrestriction.md) asociada contiene sólo la etiqueta de propiedad. 
  
Para obtener más información sobre la estructura de **SCommentRestriction** y restricciones en general, vea [Acerca de las restricciones](about-restrictions.md). 
  
## <a name="see-also"></a>Recursos adicionales



[SPropValue](spropvalue.md)
  
[SRestriction](srestriction.md)
  
[SPropertyRestriction](spropertyrestriction.md)


[Estructuras MAPI](mapi-structures.md)

