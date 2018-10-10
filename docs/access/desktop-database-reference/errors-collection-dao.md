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
# <a name="errors-collection-dao"></a><span data-ttu-id="3fc46-102">Errors Collection (DAO)</span><span class="sxs-lookup"><span data-stu-id="3fc46-102">Errors Collection (DAO)</span></span>


<span data-ttu-id="3fc46-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="3fc46-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="3fc46-104">Una colección **Errors** contiene todos los objetos **Error** almacenados, cada uno de los cuales pertenece a una única operación en la que intervienen objetos DAO.</span><span class="sxs-lookup"><span data-stu-id="3fc46-104">An **Errors** collection contains all stored **Error** objects, each of which pertains to a single operation involving DAO.</span></span>

## <a name="remarks"></a><span data-ttu-id="3fc46-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3fc46-105">Remarks</span></span>

<span data-ttu-id="3fc46-p101">Toda operación en la que intervengan objetos DAO puede generar uno o varios errores. Cuando se produce alguno de estos errores, uno o varios objetos **Error** se colocan en la colección **Errors** del objeto **DBEngine**. Cuando otra operación DAO genera un error, la colección **Errors** se borra y el nuevo conjunto de objetos **Error** se coloca en la colección **Errors**. El objeto con el número mayor en la colección \*\*Errors \*\*(DBEngine.Errors.Count - 1) se corresponde con el error generado por el objeto **Err** de Microsoft Visual Basic para Aplicaciones (VBA).</span><span class="sxs-lookup"><span data-stu-id="3fc46-p101">Any operation involving DAO objects can generate one or more errors. As each error occurs, one or more **Error** objects are placed in the **Errors** collection of the **DBEngine** object. When another DAO operation generates an error, the **Errors** collection is cleared, and the new set of **Error** objects is placed in the **Errors** collection. The highest-numbered object in the **Errors** collection (DBEngine.Errors.Count - 1) corresponds to the error reported by the Microsoft Visual Basic for Applications (VBA) **Err** object.</span></span>

<span data-ttu-id="3fc46-110">Las operaciones DAO que no generan un error no afectan a la colección **Errors**.</span><span class="sxs-lookup"><span data-stu-id="3fc46-110">DAO operations that don't generate an error have no effect on the **Errors** collection.</span></span>

<span data-ttu-id="3fc46-111">Los elementos de la colección **Errors** no se anexan como suele ocurrir con otras colecciones, por lo que la colección **Errors** no admite los métodos **Append** y **Delete**.</span><span class="sxs-lookup"><span data-stu-id="3fc46-111">Elements of the **Errors** collection aren't appended as they typically are with other collections, so the **Errors** collection doesn't support the **Append** and **Delete** methods.</span></span>

<span data-ttu-id="3fc46-p102">El conjunto de objetos **Error** de la colección **Errors** describe un solo error. El primer objeto **Error** es el error de nivel inferior, el segundo es el error del nivel superior, y así sucesivamente. Por ejemplo, si se produce un error de ODBC al intentar abrir un objeto **[Recordset](recordset-object-dao.md)**, el primer objeto de error contiene el error de ODBC del nivel inferior, y los errores siguientes contienen los errores de ODBC devueltos por los distintos niveles de ODBC. En este caso, el administrador del controlador ODBC, y probablemente el propio controlador, devuelven objetos **Error** distintos. El último objeto **Error** contiene el error de DAO que indica que no se puede abrir el objeto.</span><span class="sxs-lookup"><span data-stu-id="3fc46-p102">The set of **Error** objects in the **Errors** collection describes one error. The first **Error** object is the lowest level error, the second the next higher level, and so forth. For example, if an ODBC error occurs while trying to open a **[Recordset](recordset-object-dao.md)** object, the first error object contains the lowest level ODBC error; subsequent errors contain the ODBC errors returned by the various layers of ODBC. In this case, the ODBC driver manager, and possibly the driver itself, return separate **Error** objects. The last **Error** object contains the DAO error indicating that the object couldn't be opened.</span></span>

<span data-ttu-id="3fc46-117">La enumeración de los errores específicos en la colección **Errors** permite que las rutinas de tratamiento de errores determinen con mayor precisión la causa y el origen de un error y realicen los pasos necesarios para solucionarlo.</span><span class="sxs-lookup"><span data-stu-id="3fc46-117">Enumerating the specific errors in the **Errors** collection enables your error-handling routines to more precisely determine the cause and origin of an error, and take appropriate steps to recover.</span></span>


> [!NOTE]
> <P><span data-ttu-id="3fc46-p103">[!NOTA] Si utiliza la palabra clave <STRONG>New</STRONG> para crear un objeto que causa un error antes o mientras se coloca en la colección <STRONG>Errors</STRONG>, la colección no contiene información de error del objeto, porque el nuevo objeto no está asociado al objeto <STRONG>DBEngine</STRONG>. Sin embargo, la información sobre el error está disponible en el objeto <STRONG>Err</STRONG> de VBA.</span><span class="sxs-lookup"><span data-stu-id="3fc46-p103">If you use the <STRONG>New</STRONG> keyword to create an object that causes an error either before or while being placed into the <STRONG>Errors</STRONG> collection, the collection doesn't contain error information about that object, because the new object is not associated with the <STRONG>DBEngine</STRONG> object. However, the error information is available in the VBA <STRONG>Err</STRONG> object.</span></span></P>



## <a name="example"></a><span data-ttu-id="3fc46-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3fc46-120">Example</span></span>

<span data-ttu-id="3fc46-121">En este ejemplo se fuerza un error, se captura y se muestran las propiedades **Description**, **Number**, **Source**, **HelpContext** y **HelpFile** del objeto **Error** resultante.</span><span class="sxs-lookup"><span data-stu-id="3fc46-121">This example forces an error, traps it, and displays the **Description**, **Number**, **Source**, **HelpContext**, and **HelpFile** properties of the resulting **Error** object.</span></span>

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
