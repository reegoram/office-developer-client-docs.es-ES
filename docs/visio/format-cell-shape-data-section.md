---
title: Celda Format (Sección de datos de formas)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251340
localization_priority: Normal
ms.assetid: c36fc895-5577-59f6-0ff5-5892ca81a58f
description: Especifica el formato de un elemento de datos de formas que puede ser una cadena, una lista fija, un número, una lista variable, una fecha u hora, una duración o una moneda.
ms.openlocfilehash: 48342f21a107ff78fed2347fb679ed8199526056
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2018
ms.locfileid: "19822212"
---
# <a name="format-cell-shape-data-section"></a>Celda Format (sección Datos de formas)

Especifica el formato de un elemento de datos de formas que puede ser una cadena, una lista fija, un número, una lista variable, una fecha u hora, una duración o una moneda.
  
## <a name="remarks"></a>Comentarios

|**Tipo de elemento de datos de formas**|**Valor**|**Contenido de la celda Format**|
|:-----|:-----|:-----|
| Cadena  <br/> | 0  <br/> | Imagen de formato adecuado para el tipo de datos.  <br/> |
| Lista fija  <br/> | 1  <br/> | Elementos que aparecen en la lista, separados mediante signos de punto y coma.  <br/> |
| Número  <br/> | 2  <br/> | Imagen de formato adecuado para el tipo de datos.  <br/> |
| Lista variable  <br/> | 4  <br/> | Elementos que aparecen en la lista, separados mediante signos de punto y coma.  <br/> |
| Fecha u hora  <br/> | 5  <br/> | Imagen de formato adecuado para el tipo de datos.  <br/> |
| Duración  <br/> | 6  <br/> | Imagen de formato adecuado para el tipo de datos.  <br/> |
| Moneda  <br/> | 7  <br/> | Imagen de formato adecuado para el tipo de datos.  <br/> |
   
Como ejemplo para especificar una imagen de formato adecuado para el tipo de datos, la imagen de formato "# #/4 UU" muestra el número 12,43 pulgadas como 12 2/4 PULGADAS. Para obtener más información sobre cómo especificar una imagen de formato, vea [Imágenes de formato](about-format-pictures.md).
  
Un ejemplo de cómo especificar elementos para una lista es: "Ingeniería;Recursos humanos;Ventas;Marketing".
  
Los valores de fecha (Type = 5) se muestran con formato de fecha corta. Los valores de moneda (Type = 7) usan la configuración actual del usuario del cuadro **Moneda**, situado en la ficha **Opciones regionales** del elemento **Configuración regional y de idioma** en el **Panel de control**.
  
Un número (Type = 2) puede representar una dimensión, un escalar, un ángulo, una fecha, una hora o una moneda. Para asegurar que el número de entrada sea siempre tratado como una fecha, hora o moneda, utilice la función DATETIME o CY en la celda Format en lugar de un formato de imagen.
  
Para obtener una referencia a la celda Format por su nombre desde otra fórmula, o desde un programa mediante la propiedad **CellsU**, utilice: 
  
|||
|:-----|:-----|
| Nombre de celda:  <br/> | De propiedades.  *nombre* . Formato donde de propiedades.  *nombre* es el nombre de fila  <br/> |
   
Para obtener una referencia a la celda Format por su índice desde un programa, utilice la propiedad **CellsSRC** con los argumentos siguientes: 
  
|||
|:-----|:-----|
| Índice de sección:  <br/> |**visSectionProp** <br/> |
| Índice de fila:  <br/> |**visRowProp** +  *i* donde *i* = 0, 1, 2...  <br/> |
| Índice de celda:  <br/> |**visCustPropsFormat** <br/> |
   

