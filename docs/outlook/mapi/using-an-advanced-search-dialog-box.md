---
title: Uso de un cuadro de diálogo Búsqueda avanzada
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c9a156e6-3472-4409-a4ba-3a1a65b7bdcd
description: '�ltima modificaci�n: s�bado, 23 de julio de 2011'
ms.openlocfilehash: 3c27b859f6d056d3b9a98bd4d71db8e500dff696
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2018
ms.locfileid: "19820955"
---
# <a name="using-an-advanced-search-dialog-box"></a>Uso de un cuadro de diálogo Búsqueda avanzada

  
  
**Se aplica a**: Outlook 
  
Algunos contenedores de la libreta de direcciones compatible con una capacidad de búsqueda avanzada que permite a los clientes buscar en las propiedades que no sean **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)). Contenedores de libretas de direcciones que admiten búsquedas avanzadas tienen una propiedad de objeto de contenedor denominada **PR_SEARCH** ([PidTagSearch](pidtagsearch-canonical-property.md)). Este objeto de contenedor proporciona acceso a una tabla para mostrar que describe el cuadro de diálogo de búsqueda: un cuadro de diálogo se usa para escribir y editar los criterios de búsqueda avanzada.
  
 **Para realizar una búsqueda avanzada en un contenedor de la libreta de direcciones**
  
1. Llamar al método [IMAPIProp::OpenProperty](imapiprop-openproperty.md) del contenedor, especificando **PR_SEARCH** para la etiqueta de propiedad y IID_IMAPIContainer para el identificador de interfaz. 
    
2. Llamar al método **IMAPIProp::OpenProperty** del objeto de la búsqueda, especificando **PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) para la etiqueta de propiedad y IID_IMAPITable para el identificador de interfaz. 
    
3. Llamar al método [IMAPIProp::SetProps](imapiprop-setprops.md) del objeto de búsqueda para establecer los valores de las propiedades que se utilizará en la búsqueda avanzada. 
    
4. Llamar al método [IMAPIProp::SaveChanges](imapiprop-savechanges.md) del objeto de búsqueda para guardar los criterios de búsqueda avanzada. 
    
Esta secuencia de llamadas da como resultado una restricción que están disponibles cuando un cliente llama (método) **es posible GetSearchCriteria** del objeto de búsqueda. 
  
