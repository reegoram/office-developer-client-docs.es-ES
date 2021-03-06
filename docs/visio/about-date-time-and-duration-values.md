---
title: Valores de fecha, hora y duración
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
f1_keywords:
- Vis_DSS.chm82251852
localization_priority: Normal
ms.assetid: b6951a92-f32a-5829-5e07-b277b7934df3
description: Puede realizar operaciones en fórmulas con valores de fecha, hora y duración. En Microsoft Visio, puede calcularse un solo valor a partir de una expresión de fecha y hora. Una expresión de fecha y hora es cualquier expresión que habitualmente se reconoce como fecha, hora o ambas, o una referencia a una celda que contiene tal expresión. Esto incluye las cadenas y números con apariencia de fecha y hora, y los valores de fecha y hora obtenidos de las funciones.
ms.openlocfilehash: 936055ed6d13b75bd0c42c95564046a76082ec0d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2018
ms.locfileid: "19821498"
---
# <a name="about-date-time-and-duration-values"></a>Información sobre los valores de duración, fecha y hora

Puede realizar operaciones en fórmulas con valores de fecha, hora y duración. En Microsoft Visio, puede calcularse un solo valor a partir de una expresión de fecha y hora. Una expresión de fecha y hora es cualquier expresión que habitualmente se reconoce como fecha, hora o ambas, o una referencia a una celda que contiene tal expresión. Esto incluye las cadenas y números con apariencia de fecha y hora, y los valores de fecha y hora obtenidos de las funciones.
  
En Visio, los valores de fecha y hora se almacenan internamente como un número de 64 bits de punto flotante. El valor situado a la izquierda del separador decimal representa el número de días transcurridos desde el 30 de diciembre de 1899. El valor a la derecha del separador decimal es la fracción de día a partir de la medianoche. El mediodía se representa con ,5.
  
Para utilizar fechas y horas en una expresión (en lugar de utilizar una constante), debe emplear las funciones adecuadas que las identifiquen como valores de fecha y hora.
  
## <a name="valid-dates"></a>Fechas válidas

||||
|:-----|:-----|:-----|
| "28/2"  <br/> | "2/28/99"  <br/> | "2/28/1999"  <br/> |
| "2-28"  <br/> | "2-28-99"  <br/> | "2-28/1999"  <br/> |
| "6 Mar 99"  <br/> | "6 Mar"  <br/> | "6 Mar 99"  <br/> |
| "1 de Enero de 99"  <br/> | "Ene 1, 99"  <br/> | "Ene 1, 1999"  <br/> |
| "Ene 00"  <br/> | "Enero, 2000"  <br/> | "Ene 1, 00"  <br/> |
   
## <a name="valid-times"></a>Horas válidas

||||
|:-----|:-----|:-----|
| "3:45"  <br/> | "3: 45:27"  <br/> | "7a"  <br/> |
| "7 am"  <br/> | "7 p"  <br/> | "7:30 PM"  <br/> |
   
## <a name="date-and-time-functions"></a>Funciones de fecha y hora

|**Función**|**Descripción**|
|:-----|:-----|
|[FECHA](date-function-visioshapesheet.md) <br/> | Convierte números en un valor de fecha.  <br/> |
|[DATETIME](datetime-function.md) <br/> | Convierte una cadena en un valor de fecha y hora.  <br/> |
|[VALFECHA](datevalue-function-visioshapesheet.md) <br/> | Convierte una cadena en un valor de fecha.  <br/> |
|[NOW](now-function-visioshapesheet.md) <br/> | Devuelve la fecha actual del sistema como un valor de fecha y hora.  <br/> |
|[TIEMPO](time-function-visioshapesheet.md) <br/> | Convierte números en un valor de hora.  <br/> |
|[VALHORA](timevalue-function-visioshapesheet.md) <br/> | Convierte una cadena en un valor de hora.  <br/> |
|[DÍA](day-function-visioshapesheet.md) <br/> | Devuelve el componente de día de una expresión de fecha y hora.  <br/> |
|[DAYOFYEAR](dayofyear-function.md) <br/> | Devuelve el número de día del año de una expresión de fecha y hora.  <br/> |
|[HORA](hour-function-visioshapesheet.md) <br/> | Devuelve el componente de hora de una expresión de fecha y hora.  <br/> |
|[MINUTO](minute-function-visioshapesheet.md) <br/> | Devuelve el componente de minutos de una expresión de fecha y hora.  <br/> |
|[MES](month-function-visioshapesheet.md) <br/> | Devuelve el componente de mes de una expresión de fecha y hora.  <br/> |
|[SEGUNDO](second-function-visioshapesheet.md) <br/> | Devuelve el componente de segundos de una expresión de fecha y hora.  <br/> |
|[DÍA DE LA SEMANA](weekday-function-visioshapesheet.md) <br/> | Devuelve el número de día de la semana de una expresión de fecha y hora.  <br/> |
|[AÑO](year-function-visioshapesheet.md) <br/> | Devuelve el componente de año de una expresión de fecha y hora.  <br/> |
   
## <a name="duration"></a>Duración

Es posible realizar operaciones que calculen una duración o el tiempo transcurrido. La duración se almacena internamente como número de días y una fracción de día. Por ejemplo, 1 semana, 7 días y 168 horas transcurridos se almacenan internamente como 7,0, pero se muestran con las unidades correspondientes.
  
Visio reconoce las unidades de duración enumeradas en la tabla siguiente.
  
|**Unit**|**Abbreviation**|**Abreviatura universal**|
|:-----|:-----|:-----|
| día transcurrido  <br/> | díat, dt.  <br/> | ed  <br/> |
| hora transcurrida  <br/> | horat, ht.  <br/> | eh  <br/> |
| minuto transcurrido  <br/> | minutot, mt.  <br/> | em  <br/> |
| segundo transcurrido  <br/> | segundot, st.  <br/> | es  <br/> |
| semana transcurrida  <br/> | semanat, st.  <br/> | ew  <br/> |
   
Puede agregar un valor de fecha y hora a una duración para calcular un nuevo valor de fecha y hora. Las fechas, horas y duraciones permiten realizar las operaciones que se muestran en la tabla siguiente:
  
|**Entrada**|**Resultado**|
|:-----|:-----|
| Fecha-hora +/- duración  <br/> | Valor de fecha y hora  <br/> |
| Duración +/- fecha-hora  <br/> | Valor de fecha y hora  <br/> |
| Duración +/- duración  <br/> | Valor de duración  <br/> |
| Fecha-hora + fecha-hora  <br/> | Valor de fecha y hora  <br/> |
| Fecha-hora - fecha-hora  <br/> | Valor de duración  <br/> |
   

