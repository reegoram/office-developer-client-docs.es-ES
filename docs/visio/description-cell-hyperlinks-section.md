---
title: Celda Description (Sección de hipervínculos)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm230
localization_priority: Normal
ms.assetid: 2f571c65-6b7a-5a3a-c075-3c52d3ab989b
description: Representa una cadena de texto descriptivo para un hipervínculo.
ms.openlocfilehash: b58e6dc3ec2fc3b64db00e0f19e0718fe897aaa3
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396627"
---
# <a name="description-cell-hyperlinks-section"></a>Celda Description (sección Hipervínculos)

Representa una cadena de texto descriptivo para un hipervínculo. 
  
## <a name="remarks"></a>Observaciones

Use esta celda para almacenar comentarios acerca del hipervínculo; Por ejemplo, "vínculo a nuestro sitio Web de precio".
  
También puede usar el cuadro de diálogo **Hipervínculos** para establecer el valor de esta celda (haga clic en **Hipervínculo** en la ficha **Insertar**). 
  
Para obtener una referencia a la celda Description por su nombre desde otra fórmula, o desde un programa mediante la propiedad **CellsU**, utilice: 
  
|||
|:-----|:-----|
| Nombre de celda:  <br/> | Hipervínculo.  *Nombre* . Descripción donde hipervínculo.  *Nombre* es el nombre de la fila de hipervínculo  <br/> |
   
Para obtener una referencia a la celda Description por su índice desde un programa, utilice la propiedad **CellsSRC** con los argumentos siguientes: 
  
|||
|:-----|:-----|
| Índice de sección:  <br/> |**visSectionHyperlink** <br/> |
| Índice de fila:  <br/> |**visRow1stHyperlink** +  *i* donde *i* = 0, 1, 2...  <br/> |
| Índice de celda:  <br/> |**visHLinkDescription** <br/> |
   

