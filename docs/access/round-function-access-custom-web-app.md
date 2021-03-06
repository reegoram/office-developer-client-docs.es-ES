---
title: Función Round (aplicación web personalizada de Access)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4af7fbe2-ee34-4a52-b55e-ce3983313b5e
description: Devuelve un valor numérico, redondeado o truncado, con la longitud o precisión especificada.
ms.openlocfilehash: 5a3df4a4ddd7aace5edf886db5988704e5dd6af3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2018
ms.locfileid: "19815489"
---
# <a name="round-function-access-custom-web-app"></a>Función Round (aplicación web personalizada de Access)

Devuelve un valor numérico, redondeado o truncado, con la longitud o precisión especificada.
  
> [!IMPORTANT]
> Microsoft ya no recomienda crear ni usar aplicaciones web de Access en SharePoint. Como alternativa, considere la posibilidad de usar [Microsoft PowerApps](https://powerapps.microsoft.com/es-ES/) para crear soluciones empresariales sin código para la Web y dispositivos móviles. 
  
## <a name="syntax"></a>Sintaxis

 **Round** (*Number*, *Precision*  , [  *TruncateInsteadOfRound*  ]) 
  
La función **Round** contiene los siguientes argumentos. 
  
|**Nombre del argumento**|**Descripción**|
|:-----|:-----|
| *Número*  <br/> |Expresión numérica.  <br/> |
| *Precision*  <br/> |Precisión con la que se redondeará el argumento  *Number*  . El argumento  *Precision*  debe ser una expresión numérica. Cuando  *Precision*  sea un número positivo, el argumento  *Number*  se redondeará al número de posiciones decimales especificado por el valor de longitud. Cuando  *Precision*  sea un número negativo, el argumento  *Number*  se redondea en la izquierda de la coma, según especifique el valor de longitud.  <br/> |
| *TruncateInsteadOfRound*  <br/> |Tipo de operación que se va a realizar. Cuando se omite o se establece en 0, el argumento  *Number*  se redondea. Cuando se especifica un valor distinto de 0, el argumento  *Number*  se trunca. El valor predeterminado es 0.  <br/> |
   
## <a name="remarks"></a>Comentarios

 **Round** siempre devuelve un valor. Si el valor de longitud es negativo y mayor que el número de dígitos antes de la coma decimal, **Round** devuelve 0. 
  

