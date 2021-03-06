---
title: Función Format (aplicación web personalizada de Access)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 550fc235-f0b9-4d8e-805b-ce467821a8c9
description: Devuelve un valor con formato según un patrón especificado.
ms.openlocfilehash: 1739f87fd6e77c91aa66a64c0b7520fa6a641e95
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25387800"
---
# <a name="format-function-access-custom-web-app"></a>Función Format (aplicación web personalizada de Access)

Devuelve un valor con formato según un patrón especificado.
  
> [!NOTE]
> La característica de almacenamiento en la nube descrita en este artículo no es compatible con Office 2013 ni Office 2016 y puede provocar el siguiente error: >  *Estamos teniendo problemas con el servidor, por lo que ahora mismo no podemos agregar \< servicio \>. Inténtelo de nuevo más tarde.* > En el caso del almacenamiento en la nube para Office Online, Office para iOS y Office para Android, puede buscar en nuestro [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage). 
  
## <a name="syntax"></a>Sintaxis

 **Format** (*Expresión*, *Formato*) 
  
La función **Format** contiene los siguientes argumentos. 
  
|**Nombre de argumento**|**Descripción**|
|:-----|:-----|
| *Expresión*  <br/> |Expresión de un tipo de datos admitido para dar formato.  <br/> |
| *Formato*  <br/> | Un patrón de formato. El argumento de formato debe contener una cadena de formato válida, como una cadena de formato estándar (por ejemplo, "C" o "D"), o como un patrón de caracteres personalizados para fechas y valores numéricos (por ejemplo, "MMMM dd, aaaa (dddd)"). Para más información, consulte Comenatrios.  <br/> |
   
## <a name="remarks"></a>Comentarios

Para el parámetro  *Formato*  , puede pasar las cadenas que coincidan con cualquiera de los siguientes patrones: 
  
- [Cadenas de formato numérico estándar](https://msdn.microsoft.com/library/dwhawy9k%28v=vs.110%29.aspx)
    
- [Cadenas de formato numérico personalizado](https://msdn.microsoft.com/library/0c899ak8%28v=vs.110%29.aspx)
    
- [Cadenas de formato de fecha y hora estándar](https://msdn.microsoft.com/library/az4se3k1%28v=vs.110%29.aspx)
    
- [Cadenas de formato de fecha y hora personalizado](https://msdn.microsoft.com/library/8kb3ddd4%28v=vs.110%29.aspx)
    
No puede usar la función **Formato** en las siguientes áreas de las aplicaciones web de Access 2013: 
  
- Columnas calculadas en el nivel de tabla
    
- Macros de interfaz de usuario
    
- Expresiones de vistas (por ejemplo, en formularios)
    

