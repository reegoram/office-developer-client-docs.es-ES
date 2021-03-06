---
title: STnefProblem
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.STnefProblem
api_type:
- COM
ms.assetid: 3fe651b7-0ddf-42fd-8277-9224505be1a8
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 90829f8fff530d22a7dee68dc227655064147cee
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575332"
---
# <a name="stnefproblem"></a>STnefProblem

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Contiene información acerca de un problema de procesamiento de propiedad o un atributo que se ha producido durante la codificación o descodificación de una secuencia de formato de encapsulación neutro de transporte (TNEF).
  
|||
|:-----|:-----|
|Archivo de encabezado:  <br/> |TNEF.h  <br/> |
   
```cpp
typedef struct _STnefProblem
{
  ULONG ulComponent;
  ULONG ulAttribute;
  ULONG ulPropTag;
  SCODE scode;
} STnefProblem;

```

## <a name="members"></a>Members

 **ulComponent**
  
> El tipo de procesamiento durante el cual se produjera el problema. Si el problema se produjo durante el procesamiento de mensajes, el miembro **ulComponent** se establece en cero. Si el problema se produjo durante el procesamiento de datos adjuntos, **ulComponent** se establece igual al valor de **PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) de la correspondiente de los datos adjuntos.
    
 **ulAttribute**
  
> Atributo asociado con la propiedad indicada por el miembro de **ulPropTag** o cuando se produce el problema de procesamiento de TNEF cuando una encapsulación de descodificación bloquear, uno de los siguientes valores: 
    
 _attMAPIProps_
  
> Nivel de mensaje
    
 _attAttachment_
  
> Nivel de datos adjuntos
    
 **ulPropTag**
  
> Etiqueta de la propiedad de la propiedad que ha provocado el problema de procesamiento de TNEF, excepto cuando el problema se produce cuando la descodificación de un bloque de encapsulación, en la que los casos **ulPropTag** se establece en cero. 
    
 **SCODE**
  
> Valor de error que indica el problema detectado durante el procesamiento.
    
## <a name="remarks"></a>Comentarios

Si no se genera una estructura de **STnefProblem** durante el procesamiento de un atributo o propiedad, la aplicación puede continuar en la suposición de que se ha realizado correctamente en el procesamiento de ese atributo o propiedad. La única excepción se produce cuando surgió el problema durante la descodificación de un bloque de encapsulación. En este caso, la descodificación del componente correspondiente al bloque se ha detenido y descodificación continúa en otro componente. 
  
## <a name="see-also"></a>Recursos adicionales



[STnefProblemArray](stnefproblemarray.md)
  
[Propiedad canónica PidTagAttachNumber](pidtagattachnumber-canonical-property.md)


[Estructuras MAPI](mapi-structures.md)

