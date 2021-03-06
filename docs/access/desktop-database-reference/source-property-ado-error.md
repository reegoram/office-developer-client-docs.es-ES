---
title: Source (propiedad, Error ADO)
TOCTitle: Source Property (ADO Error)
ms:assetid: ffc6c77f-1494-d63a-d832-416faa4c6f07
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250316(v=office.15)
ms:contentKeyID: 48548969
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: adeadcf4c467aabad7b486bd43c12e26d67ce302
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2018
ms.locfileid: "25603871"
---
# <a name="source-property-ado-error"></a>Source (propiedad, Error ADO)


**Se aplica a**: Access 2013 | Office 2013

Indica el nombre del objeto o de la aplicación que ha generado un error originariamente.

<<<<<<< HEAD
## <a name="return-value"></a>Valor devuelto
=======
## <a name="return-value"></a>Valor devuelto
>>>>>>> master

Devuelve un valor de tipo **String** que indica el nombre de un objeto o una aplicación.

## <a name="remarks"></a>Comentarios

Use la propiedad **Source** en un objeto [Error](error-object-ado.md) para determinar el nombre del objeto o la aplicación que generó originalmente un error. Esto podría ser el nombre de clase del objeto o el identificador de programación. Para los errores de ADO, el valor de la propiedad será **ADODB. *** ObjectName*, donde *ObjectName* es el nombre del objeto que ha desencadenado el error. En ADOX y ADO MD, el valor será **ADOX. *** ObjectName* y **ADOMD. *** ObjectName,* respectivamente.

Basándose en la documentación del error de las propiedades **Source**, [Number](number-property-ado.md) y [Description](description-property-ado.md) de los objetos **Error**, es posible escribir código que controle el error de forma adecuada.

La propiedad **Source** es de sólo lectura para objetos **Error**.

