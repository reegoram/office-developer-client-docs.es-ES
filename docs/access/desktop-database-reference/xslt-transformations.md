---
title: Transformaciones XSLT
TOCTitle: XSLT Transformations
ms:assetid: 6a19310d-027f-e8d6-9859-0b545ae7e2f1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249418(v=office.15)
ms:contentKeyID: 48545425
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 733dd62122ee99d4e243c2af724f709a15333d51
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485341"
---
# <a name="xslt-transformations"></a>Transformaciones XSLT


**Se aplica a**: Access 2013 | Office 2013

## <a name="xslt-transformations"></a>Transformaciones XSLT

XSLT se puede aplicar al XML generado para transformarlo en otro formato. Entender el formato XML en ADO ayuda a crear plantillas XSLT que pueden transformarlo en más intuitivo.

Por ejemplo, se sabe que cada fila del objeto **Recordset** se guarda como el elemento z:row dentro del elemento rs:data. De igual forma, cada campo del objeto **Recordset** se guarda como par atributo-valor para este elemento.

El siguiente script XSLT se puede aplicar al XML mostrado en la sección anterior para transformarlo en una tabla HTML que se mostrará en el explorador:

```xml 
 
<?xml version="1.0" encoding="ISO-8859-1"?> 
<html xmlns:xsl="https://www.w3.org/TR/WD-xsl"> 
<body STYLE="font-family:Arial, helvetica, sans-serif; font-size:12pt; background-color:white"> 
<table border="1" style="table-layout:fixed" width="600"> 
  <col width="200"></col> 
  <tr bgcolor="teal"> 
    <th><font color="white">CustomerId</font></th> 
    <th><font color="white">CompanyName</font></th> 
    <th><font color="white">ContactName</font></th> 
  </tr> 
<xsl:for-each select="xml/rs:data/z:row"> 
  <tr bgcolor="navy"> 
    <td><font color="white"><xsl:value-of select="@CustomerID"/></font></td> 
    <td><font color="white"><xsl:value-of select="@CompanyName"/></font></td> 
    <td><font color="white"><xsl:value-of select="@ContactName"/></font></td>  
  </tr> 
</xsl:for-each> 
</table> 

</body> 
</html> 
```

El XSLT convierte la secuencia XML generada por el método **Save** de ADO en una tabla HTML que muestra cada campo del objeto **Recordset** junto con un encabezado de tabla. Los encabezados de tabla y las filas utilizan colores y fuentes diferentes.

