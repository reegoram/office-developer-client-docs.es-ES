---
title: Errors Collection (DAO)
TOCTitle: Errors Collection
ms:assetid: d42007b5-6410-14e9-baf9-9306fdef38f9
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834805(v=office.15)
ms:contentKeyID: 48547929
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7f118bab1a73d29858776e33149c54aab39ef5cc
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25483672"
---
# <a name="errors-collection-dao"></a>Errors Collection (DAO)


**Se aplica a**: Access 2013 | Office 2013

Una colección **Errors** contiene todos los objetos **Error** almacenados, cada uno de los cuales pertenece a una única operación en la que intervienen objetos DAO.

## <a name="remarks"></a>Observaciones

Toda operación en la que intervengan objetos DAO puede generar uno o varios errores. Cuando se produce alguno de estos errores, uno o varios objetos **Error** se colocan en la colección **Errors** del objeto **DBEngine**. Cuando otra operación DAO genera un error, la colección **Errors** se borra y el nuevo conjunto de objetos **Error** se coloca en la colección **Errors**. El objeto con el número mayor en la colección **Errors **(DBEngine.Errors.Count - 1) se corresponde con el error generado por el objeto **Err** de Microsoft Visual Basic para Aplicaciones (VBA).

Las operaciones DAO que no generan un error no afectan a la colección **Errors**.

Los elementos de la colección **Errors** no se anexan como suele ocurrir con otras colecciones, por lo que la colección **Errors** no admite los métodos **Append** y **Delete**.

El conjunto de objetos **Error** de la colección **Errors** describe un solo error. El primer objeto **Error** es el error de nivel inferior, el segundo es el error del nivel superior, y así sucesivamente. Por ejemplo, si se produce un error de ODBC al intentar abrir un objeto **[Recordset](recordset-object-dao.md)**, el primer objeto de error contiene el error de ODBC del nivel inferior, y los errores siguientes contienen los errores de ODBC devueltos por los distintos niveles de ODBC. En este caso, el administrador del controlador ODBC, y probablemente el propio controlador, devuelven objetos **Error** distintos. El último objeto **Error** contiene el error de DAO que indica que no se puede abrir el objeto.

La enumeración de los errores específicos en la colección **Errors** permite que las rutinas de tratamiento de errores determinen con mayor precisión la causa y el origen de un error y realicen los pasos necesarios para solucionarlo.


> [!NOTE]
> <P>[!NOTA] Si utiliza la palabra clave <STRONG>New</STRONG> para crear un objeto que causa un error antes o mientras se coloca en la colección <STRONG>Errors</STRONG>, la colección no contiene información de error del objeto, porque el nuevo objeto no está asociado al objeto <STRONG>DBEngine</STRONG>. Sin embargo, la información sobre el error está disponible en el objeto <STRONG>Err</STRONG> de VBA.</P>



## <a name="example"></a>Ejemplo

En este ejemplo se fuerza un error, se captura y se muestran las propiedades **Description**, **Number**, **Source**, **HelpContext** y **HelpFile** del objeto **Error** resultante.

```vb 
Sub DescriptionX() 
 
 Dim dbsTest As Database 
 
 On Error GoTo ErrorHandler 
 
 ' Intentionally trigger an error. 
 Set dbsTest = OpenDatabase("NoDatabase") 
 
 Exit Sub 
 
ErrorHandler: 
 Dim strError As String 
 Dim errLoop As Error 
 
 ' Enumerate Errors collection and display properties of 
 ' each Error object. 
 For Each errLoop In Errors 
 With errLoop 
 strError = _ 
 "Error #" & .Number & vbCr 
 strError = strError & _ 
 " " & .Description & vbCr 
 strError = strError & _ 
 " (Source: " & .Source & ")" & vbCr 
 strError = strError & _ 
 "Press F1 to see topic " & .HelpContext & vbCr 
 strError = strError & _ 
 " in the file " & .HelpFile & "." 
 End With 
 MsgBox strError 
 Next 
 
 Resume Next 
 
End Sub 
 
```

