---
title: Celda Invisible (sección de acciones)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60046
localization_priority: Normal
ms.assetid: 070b4468-c907-b201-1633-1d3e10ecc2b2
description: Indica si la acción está visible en el menú contextual o de etiqueta de acción.
ms.openlocfilehash: 8749b7d6db4a932b97c68ab5cf30b879a57d28f2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2018
ms.locfileid: "19822347"
---
# <a name="invisible-cell-actions-section"></a>Celda Invisible (sección Acciones)

Indica si la acción está visible en el menú contextual o de etiqueta de acción. 
  
> [!NOTE]
> En versiones anteriores de Microsoft Visio, las etiquetas de acción se denominaban etiquetas inteligentes. 
  
|**Valor**|**Descripción**|
|:-----|:-----|
|TRUE  <br/> |La acción no está visible en el menú.  <br/> |
|FALSE  <br/> |La acción está visible en el menú (valor predeterminado).  <br/> |
   
## <a name="remarks"></a>Observaciones

Para obtener una referencia a la celda Invisible por su nombre desde otra fórmula, o desde un programa mediante la propiedad **CellsU**, use: 
  
|||
|:-----|:-----|
|Nombre de celda:  <br/> |Acciones. *nombre* . Acciones de Invisiblewhere.  *nombre* es el nombre de la fila de acciones  <br/> |
   
Para obtener una referencia desde un programa a la celda Invisible por su índice, utilice la propiedad **CellsSRC** con los argumentos siguientes: 
  
|||
|:-----|:-----|
|Índice de sección:  <br/> |**visSectionAction** <br/> |
|Índice de fila:  <br/> |**visRowAction** +  *i* donde *i* = 0, 1, 2...  <br/> |
|Índice de celda:  <br/> |**visActionInvisible** <br/> |
   

