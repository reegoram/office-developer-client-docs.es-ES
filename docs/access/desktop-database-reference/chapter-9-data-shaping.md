---
title: 'Capítulo 9: Forma de datos'
TOCTitle: 'Chapter 9: Data Shaping'
ms:assetid: f66a319f-1b3d-c4a3-50b3-af1a47540832
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250253(v=office.15)
ms:contentKeyID: 48548739
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 8217be1004ea8304501e7d32908b8af269873b7a
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485851"
---
# <a name="chapter-9-data-shaping"></a>Capítulo 9: Forma de datos


**Se aplica a**: Access 2013 | Office 2013

La *Forma de datos* permite consultar un origen de datos y devolver un objeto [Recordset](recordset-object-ado.md) que representa una relación de objeto primario-objeto secundario entre dos o más entidades lógicas (una jerarquía). Un ejemplo clásico de una relación jerárquica es la de clientes y pedidos. Para cada cliente de una base de datos, puede haber cero o más pedidos. SQL permite recuperar los datos mediante la sintaxis de JOIN, pero esto puede resultar ser ineficaz y poco flexible porque los datos primarios redundantes se repiten en cada registro devuelto para una determinada relación de objeto primario-objeto secundario. La Forma de datos puede relacionar un solo registro primario del objeto **Recordset** primario con varios registros secundarios en el objeto **Recordset** secundario, evitando la redundancia de una sintaxis de JOIN. La mayoría de los usuarios opinan que este modelo de programación de ** Recordset** es más natural y más sencillo de usar que el modelo de JOIN de un solo objeto **Recordset**.

La sintaxis de la forma de datos también proporciona otras funciones. Los programadores pueden crear nuevos objetos **Recordset** sin origen de datos subyacente mediante la palabra clave NEW para describir los campos de los objetos **Recordset** primarios y secundarios. El nuevo objeto **Recordset** se puede rellenar con datos y almacenar de manera permanente. Los programadores también pueden realizar varios cálculos o agregaciones (por ejemplo, SUMA, MEDIA y MAX) en los campos secundarios. Además, la forma de datos puede crear un objeto **Recordset** primario a partir de un objeto **Recordset** secundario agrupando los registros en el objeto secundario y colocando una fila en el objeto primario por cada grupo en el objeto secundario.

Vea los temas siguientes para obtener más información sobre la forma de datos:

  - [Resumen de forma de datos](data-shaping-summary.md)

  - [Proveedores necesarios para la forma de datos](required-providers-for-data-shaping.md)

  - [Comandos Shape en general](shape-commands-in-general.md)

  - [Cláusula APPEND del comando Shape](shape-append-clause.md)

  - [Cláusula COMPUTE del comando Shape](shape-compute-clause.md)

  - [Crear conjuntos de registros jerárquicos](fabricating-hierarchical-recordsets.md)

  - [Obtener acceso a las filas de un objeto Recordset jerárquico](accessing-rows-in-a-hierarchical-recordset.md)

  - [Gramática formal del comando Shape](formal-shape-grammar.md)

  - [Funciones de Visual Basic para Aplicaciones](visual-basic-for-applications-functions.md)

