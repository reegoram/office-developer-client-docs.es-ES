---
title: SizedDtblPage
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SizedDtblPage
api_type:
- COM
ms.assetid: 47b2a69d-e902-429f-8b31-166b51aeaf7f
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: ae3f84c6b219c7becb88737f0d6c9fcb9722ea34
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584971"
---
# <a name="sizeddtblpage"></a>SizedDtblPage

**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Crea una estructura con nombre que incluye una estructura [DTBLPAGE](dtblpage.md) para describir un control de páginas con fichas, una etiqueta de un período especificado y una entrada de archivo de Ayuda de una longitud especificada. 
  
|||
|:-----|:-----|
|Archivo de encabezado:  <br/> |Mapidefs.h  <br/> |
|Estructura relacionado:  <br/> |**DTBLPAGE** <br/> |
   
```cpp
SizedDtblPage (n, n1, u)
```

## <a name="parameters"></a>Parámetros

_n_
  
> Longitud de la etiqueta de la ficha página.
    
_N1_
  
> Longitud de la entrada que aparece en el archivo Mapisvc.inf que identifica el archivo de ayuda que se utilizará junto con el control de la página con fichas.
    
_s_
  
> Nombre de la nueva estructura.
    
## <a name="remarks"></a>Comentarios

La macro **SizedDtblPage** le permite definir un control de páginas con fichas cuando se conoce el número de caracteres en la etiqueta asociada y la entrada del archivo de ayuda. Se crea la nueva estructura con los siguientes miembros: 
  
```cpp
DTBLPAGE dtblpage;
TCHAR lpszLabel[n];
TCHAR lpszComponent[n1];
```

Para utilizar un puntero a la estructura resultante de la macro **SizedDtblPage** como un puntero de estructura **DTBLPAGE** , realizar la conversión a la siguiente: 
  
```cpp
lpDtblPage = (LPDTBLPAGE) &SizedDtblPage;
```

## <a name="see-also"></a>Recursos adicionales

- [DTBLPAGE](dtblpage.md)
- [Macros relacionadas con estructuras](macros-related-to-structures.md)

