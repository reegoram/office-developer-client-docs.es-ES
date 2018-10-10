---
title: Field2.DefaultValue Property (DAO)
TOCTitle: DefaultValue Property
ms:assetid: 709c9580-520e-46ce-7d70-e409872184bb
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195744(v=office.15)
ms:contentKeyID: 48545563
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053121
f1_categories:
- Office.Version=v15
ms.openlocfilehash: cff7a319130786cfdab26546d49f83da5769c5f6
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485570"
---
# <a name="field2defaultvalue-property-dao"></a><span data-ttu-id="f1e71-102">Field2.DefaultValue Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="f1e71-102">Field2.DefaultValue Property (DAO)</span></span>


<span data-ttu-id="f1e71-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="f1e71-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="f1e71-p101">Establece o devuelve el valor predeterminado de un objeto **Field2**. Para un objeto **Field2** no anexado todavía a la colección **[Fields](fields-collection-dao.md)**, esta propiedad es de lectura y escritura (sólo para áreas de trabajo de Microsoft Access).</span><span class="sxs-lookup"><span data-stu-id="f1e71-p101">Sets or returns the default value of a **Field2** object. For a **Field2** object not yet appended to the **[Fields](fields-collection-dao.md)** collection, this property is read/write (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="f1e71-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f1e71-106">Syntax</span></span>

<span data-ttu-id="f1e71-107">*expresión* . DefaultValue</span><span class="sxs-lookup"><span data-stu-id="f1e71-107">*expression* .DefaultValue</span></span>

<span data-ttu-id="f1e71-108">*expresión* Variable que representa un objeto **Field2** .</span><span class="sxs-lookup"><span data-stu-id="f1e71-108">*expression* A variable that represents a **Field2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="f1e71-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f1e71-109">Remarks</span></span>

<span data-ttu-id="f1e71-p102">La configuración o el valor devuelto es un tipo de datos **String** que puede contener un máximo de 255 caracteres. Puede ser texto o una expresión. Si el valor de la propiedad es una expresión, no puede contener funciones definidas por el usuario, no puede agregar funciones SQL del motor de base de datos de Microsoft Access, ni tener referencias a consultas, formularios u otros objetos **Field2**.</span><span class="sxs-lookup"><span data-stu-id="f1e71-p102">The setting or return value is a **String** data type that can contain a maximum of 255 characters. It can be either text or an expression. If the property setting is an expression, it can't contain user-defined functions, Microsoft Access database engine SQL aggregate functions, or references to queries, forms, or other **Field2** objects.</span></span>


> [!NOTE]
> <P><span data-ttu-id="f1e71-p103">[!NOTA] También puede establecer la propiedad <STRONG>DefaultValue</STRONG> de un objeto <STRONG>Field2</STRONG> en un objeto <STRONG>TableDef</STRONG> para un valor especial denominado "GenUniqueID( )". Esto provoca que se asigne un número aleatorio a este campo siempre que se agregue o se cree un nuevo registro, de ese modo se asigna cada registro a un identificador único. La propiedad <STRONG>Type</STRONG> del campo debe ser <STRONG>Long</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f1e71-p103">You can also set the <STRONG>DefaultValue</STRONG> property of a <STRONG>Field2</STRONG> object on a <STRONG>TableDef</STRONG> object to a special value called "GenUniqueID( )". This causes a random number to be assigned to this field whenever a new record is added or created, thereby giving each record a unique identifier. The field's <STRONG>Type</STRONG> property must be <STRONG>Long</STRONG>.</span></span></P>



<span data-ttu-id="f1e71-116">La disponibilidad de la propiedad **DefaultValue** depende del objeto que contiene la colección **Fields**, como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="f1e71-116">The availability of the **DefaultValue** property depends on the object that contains the **Fields** collection, as shown in the following table.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f1e71-117">Si la colección Fields pertenece a</span><span class="sxs-lookup"><span data-stu-id="f1e71-117">If the Fields collection belongs to an</span></span></p></th>
<th><p><span data-ttu-id="f1e71-118">Entonces DefaultValue</span><span class="sxs-lookup"><span data-stu-id="f1e71-118">Then DefaultValue is</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f1e71-119">Objeto Index</span><span class="sxs-lookup"><span data-stu-id="f1e71-119">Index object</span></span></p></td>
<td><p><span data-ttu-id="f1e71-120">No está admitido</span><span class="sxs-lookup"><span data-stu-id="f1e71-120">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1e71-121">Objeto QueryDef</span><span class="sxs-lookup"><span data-stu-id="f1e71-121">QueryDef object</span></span></p></td>
<td><p><span data-ttu-id="f1e71-122">Sólo lectura</span><span class="sxs-lookup"><span data-stu-id="f1e71-122">Read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1e71-123">Objeto Recordset</span><span class="sxs-lookup"><span data-stu-id="f1e71-123">Recordset object</span></span></p></td>
<td><p><span data-ttu-id="f1e71-124">Sólo lectura</span><span class="sxs-lookup"><span data-stu-id="f1e71-124">Read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1e71-125">Objeto Relation</span><span class="sxs-lookup"><span data-stu-id="f1e71-125">Relation object</span></span></p></td>
<td><p><span data-ttu-id="f1e71-126">No está admitido</span><span class="sxs-lookup"><span data-stu-id="f1e71-126">Not supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1e71-127">Objeto TableDef</span><span class="sxs-lookup"><span data-stu-id="f1e71-127">TableDef object</span></span></p></td>
<td><p><span data-ttu-id="f1e71-128">Lectura y escritura</span><span class="sxs-lookup"><span data-stu-id="f1e71-128">Read/write</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f1e71-p104">Cuando se crea un nuevo registro, el valor de la propiedad **DefaultValue** se incluye automáticamente como el valor para el campo. Puede cambiar el valor del campo al establecer su propiedad en **Value**.</span><span class="sxs-lookup"><span data-stu-id="f1e71-p104">When a new record is created, the **DefaultValue** property setting is automatically entered as the value for the field. You can change the field value by setting its **Value** property.</span></span>

<span data-ttu-id="f1e71-131">La propiedad **DefaultValue** no se aplica a los campos **AutoNumber** y **Long Binary**.</span><span class="sxs-lookup"><span data-stu-id="f1e71-131">The **DefaultValue** property doesn't apply to **AutoNumber** and **Long Binary** fields.</span></span>

## <a name="example"></a><span data-ttu-id="f1e71-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f1e71-132">Example</span></span>

<span data-ttu-id="f1e71-p105">En este ejemplo se utiliza la propiedad **DefaultValue** para advertir al usuario de un valor normal del campo mientras se le piden datos de entrada. Además, se demuestra cómo los registros nuevos se rellenarán utilizando **DefaultValue** en ausencia de cualquier otra entrada. Se requiere la función DefaultPrompt para que pueda ejecutarse este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f1e71-p105">This example uses the **DefaultValue** property to alert the user of a field's normal value while prompting for input. In addition, it demonstrates how new records will be filled using **DefaultValue** in the absence of any other input. The DefaultPrompt function is required for this procedure to run.</span></span>

```vb
    Sub DefaultValueX() 
     
     Dim dbsNorthwind As Database 
     Dim tdfEmployees As TableDef 
     Dim strOldDefault As String 
     Dim rstEmployees As Recordset 
     Dim strMessage As String 
     Dim strCode As String 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set tdfEmployees = dbsNorthwind.TableDefs!Employees 
     
     ' Store original DefaultValue information and set the 
     ' property to a new value. 
     strOldDefault = _ 
     tdfEmployees.Fields!PostalCode.DefaultValue 
     tdfEmployees.Fields!PostalCode.DefaultValue = "98052" 
     
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees", _ 
     dbOpenDynaset) 
     
     With rstEmployees 
     ' Add a new record to the Recordset. 
     .AddNew 
     !FirstName = "Bruce" 
     !LastName = "Oberg" 
     
     ' Get user input. If user enters something, the field 
     ' will be filled with that data; otherwise, it will be 
     ' filled with the DefaultValue information. 
     strMessage = "Enter postal code for " & vbCr & _ 
     !FirstName & " " & !LastName & ":" 
     strCode = DefaultPrompt(strMessage, !PostalCode) 
     If strCode <> "" Then !PostalCode = strCode 
     .Update 
     
     ' Go to new record and print information. 
     .Bookmark = .LastModified 
     Debug.Print " FirstName = " & !FirstName 
     Debug.Print " LastName = " & !LastName 
     Debug.Print " PostalCode = " & !PostalCode 
     
     ' Delete new record because this is a demonstration. 
     .Delete 
     .Close 
     End With 
     
     ' Restore original DefaultValue property because this is a 
     ' demonstration. 
     tdfEmployees.Fields!PostalCode.DefaultValue = _ 
     strOldDefault 
     
     dbsNorthwind.Close 
     
    End Sub 
     
    Function DefaultPrompt(strPrompt As String, _ 
     fldTemp As Field2) As String 
     
     Dim strFullPrompt As String 
     
     ' Ask user for new DefaultValue setting for the specified 
     ' Field object. 
     strFullPrompt = strPrompt & vbCr & _ 
     "[Default = " & fldTemp.DefaultValue & _ 
     ", Cancel - use default]" 
     DefaultPrompt = InputBox(strFullPrompt) 
     
    End Function
```