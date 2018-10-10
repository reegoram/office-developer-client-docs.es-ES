---
title: 'Capítulo 3: Examinar datos'
TOCTitle: 'Chapter 3: Examining Data'
ms:assetid: 73c69134-3127-3344-d5c3-5ecb9e0e958b
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249474(v=office.15)
ms:contentKeyID: 48545648
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 481fbc3bc39f184aeefe6738ac8d2a80fcd1d93f
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25484968"
---
# <a name="chapter-3-examining-data"></a><span data-ttu-id="c06f9-102">Capítulo 3: Examinar datos</span><span class="sxs-lookup"><span data-stu-id="c06f9-102">Chapter 3: Examining Data</span></span>


<span data-ttu-id="c06f9-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="c06f9-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="c06f9-p101">El Capítulo 2 explicaba cómo se recuperan datos de un origen de datos en forma de objeto **Recordset**. En este capítulo se analizará con más detalle el objeto **Recordset**, incluyendo la forma de navegar a través de **Recordset** y ver sus datos.</span><span class="sxs-lookup"><span data-stu-id="c06f9-p101">Chapter 2 explained how to retrieve data from a data source as a **Recordset** object. This chapter will discuss the **Recordset** in more detail, including how to navigate through the **Recordset** and view its data.</span></span>

<span data-ttu-id="c06f9-p102">Los objetos **Recordset** tienen métodos y propiedades que se diseñaron para facilitar el desplazamiento por ellos y examinar su contenido. En función de la funcionalidad admitida por el proveedor, algunas propiedades o métodos de **Recordset** pueden no estar disponibles. Para continuar explorando el objeto **Recordset**, considere un objeto **Recordset** que sería devuelto por la base de datos de ejemplo Neptuno en Microsoft SQL Server 2000, usando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="c06f9-p102">**Recordsets** have methods and properties designed to make it easy to move through them and examine their contents. Depending on the functionality supported by the provider, some **Recordset** methods or properties might not be available. To continue exploring the **Recordset** object, consider a **Recordset** that would be returned from the Northwind sample database on Microsoft SQL Server 2000, using the following code:</span></span>

```vb 
 
'BeginRsTour 
Public Sub RecordsetTour() 
 On Error GoTo ErrHandler: 
 
 Dim objRs As New ADODB.Recordset 
 Dim strSQL As String 
 
 strSQL = "SELECT ProductID, ProductName, UnitPrice FROM Products " & _ 
 "WHERE CategoryID = 7" '7 = Produce 
 
 objRs.Open strSQL, strConnStr, adOpenForwardOnly, _ 
 adLockReadOnly, adCmdText 
 
 'Clean up 
 objRs.Close 
 Set objRs = Nothing 
 Exit Sub 
 
ErrHandler: 
 If Not objRs Is Nothing Then 
 If objRs.State = adStateOpen Then objRs.Close 
 Set objRs = Nothing 
 End If 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
'EndRsTour 
```

<span data-ttu-id="c06f9-p103">Esta consulta SQL devuelve un objeto **Recordset** con cinco filas (registros) y tres columnas (campos). En la tabla siguiente se muestran los valores correspondientes a cada fila.</span><span class="sxs-lookup"><span data-stu-id="c06f9-p103">This SQL query returns a **Recordset** with five rows (records) and three columns (fields). The values for each row are shown in the following table.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c06f9-111">CAMPO 0</span><span class="sxs-lookup"><span data-stu-id="c06f9-111">FIELD 0</span></span><br />
<span data-ttu-id="c06f9-112">Nombre = ProductID</span><span class="sxs-lookup"><span data-stu-id="c06f9-112">Name = ProductID</span></span></p></th>
<th><p><span data-ttu-id="c06f9-113">CAMPO 1</span><span class="sxs-lookup"><span data-stu-id="c06f9-113">FIELD 1</span></span><br />
<span data-ttu-id="c06f9-114">Nombre = ProductName</span><span class="sxs-lookup"><span data-stu-id="c06f9-114">Name = ProductName</span></span></p></th>
<th><p><span data-ttu-id="c06f9-115">CAMPO 2</span><span class="sxs-lookup"><span data-stu-id="c06f9-115">FIELD 2</span></span><br />
<span data-ttu-id="c06f9-116">Nombre = UnitPrice</span><span class="sxs-lookup"><span data-stu-id="c06f9-116">Name = UnitPrice</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c06f9-117">7</span><span class="sxs-lookup"><span data-stu-id="c06f9-117">7</span></span></p></td>
<td><p><span data-ttu-id="c06f9-118">Peras secas orgánicas del tío Bob</span><span class="sxs-lookup"><span data-stu-id="c06f9-118">Uncle Bob's Organic Dried Pears</span></span></p></td>
<td><p><span data-ttu-id="c06f9-119">30.0000</span><span class="sxs-lookup"><span data-stu-id="c06f9-119">30.0000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c06f9-120">14</span><span class="sxs-lookup"><span data-stu-id="c06f9-120">14</span></span></p></td>
<td><p><span data-ttu-id="c06f9-121">Cuajada de judías</span><span class="sxs-lookup"><span data-stu-id="c06f9-121">Tofu</span></span></p></td>
<td><p><span data-ttu-id="c06f9-122">23.2500</span><span class="sxs-lookup"><span data-stu-id="c06f9-122">23.2500</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c06f9-123">28</span><span class="sxs-lookup"><span data-stu-id="c06f9-123">28</span></span></p></td>
<td><p><span data-ttu-id="c06f9-124">Col fermentada Rössle</span><span class="sxs-lookup"><span data-stu-id="c06f9-124">Rssle Sauerkraut</span></span></p></td>
<td><p><span data-ttu-id="c06f9-125">45.6000</span><span class="sxs-lookup"><span data-stu-id="c06f9-125">45.6000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c06f9-126">51</span><span class="sxs-lookup"><span data-stu-id="c06f9-126">51</span></span></p></td>
<td><p><span data-ttu-id="c06f9-127">Manzanas secas Manjimup</span><span class="sxs-lookup"><span data-stu-id="c06f9-127">Manjimup Dried Apples</span></span></p></td>
<td><p><span data-ttu-id="c06f9-128">53.0000</span><span class="sxs-lookup"><span data-stu-id="c06f9-128">53.0000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c06f9-129">74</span><span class="sxs-lookup"><span data-stu-id="c06f9-129">74</span></span></p></td>
<td><p><span data-ttu-id="c06f9-130">Queso de soja Longlife</span><span class="sxs-lookup"><span data-stu-id="c06f9-130">Longlife Tofu</span></span></p></td>
<td><p><span data-ttu-id="c06f9-131">10.0000</span><span class="sxs-lookup"><span data-stu-id="c06f9-131">10.0000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c06f9-132">En la sección siguiente se explicará cómo se localiza la posición actual del cursor en este objeto **Recordset** de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c06f9-132">The next section will explain how to locate the current position of the cursor in this sample **Recordset**.</span></span>
