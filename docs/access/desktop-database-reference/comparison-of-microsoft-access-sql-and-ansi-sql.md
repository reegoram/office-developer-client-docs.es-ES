---
title: Comparación de Microsoft Access SQL y ANSI SQL
TOCTitle: Comparison of Microsoft Access SQL and ANSI SQL
ms:assetid: 0686f98f-10fe-0e02-e9d1-84ff3e755b57
ms:mtpsurl: https://msdn.microsoft.com/library/Ff844937(v=office.15)
ms:contentKeyID: 48543052
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: cd28cebe731ee3c922adec0bc3357e998dc1959b
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25484764"
---
# <a name="comparison-of-microsoft-access-sql-and-ansi-sql"></a>Comparación de Microsoft Access SQL y ANSI SQL


**Se aplica a**: Access 2013 | Office 2013

En términos generales, SQL en el motor de base de datos de Microsoft Access es compatible con ANSI-89 nivel 1. Sin embargo, determinadas características de ANSI SQL no se implementan en Microsoft® Access SQL. Por su parte, Microsoft Access SQL incluye palabras reservadas y características no admitidas en ANSI SQL.

## <a name="major-differences"></a>Diferencias principales

  - Microsoft Access SQL y ANSI SQL tienen palabras reservadas y tipos de datos diferentes. Para obtener más información, vea [Palabras reservadas SQL del motor de base de datos de Microsoft Access](sql-reserved-words.md) y [Tipos de datos equivalentes de ANSI SQL](equivalent-ansi-sql-data-types.md). Si se usa el proveedor OLE DB del motor de base de datos de Microsoft Access, hay palabras reservadas adicionales.

  - **[Between…And](https://msdn.microsoft.com/library/ff192436\(v=office.15\))**
    
    *expr1* \[No\] **entre** *valor1* **y** *valor2*
    
    En Microsoft Access SQL, *valor1* puede ser mayor que *valor2*; en ANSI SQL, *valor1* debe ser igual o menor que *valor2.*

  - Microsoft Access SQL admite los caracteres comodín de ANSI SQL y los [caracteres comodín](using-wildcard-characters-in-string-comparisons.md) que son específicos del motor de base de datos de Microsoft Access para su uso con el operador **[Like](https://msdn.microsoft.com/library/ff195752\(v=office.15\))**. El uso de los caracteres comodín de ANSI y el motor de base de datos de Microsoft Access es mutuamente excluyente. Debe usar uno de los dos conjuntos y no se pueden mezclar. Los caracteres comodín de ANSI SQL sólo están disponibles cuando se usa el motor de base de datos de Microsoft Access y el proveedor OLE DB del motor de base de datos de Microsoft Access. Si intenta usar los caracteres comodín de ANSI SQL con Microsoft Access o DAO, se interpretarán como caracteres literales. Y también sucede lo contrario cuando se utiliza el proveedor OLE DB del motor de base de datos de Microsoft Access.
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Carácter correspondiente</p></th>
    <th><p>Microsoft Access SQL</p></th>
    <th><p>ANSI SQL</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Cualquier carácter</p></td>
    <td><p>?</p></td>
    <td><p>_ (subrayado)</p></td>
    </tr>
    <tr class="even">
    <td><p>Cero o más caracteres</p></td>
    <td><p>*</p></td>
    <td><p>%</p></td>
    </tr>
    </tbody>
    </table>


  - En general, Microsoft Access SQL es menos restrictivo. Por ejemplo, permite agrupar y ordenar por expresiones.

  - Microsoft Access SQL admite expresiones más eficaces.

## <a name="enhanced-features-of-microsoft-access-sql"></a>Características mejoradas de Microsoft Access SQL

Microsoft Access SQL ofrece las siguientes características mejoradas:

  - Instrucción [TRANSFORM](transform-statement-microsoft-access-sql.md), que proporciona compatibilidad con las consultas de tabla de referencias cruzadas.

  - [Funciones de agregado](sql-aggregate-functions-sql.md) adicionales, como **StDev** y **VarP**.

  - Declaración [PARAMETERS](parameters-declaration-microsoft-access-sql.md) para definir consultas de parámetros.

## <a name="ansi-sql-features-not-supported-in-microsoft-access-sql"></a>Características de ANSI SQL no admitidas en Microsoft Access SQL

Microsoft Access SQL no admite las siguientes características de ANSI SQL:

  - Referencias de la función de agregado DISTINCT. Por ejemplo, Microsoft Access SQL no permite SUM(DISTINCT *nombreDeColumna*).

  - La cláusula límite *nn* ROWS utilizada para limitar el número de filas devueltas por una consulta. Sólo se puede usar la [cláusula WHERE](https://msdn.microsoft.com/library/ff195245\(v=office.15\)) para limitar el ámbito de una consulta.

