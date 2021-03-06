---
title: Sección del archivo de configuración de formulario [Verbos]
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e7e1f371-9e9a-4bec-a0b3-87753a16f5e0
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: 6a06283e3eb072e1f502d0b1bd303ce9f0733578
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583977"
---
# <a name="form-configuration-file-verbs-section"></a>Sección del archivo de configuración de formulario [Verbos]

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
La sección **[verbos]** enumera todo el conjunto de verbos admitidos por el formulario. El formato de la sección **[verbos]** es: 
  
 **[Verbos]**
  
 **Verb1** =  _cadena_
  
Siguiente es un ejemplo de una sección **[verbos]** . 
  
```cpp
[Verbs]
Verb1=1
Verb2=2

```

Se define cada verbo en un independiente **[verbo.** _cadena_ sección **]** . A **[verbo.** _cadena_ **]** sección describe un solo verbo ofrecido por el formulario. La entrada **DisplayName** en un **[verbo.** _cadena_ sección **]** especifica el nombre del comando que se muestra en la interfaz de usuario. La entrada de **código** se corresponde con el número de verbo que se pasa en el método [IMAPIForm::DoVerb](imapiform-doverb.md) . La sintaxis de la **[verbo.** _cadena_ sección **]** es: 
  
 **[Verbo.** _cadena_ **]**
  
 **DisplayName** =  _muestra la cadena_
  
 **Código** =  _entero_
  
 **Marcas de** =  _entero_
  
 **Se utilizaron atributos** =  _entero_
  
A continuación se incluye un ejemplo de un **[verbo.** _cadena_ sección **]** . 
  
```cpp
[Verb.1]
DisplayName=Reply
code=1
Flags=0
Attribs=2
[Verb.2]
DisplayName=Delete
Code=2
Flags=0
Attribs=2

```

Verbos enumerados en esta sección se recuperan mediante un cliente mediante el [método IMAPIFormInfo::CalcVerbSet](imapiforminfo-calcverbset.md). Verbos se activan al llamar al método [IMAPIForm::DoVerb](imapiform-doverb.md) del formulario y pasar el número de código del verbo que se debe realizar. 
  

