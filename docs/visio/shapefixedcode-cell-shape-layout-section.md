---
title: Celda ShapeFixedCode (Sección de diseño de forma)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm880
localization_priority: Normal
ms.assetid: a1736a5c-421c-2bdb-b164-76a8cd06cc3d
description: Especifica el comportamiento de colocación de una forma que puede colocarse.
ms.openlocfilehash: 6ae83fa70cc545c88080ce27046bd8c226c060e3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2018
ms.locfileid: "19823140"
---
# <a name="shapefixedcode-cell-shape-layout-section"></a>Celda ShapeFixedCode (sección Diseño de forma)

Especifica el comportamiento de colocación de una forma que puede colocarse.
  
|**Valor**|**Modo de selección**|**Constante de automatización**|
|:-----|:-----|:-----|
|&amp;H1  <br/> |No mover esta forma cuando se coloquen mediante el cuadro de diálogo **Configurar diseño** .  <br/> |**visSLOFixedPlacement** <br/> |
|&amp;H2  <br/> |No mover esta forma y no permitir que se coloquen sobre ella otras formas que la quiten.  <br/> |**visSLOFixedPlow** <br/> |
|&amp;H4  <br/> |No mover esta forma y permitir colocar sobre ella otras formas que la quiten.  <br/> |**visSLOFixedPermeablePlow** <br/> |
|&amp;H20 (32)  <br/> |Omitir las ubicaciones de los puntos de conexión cuando se está enrutando.  <br/> |**visSLOFixedConnPtsIgnore** <br/> |
|&amp;H40 (64)  <br/> |Permitir el enrutamiento únicamente a los lados con puntos de conexión.  <br/> |**visSLOFixedConnPtsOnly** <br/> |
|&amp;H80 (128)  <br/> |No pegar al perímetro de esta forma. En lugar de ello, pegar al cuadro de alineación de la forma.  <br/> |**visSLOFixedNoFoldToShape** <br/> |
   
## <a name="remarks"></a>Comentarios

También puede establecer el valor de esta celda en la ficha de **colocación** en el cuadro de diálogo **comportamiento** (con una forma seleccionada, en la ficha [Programador](run-in-developer-mode-display-the-developer-tab.md) , en el grupo **Diseño de formas** , haga clic en **comportamiento**y, a continuación, haga clic en la ficha **colocación** ). 
  
Puede establecer cualquier combinación de estos valores para esta celda. Por ejemplo, puede escribir el valor 3 (&amp;H3), que elimina el movimiento al disponer formas mediante el cuadro de diálogo **Configurar diseño** (en la ficha **Diseño** , en el grupo **Diseño** , haga clic en **Página de diseño de Re**y, a continuación, haga clic en ** Más opciones de diseño** ) y cuando se colocan otras formas que puede colocarse en o cerca de la forma. 
  
En las versiones anteriores a Visio 2000, este comportamiento se establece mediante la celda ObjInteract, en la sección de varios. 
  
Para obtener una referencia a la celda ShapeFixedCode por su nombre desde otra fórmula, o desde un programa mediante la propiedad **CellsU**, use: 
  
|||
|:-----|:-----|
|Nombre de celda:  <br/> |ShapeFixedCode  <br/> |
   
Para obtener una referencia desde un programa a la celda ShapeFixedCode por su índice, utilice la propiedad **CellsSRC** con los argumentos siguientes: 
  
|||
|:-----|:-----|
|Índice de sección:  <br/> |**visSectionObject** <br/> |
|Índice de fila:  <br/> |**visRowShapeLayout** <br/> |
|Índice de celda:  <br/> |**visSLOFixedCode** <br/> |
   

