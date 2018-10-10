---
title: Field.ValidateOnSet Property (DAO)
TOCTitle: ValidateOnSet Property
ms:assetid: 00245a8a-a78f-b0a8-3eb3-11dd27873984
ms:mtpsurl: https://msdn.microsoft.com/library/Ff844720(v=office.15)
ms:contentKeyID: 48542898
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052929
f1_categories:
- Office.Version=v15
ms.openlocfilehash: e4b1297fe7c41efd49a457f3382f72c480f85363
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485587"
---
# <a name="fieldvalidateonset-property-dao"></a><span data-ttu-id="4a82f-102">Field.ValidateOnSet Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="4a82f-102">Field.ValidateOnSet Property (DAO)</span></span>


<span data-ttu-id="4a82f-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="4a82f-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="4a82f-104">Establece o devuelve un valor que especifica si el valor de un objeto **[Field](field-object-dao.md)** se valida o no inmediatamente cuando se establece la propiedad **[Value](field-value-property-dao.md)** del objeto (únicamente áreas de trabajo de Microsoft Access).</span><span class="sxs-lookup"><span data-stu-id="4a82f-104">Sets or returns a value that specifies whether or not the value of a **[Field](field-object-dao.md)** object is immediately validated when the object's **[Value](field-value-property-dao.md)** property is set (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="4a82f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4a82f-105">Syntax</span></span>

<span data-ttu-id="4a82f-106">*expresión* . ValidateOnSet</span><span class="sxs-lookup"><span data-stu-id="4a82f-106">*expression* .ValidateOnSet</span></span>

<span data-ttu-id="4a82f-107">*expresión* Variable que representa un objeto **Field** .</span><span class="sxs-lookup"><span data-stu-id="4a82f-107">*expression* A variable that represents a **Field** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="4a82f-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4a82f-108">Remarks</span></span>

<span data-ttu-id="4a82f-109">Solo los objetos **Field** de objetos **[Recordset](recordset-object-dao.md)** admiten la propiedad **ValidateOnSet** como propiedad de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="4a82f-109">Only **Field** objects in **[Recordset](recordset-object-dao.md)** objects support the **ValidateOnSet** property as read/write.</span></span>

<span data-ttu-id="4a82f-p101">El establecimiento de la propiedad **ValidateOnSet** en **True** puede ser útil en situaciones en que un usuario especifica registros que incluyen datos sustanciales de tipo Memo. Esperar a que se produzca la llamada a **[Update](recordset-update-method-dao.md)** para validar los datos puede hacer que se utilice un tiempo innecesario en la escritura de datos extensos de tipo Memo en la base de datos si, en cualquier caso, los datos no eran válidos a causa de la interrupción de una regla de validación en otro campo.</span><span class="sxs-lookup"><span data-stu-id="4a82f-p101">Setting the **ValidateOnSet** property to **True** can be useful in a situation when a user is entering records that include substantial Memo data. Waiting until the **[Update](recordset-update-method-dao.md)** call to validate the data can result in unnecessary time spent writing the lengthy Memo data to the database if it turns out that the data was invalid anyway because a validation rule was broken in another field.</span></span>

## <a name="example"></a><span data-ttu-id="4a82f-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4a82f-112">Example</span></span>

<span data-ttu-id="4a82f-p102">En este ejemplo se usa la propiedad **ValidateOnSet** para mostrar cómo se pueden interceptar errores durante la entrada de datos. Para que este procedimiento se ejecute se necesita la función ValidateData.</span><span class="sxs-lookup"><span data-stu-id="4a82f-p102">This example uses the **ValidateOnSet** property to demonstrate how one might trap for errors during data entry. The ValidateData function is required for this procedure to run.</span></span>

```vb
    Sub ValidateOnSetX() 
     
     Dim dbsNorthwind As Database 
     Dim fldDays As Field 
     Dim rstEmployees As Recordset 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
     ' Create and append a new Field object to the Fields 
     ' collection of the Employees table. 
     Set fldDays = _ 
     dbsNorthwind.TableDefs!Employees.CreateField( _ 
     "DaysOfVacation", dbInteger, 2) 
     fldDays.ValidationRule = "BETWEEN 1 AND 20" 
     fldDays.ValidationText = _ 
     "Number must be between 1 and 20!" 
     dbsNorthwind.TableDefs!Employees.Fields.Append fldDays 
     
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees") 
     
     With rstEmployees 
     
     Do While True 
     ' Add new record. 
     .AddNew 
     
     ' Get user input for three fields. Verify that the 
     ' data do not violate the validation rules for any 
     ' of the fields. 
     If ValidateData(!FirstName, _ 
     "Enter first name.") = False Then Exit Do 
     If ValidateData(!LastName, _ 
     "Enter last name.") = False Then Exit Do 
     If ValidateData(!DaysOfVacation, _ 
     "Enter days of vacation.") = False Then Exit Do 
     
     .Update 
     .Bookmark = .LastModified 
     Debug.Print !FirstName & " " & !LastName & _ 
     " - " & "DaysOfVacation = " & !DaysOfVacation 
     
     ' Delete new record because this is a demonstration. 
     .Delete 
     Exit Do 
     Loop 
     
     ' Cancel AddNew method if any of the validation rules 
     ' were broken. 
     If .EditMode <> dbEditNone Then .CancelUpdate 
     .Close 
     End With 
     
     ' Delete new field because this is a demonstration. 
     dbsNorthwind.TableDefs!Employees.Fields.Delete _ 
     fldDays.Name 
     dbsNorthwind.Close 
     
    End Sub 
     
    Function ValidateData(fldTemp As Field, _ 
     strMessage As String) As Boolean 
     
     Dim strInput As String 
     Dim errLoop As Error 
     
     ValidateData = True 
     ' ValidateOnSet is only read/write for Field objects in 
     ' Recordset objects. 
     fldTemp.ValidateOnSet = True 
     
     Do While True 
     strInput = InputBox(strMessage) 
     If strInput = "" Then Exit Do 
     ' Trap for errors when setting the Field value. 
     On Error GoTo Err_Data 
     If fldTemp.Type = dbInteger Then 
     fldTemp = Val(strInput) 
     Else 
     fldTemp = strInput 
     End If 
     On Error GoTo 0 
     If Not IsNull(fldTemp) Then Exit Do 
     Loop 
     
     If strInput = "" Then ValidateData = False 
     
     Exit Function 
     
    Err_Data: 
     
     If DBEngine.Errors.Count > 0 Then 
     ' Enumerate the Errors collection. The description 
     ' property of the last Error object will be set to 
     ' the ValidationText property of the relevant 
     ' field. 
     For Each errLoop In DBEngine.Errors 
     MsgBox "Error number: " & errLoop.Number & _ 
     vbCr & errLoop.Description 
     Next errLoop 
     End If 
     
     Resume Next 
     
    End Function
```