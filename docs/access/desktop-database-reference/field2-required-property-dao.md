---
title: Field2.Required Property (DAO)
TOCTitle: Required Property
ms:assetid: 7d14dfd7-a50d-6044-469e-1511c74c148d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196390(v=office.15)
ms:contentKeyID: 48545848
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 048c4dc46f03af213dee090b839dfcc67d4f48ac
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485899"
---
# <a name="field2required-property-dao"></a>Field2.Required Property (DAO)


**Se aplica a**: Access 2013 | Office 2013


Establece o devuelve un valor que indica si un objeto **Field2** requiere un valor no Null.

## <a name="syntax"></a>Sintaxis

*expresión* . Obligatorio

*expresión* Variable que representa un objeto **Field2** .

## <a name="remarks"></a>Observaciones

Para un **Field2** que no está todavía anexado a la colección **Fields**, esta propiedad es de lectura y escritura.

La disponibilidad de la propiedad **Required** depende del objeto que contiene la colección **[Fields](fields-collection-dao.md)**, como se muestra en la siguiente tabla.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Si la colección Fields pertenece a un</p></th>
<th><p>Entonces Required</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>							Objeto <strong>Index</strong></p></td>
<td><p>No admitido</p></td>
</tr>
<tr class="even">
<td><p>							Objeto <strong>QueryDef</strong></p></td>
<td><p>Solo lectura</p></td>
</tr>
<tr class="odd">
<td><p>							Objeto <strong>Recordset</strong></p></td>
<td><p>Solo lectura</p></td>
</tr>
<tr class="even">
<td><p>							Objeto <strong>Relation</strong></p></td>
<td><p>No admitido</p></td>
</tr>
<tr class="odd">
<td><p>							Objeto <strong>TableDef</strong></p></td>
<td><p>Es de lectura y escritura.</p></td>
</tr>
</tbody>
</table>


Puede utilizar la propiedad **Required** junto con la propiedad **AllowZeroLength**, **ValidateOnSet** o **ValidationRule** para determinar la validez del valor de la propiedad **Value** para ese objeto **Field2**. Si la propiedad **Required** está establecida como **False**, el campo puede contener valores **null**, así como valores que cumplan las condiciones especificadas por los valores de las propiedades **AllowZeroLength** y **ValidationRule**.


> [!NOTE]
> <P>[!NOTA] Cuando pueda establecer esta propiedad tanto para un objeto <STRONG>Index</STRONG> como para un objeto <STRONG>Field2</STRONG>, establézcala para el objeto <STRONG>Field2</STRONG>. La validez del valor de la propiedad para un objeto <STRONG>Field2</STRONG> se comprueba antes que para un objeto <STRONG>Index</STRONG>.</P>



## <a name="example"></a>Ejemplo

En este ejemplo se utiliza la propiedad **Required** que informa sobre qué campo de tres tablas distintas debe contener los datos necesarios para agregar un nuevo registro. El procedimiento RequiredOutput es necesario para ejecutar este ejemplo.

```vb 
Sub RequiredX() 
 
 Dim dbsNorthwind As Database 
 Dim tdfloop As TableDef 
 
 Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
 
 With dbsNorthwind 
 ' Show which fields are required in the Fields 
 ' collections of three different TableDef objects. 
 RequiredOutput .TableDefs("Categories") 
 RequiredOutput .TableDefs("Customers") 
 RequiredOutput .TableDefs("Employees") 
 .Close 
 End With 
 
End Sub 
 
Sub RequiredOutput(tdfTemp As TableDef) 
 
 Dim fldLoop As Field2 
 
 ' Enumerate Fields collection of the specified TableDef 
 ' and show the Required property. 
 Debug.Print "Fields in " & tdfTemp.Name & ":" 
 For Each fldLoop In tdfTemp.Fields 
 Debug.Print , fldLoop.Name & ", Required = " & _ 
 fldLoop.Required 
 Next fldLoop 
 
End Sub 
 
```

