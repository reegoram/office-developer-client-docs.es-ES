---
title: Celda IsSnapTarget (Sección de propiedades de grupo)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251626
localization_priority: Normal
ms.assetid: b58131f6-a566-d9ca-bad4-4f4b66e03aaf
description: Determina si las formas se ajustan en un grupo o dentro de él.
ms.openlocfilehash: 89536923617f80768d7c14658cb07c97595824ea
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2018
ms.locfileid: "19822380"
---
# <a name="issnaptarget-cell-group-properties-section"></a>Celda IsSnapTarget (sección Propiedades de grupo)

Determina si las formas se ajustan en un grupo o dentro de él.
  
|**Valor**|**Descripción**|
|:-----|:-----|
|TRUE  <br/> |Habilitar el ajuste a las formas dentro de un grupo.  <br/> |
|FALSE  <br/> |Ajustar sólo al grupo.  <br/> |
   
## <a name="remarks"></a>Observaciones

También puede ajustar este valor si selecciona un grupo, hace clic en **Comportamiento** en la ficha [Programador](run-in-developer-mode-display-the-developer-tab.md) y, a continuación, activa la casilla **Ajustar a las formas pertenecientes**. 
  
Para obtener una referencia a la celda IsSnapTarget por su nombre desde otra fórmula, o desde un programa mediante la propiedad **CellsU**, utilice: 
  
|||
|:-----|:-----|
|Nombre de celda:  <br/> |IsSnapTarget  <br/> |
   
Para obtener una referencia desde un programa a la celda IsSnapTarget por su índice, utilice la propiedad **CellsSRC** con los argumentos siguientes: 
  
|||
|:-----|:-----|
|Índice de sección:  <br/> |**visSectionObject** <br/> |
|Índice de fila:  <br/> |**visRowGroup** <br/> |
|Índice de celda:  <br/> |**visGroupIsSnapTarget** <br/> |
   

