---
title: Recordset2.MoveNext Method (DAO)
TOCTitle: MoveNext Method
ms:assetid: 0eeb917e-f76a-03ec-9e1e-aa8d501db031
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845265(v=office.15)
ms:contentKeyID: 48543254
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: fd6eddf9f9b41223603887bb038bf2c9bd227031
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485419"
---
# <a name="recordset2movenext-method-dao"></a>Recordset2.MoveNext Method (DAO)


**Se aplica a**: Access 2013 | Office 2013

Se desplaza al siguiente registro de un objeto **Recordset** especificado y convierte ese registro en el registro activo.

## <a name="syntax"></a>Sintaxis

*expresión* . MoveNext

*expresión* Variable que representa un objeto **Recordset2** .

## <a name="remarks"></a>Observaciones

Utilice los métodos **Move** para desplazarse de un registro a otro sin aplicar una condición.

Si edita el registro activo, asegúrese de que utiliza el método **Update** para guardar los cambios antes de moverse a otro registro. Si se desplaza a otro registro sin ejecutar una actualización, los cambios se pierden sin advertencia.

Cuando abre un objeto **Recordset**, el primer registro es el activo y la propiedad **BOF** es **False**. Si **Recordset** no contiene registros, la propiedad **BOF** es **True** y no hay ningún registro activo.

Si utiliza **MoveNext** cuando el último registro está activo, la propiedad **EOF** es **True** y no hay registro activo. Si utiliza **MoveNext** de nuevo, se produce un error y **EOF** sigue siendo **True**.

Si el objeto recordset hace referencia a un **objeto Recordset** de tipo tabla (sólo áreas de trabajo de Microsoft Access), el desplazamiento sigue el índice actual. Puede definir el índice actual mediante la propiedad **Index**. Si no define el índice actual, el orden de los registros devueltos queda sin definir.

No puede usar los métodos **MoveFirst**, **MoveLast**ni **MovePrevious** en un objeto **Recordset** de tipo forward – only.

Para mover hacia delante o hacia atrás la posición del registro actual en un objeto **Recordset** un número determinado de registros, use el método **Move**.

