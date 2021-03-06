---
title: Celda Bullet (Sección de párrafo)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm130
localization_priority: Normal
ms.assetid: 124a5ee1-6dd1-d17d-6f0e-dbaa5d95d9cd
description: Determina el estilo de viñetas.
ms.openlocfilehash: d3ecdd8e0f3780490f92766351b5ac94e875ae28
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2018
ms.locfileid: "19821695"
---
# <a name="bullet-cell-paragraph-section"></a>Celda Bullet (sección Párrafo)

Determina el estilo de viñetas.
  
|**Valor**|**Estilo de viñeta**|
|:-----|:-----|
|0  <br/> |Ninguno  <br/> |
|1  <br/> |![](media/IC_Bullet1_ZA07645847.gif)           <br/> |
|2  <br/> |![](media/IC_Bullet2_ZA07645848.gif)           <br/> |
|3  <br/> |![](media/IC_Bullet3_ZA07645849.gif)           <br/> |
|4  <br/> |![](media/IC_Bullet4_ZA07645851.gif)           <br/> |
|5  <br/> |![](media/IC_Bullet5_ZA07645852.gif)           <br/> |
|6  <br/> |![](media/IC_Bullet6_ZA07645853.gif)           <br/> |
|7  <br/> |![](media/IC_Bullet7_ZA07645854.gif)           <br/> |
   
|||
|:-----|:-----|
|Índice de sección:  <br/> |**visSectionParagraph** <br/> |
|Índice de fila:  <br/> |**visRowParagraph** +  *i* donde *i* = 0, 1, 2,...  <br/> |
|Índice de celda:  <br/> |**visBulletIndex** <br/> |
   
## <a name="remarks"></a>Comentarios

Asimismo, para establecer el valor de esta celda, haga clic con el botón secundario en una forma, elija **Formato**, haga clic en **Texto** y, a continuación, haga clic en la pestaña **Viñetas**. 
  
Para obtener una referencia a la celda Bullet por su nombre desde otra fórmula, o desde un programa mediante la propiedad **CellsU**, use: 
  
|||
|:-----|:-----|
|Nombre de celda:  <br/> |Para.Bullet [ *i* ] donde *i* = < 1 >, 2, 3,...  <br/> |
   
Para obtener una referencia a la celda Bullet por su índice desde un programa, utilice la propiedad **CellsSRC** con los argumentos siguientes: 
  

