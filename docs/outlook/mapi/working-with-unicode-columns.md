---
title: Trabajar con columnas Unicode
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2cd55464-263f-4f83-b874-524271773934
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: ffeee38920bf1c864b93e6513913c140cb658d8b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22595310"
---
# <a name="working-with-unicode-columns"></a>Trabajar con columnas Unicode

  
  
**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
Las cadenas de caracteres en las tablas se pueden representar mediante caracteres de 8 bits estándar, que son el tipo de propiedad PT_STRING8, o caracteres Unicode de 16 bits, que son propiedad de tipo PT_UNICODE. Los implementadores de tabla son libres de elegir si sus tablas admiten cadenas Unicode. Como Unicode agrega valor para los clientes y proveedores de servicios de ampliando el conjunto de características, se recomienda la compatibilidad con Unicode siempre que sea posible. 
  
Muchos métodos de tabla aceptan una marca que determina si los valores de propiedad de cadena se prevé que Unicode. En la entrada, si se especifica el indicador MAPI_UNICODE indica para el implementador de tabla que todos los valores de propiedad de cadena pasados con la llamada son cadenas Unicode y tienen tipos de propiedad de PT_UNICODE. En la salida, esta marca indica que todos los valores de propiedad de la cadena devuelta deben ser cadenas Unicode, si es posible. Si el marcador no tiene un significado para la entrada o salida depende del método. Los implementadores de tabla que no admiten Unicode y se pasan el indicador MAPI_UNICODE devolver el valor MAPI_E_BAD_CHAR_WIDTH.
  
## <a name="see-also"></a>Vea también



[Tablas MAPI](mapi-tables.md)

