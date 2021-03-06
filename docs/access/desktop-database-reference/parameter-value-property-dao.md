---
title: Parameter.Value Property (DAO)
TOCTitle: Value Property
ms:assetid: 7058f3cd-9102-c711-bc83-b1565a8b001c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195733(v=office.15)
ms:contentKeyID: 48545556
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: bfba253424af0ceac3ca6bf5ce244beff472702c
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25486653"
---
# <a name="parametervalue-property-dao"></a>Parameter.Value Property (DAO)


**Se aplica a**: Access 2013 | Office 2013

Establece o devuelve el valor de un objeto. **Variant** de lectura y escritura.

## <a name="syntax"></a>Sintaxis

*expresión* . Valor

*expresión* Variable que representa un objeto **Parameter** .

## <a name="remarks"></a>Observaciones

La configuración o el valor devuelto es un tipo de datos Variant que da como resultado un valor apropiado para el tipo de datos, tal como especifica la propiedad **Type** de un objeto.

En general, la propiedad **Value** se usa para recuperar y modificar datos en objetos **Recordset**.

La propiedad **Value** es la propiedad predeterminada de los objetos **Field**, **Parameter** y **Property**. Por lo tanto, puede hacer que se establezca o devuelva el valor de uno de estos objetos haciendo referencia a ellos directamente en lugar de especificar la propiedad **Value**.

Si intenta que se establezca o devuelva la propiedad **Value** en un contexto no apropiado (por ejemplo, la propiedad **Value** de un objeto **Field** de la colección **Fields** de un objeto **TableDef**) se producirá un error capturable.


> [!NOTE]
> <P>Cuando se lean valores decimales de una base de datos de Microsoft SQL Server, se les dará formato con notación científica a través de un área de trabajo de Microsoft Access, pero aparecerán como valores decimales normales a través de un área de trabajo de ODBCDirect.</P>


