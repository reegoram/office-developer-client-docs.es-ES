---
title: Celda IsDropTarget (Sección de propiedades de grupo)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm495
localization_priority: Normal
ms.assetid: 8140fc7b-b99c-54bb-7af3-7de6fcdae7d3
description: Determina si el grupo permite agregar una forma soltándola en él.
ms.openlocfilehash: 326ead15bcdc72797853daee797d8f08d459a638
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2018
ms.locfileid: "19822365"
---
# <a name="isdroptarget-cell-group-properties-section"></a>Celda IsDropTarget (sección Propiedades de grupo)

Determina si el grupo permite agregar una forma soltándola en él.
  
|**Valor**|**Descripción**|
|:-----|:-----|
|TRUE  <br/> |Permite agregar una forma a un grupo soltándola en él.  <br/> |
|FALSE  <br/> |No permite soltar la forma en el grupo.  <br/> |
   
## <a name="remarks"></a>Observaciones

También puede ajustar este valor si selecciona el grupo, hace clic en **Comportamiento** en la ficha [Programador](run-in-developer-mode-display-the-developer-tab.md) y, a continuación, selecciona la casilla **Aceptar formas colocadas**. 
  
Para agregar una forma a un grupo colocándola en él, también debe habilitar un comportamiento de forma similar. Debe seleccionar la forma, hacer clic en **Comportamiento** en la ficha [Programador](run-in-developer-mode-display-the-developer-tab.md) y, a continuación, activar la casilla **Agregar formas a un grupo al colocarlas**. Este valor se almacena en la celda IsDropSource en la sección de varios. 
  
Para obtener una referencia a la celda IsDropTarget por su nombre desde otra fórmula, o desde un programa mediante la propiedad **CellsU**, utilice: 
  
|||
|:-----|:-----|
|Nombre de celda:  <br/> |IsDropTarget  <br/> |
   
Para obtener una referencia desde un programa a la celda IsDropTarget por su índice, utilice la propiedad **CellsSRC** con los argumentos siguientes: 
  
|||
|:-----|:-----|
|Índice de sección:  <br/> |**visSectionObject** <br/> |
|Índice de fila:  <br/> |**visRowGroup** <br/> |
|Índice de celda:  <br/> |**visGroupIsDropTarget** <br/> |
   

