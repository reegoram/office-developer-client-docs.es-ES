---
title: Recordset2.Sort Property (DAO)
TOCTitle: Sort Property
ms:assetid: 523a8c29-46e2-564f-205d-03c214f277fe
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193917(v=office.15)
ms:contentKeyID: 48544842
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 0c7674f7513e75d0b03533dc165b49ac78d0461d
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25484564"
---
# <a name="recordset2sort-property-dao"></a><span data-ttu-id="5369c-102">Recordset2.Sort Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="5369c-102">Recordset2.Sort Property (DAO)</span></span>


<span data-ttu-id="5369c-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="5369c-103">**Applies to**: Access 2013 | Office 2013</span></span> 

<span data-ttu-id="5369c-104">Establece o devuelve el criterio de ordenación para los registros de un objeto **[Recordset](recordset-object-dao.md)** (solo en áreas de trabajo de Microsoft Access).</span><span class="sxs-lookup"><span data-stu-id="5369c-104">Sets or returns the sort order for records in a **[Recordset](recordset-object-dao.md)** object (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="5369c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5369c-105">Syntax</span></span>

<span data-ttu-id="5369c-106">*expresión* . Ordenar</span><span class="sxs-lookup"><span data-stu-id="5369c-106">*expression* .Sort</span></span>

<span data-ttu-id="5369c-107">*expresión* Variable que representa un objeto **Recordset2** .</span><span class="sxs-lookup"><span data-stu-id="5369c-107">*expression* A variable that represents a **Recordset2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="5369c-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5369c-108">Remarks</span></span>

<span data-ttu-id="5369c-109">Puede usar la propiedad **Sort** con objetos **Recordset** de tipo dynaset y snapshot.</span><span class="sxs-lookup"><span data-stu-id="5369c-109">You can use the **Sort** property with dynaset– and snapshot–type **Recordset** objects.</span></span>

<span data-ttu-id="5369c-p101">Si establece esta propiedad para un objeto, la ordenación se realiza cuando se crea un objeto posterior **Recordset** desde ese objeto. El valor de la propiedad **Sort** anula cualquier criterio de ordenación especificado para un objeto **[QueryDef](querydef-object-dao.md)**.</span><span class="sxs-lookup"><span data-stu-id="5369c-p101">When you set this property for an object, sorting occurs when a subsequent **Recordset** object is created from that object. The **Sort** property setting overrides any sort order specified for a **[QueryDef](querydef-object-dao.md)** object.</span></span>

<span data-ttu-id="5369c-112">El criterio de ordenación predeterminado es ascendente (de A a Z, o de 0 a 100).</span><span class="sxs-lookup"><span data-stu-id="5369c-112">The default sort order is ascending (A to Z or 0 to 100).</span></span>

<span data-ttu-id="5369c-113">La propiedad **Sort** no se aplica a los objetos **Recordset** de tipo tabla o de tipo de sólo avance.</span><span class="sxs-lookup"><span data-stu-id="5369c-113">The **Sort** property doesn't apply to table– or forward–only–type **Recordset** objects.</span></span> <span data-ttu-id="5369c-114">Para ordenar un objeto **Recordset** de tipo tabla, utilice la propiedad **[Index](recordset2-index-property-dao.md)** .</span><span class="sxs-lookup"><span data-stu-id="5369c-114">To sort a table–type **Recordset** object, use the **[Index](recordset2-index-property-dao.md)** property.</span></span>


> [!NOTE]
> <P><span data-ttu-id="5369c-115">[!NOTA] En muchos casos, es más rápido abrir un nuevo objeto <STRONG>Recordset</STRONG> mediante una instrucción SQL que incluya los criterios de ordenación.</span><span class="sxs-lookup"><span data-stu-id="5369c-115">In many cases, it's faster to open a new <STRONG>Recordset</STRONG> object by using an SQL statement that includes the sorting criteria.</span></span></P>



## <a name="example"></a><span data-ttu-id="5369c-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5369c-116">Example</span></span>

<span data-ttu-id="5369c-p103">En este ejemplo se cambia el valor de la propiedad **Sort** y se crea un nuevo objeto **Recordset** para demostrar el uso de dicha propiedad. Para que este procedimiento se ejecute se necesita la función SortOutput.</span><span class="sxs-lookup"><span data-stu-id="5369c-p103">This example demonstrates the **Sort** property by changing its value and creating a new **Recordset**. The SortOutput function is required for this procedure to run.</span></span>

```vb
    Sub SortX() 
     
     Dim dbsNorthwind As Database 
     Dim rstEmployees As Recordset2 
     Dim rstSortEmployees As Recordset2 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees", _ 
     dbOpenDynaset) 
     
     With rstEmployees 
     SortOutput "Original Recordset:", rstEmployees 
     .Sort = "LastName, FirstName" 
     ' Print report showing Sort property and record order. 
     SortOutput _ 
     "Recordset after changing Sort property:", _ 
     rstEmployees 
     ' Open new Recordset from current one. 
     Set rstSortEmployees = .OpenRecordset 
     ' Print report showing Sort property and record order. 
     SortOutput "New Recordset:", rstSortEmployees 
     rstSortEmployees.Close 
     .Close 
     End With 
     
     dbsNorthwind.Close 
     
    End Sub 
     
    Function SortOutput(strTemp As String, _ 
     rstTemp As Recordset) 
     
     With rstTemp 
     Debug.Print strTemp 
     Debug.Print " Sort = " & _ 
     IIf(.Sort <> "", .Sort, "[Empty]") 
     .MoveFirst 
     
     ' Enumerate Recordset. 
     Do While Not .EOF 
     Debug.Print " " & !LastName & _ 
     ", " & !FirstName 
     .MoveNext 
     Loop 
     
     End With 
     
    End Function 
```

<br/>

<span data-ttu-id="5369c-p104">Cuando se conocen los datos que quieren seleccionar, suele ser más eficaz crear un objeto **Recordset** con una instrucción SQL. En este ejemplo se muestra cómo se puede crear un objeto **Recordset** y obtener los mismos resultados que en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="5369c-p104">When you know the data you want to select, it's usually more efficient to create a **Recordset** with an SQL statement. This example shows how you can create just one **Recordset** and obtain the same results as in the preceding example.</span></span>

```vb
    Sub SortX2() 
     
     Dim dbsNorthwind As Database 
     Dim rstEmployees As Recordset 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     ' Open a Recordset from an SQL statement that specifies a 
     ' sort order. 
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("SELECT * " & _ 
     "FROM Employees ORDER BY LastName, FirstName", _ 
     dbOpenDynaset) 
     
     dbsNorthwind.Close 
     
    End Sub
```