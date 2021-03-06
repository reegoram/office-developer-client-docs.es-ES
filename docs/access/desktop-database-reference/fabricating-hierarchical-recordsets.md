---
title: Crear conjuntos de registros jerárquicos
TOCTitle: Fabricating Hierarchical Recordsets
ms:assetid: 0a6e41ba-015e-c07e-8876-1e744256b876
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248836(v=office.15)
ms:contentKeyID: 48543153
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 81302ba1c18645a51913cb92179f4b61f3c32ce4
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485879"
---
# <a name="fabricating-hierarchical-recordsets"></a>Crear conjuntos de registros jerárquicos


**Se aplica a**: Access 2013 | Office 2013

En el ejemplo siguiente se muestra cómo crear un objeto Recordset jerárquico sin origen de datos subyacente mediante la gramática de forma de datos para definir las columnas de los objetos **Recordset** primarios y secundarios.

Para crear un objeto **Recordset** jerárquico, debe especificar el Servicio de forma de datos de Microsoft para OLE DB (MSDataShape) y puede especificar el valor NONE para el proveedor de datos en el parámetro de la cadena de conexión del método [Open](connection-object-ado.md) del objeto [Connection](open-method-ado-connection.md). Para obtener más información, vea [Proveedores necesarios para la forma de datos](required-providers-for-data-shaping.md).

```vb
    Dim cn As New ADODB.Connection
    Dim rsCustomers As New ADODB.Recordset
    
    cn.Open "Provider=MSDataShape;Data Provider=NONE;"
     
    strShape = _
    "SHAPE APPEND NEW adInteger AS CustID," & _
                " NEW adChar(25) AS FirstName," & _
                " NEW adChar(25) AS LastName," & _
                " NEW adChar(12) AS SSN," & _
                " NEW adChar(50) AS Address," & _
             " ((SHAPE APPEND NEW adChar(80) AS VIN_NO," & _
                            " NEW adInteger AS CustID," & _
                            " NEW adChar(20) AS BodyColor, " & _
                         " ((SHAPE APPEND NEW adChar(80) AS VIN_NO," & _
                                        " NEW adChar(20) AS Make, " & _
                                        " NEW adChar(20) AS Model," & _
                                        " NEW adChar(4) AS Year) " & _
                            " AS VINS RELATE VIN_NO TO VIN_NO))" & _
                " AS Vehicles RELATE CustID TO CustID) "
     
    rsCustomers.Open strShape, cn, adOpenStatic, adLockOptimistic, -1
```

Una vez creado el **objeto Recordset** , puede ser rellena, manipular o almacenar en un archivo.

