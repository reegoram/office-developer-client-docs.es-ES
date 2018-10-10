---
title: Objeto Recordset (DAO)
TOCTitle: Recordset Object
ms:assetid: 9774232c-e6da-175b-fc7f-ed2ab7908fa0
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197799(v=office.15)
ms:contentKeyID: 48546469
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3fb327b77a9b17ef83ef48cbe5f9e657f859687b
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25484372"
---
# <a name="recordset-object-dao"></a><span data-ttu-id="1eb7f-102">Objeto Recordset (DAO)</span><span class="sxs-lookup"><span data-stu-id="1eb7f-102">Recordset Object (DAO)</span></span>

<span data-ttu-id="1eb7f-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="1eb7f-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="1eb7f-104">Un objeto **Recordset** representa los registros de una tabla base o los registros que son el resultado de ejecutar una consulta.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-104">A **Recordset** object represents the records in a base table or the records that result from running a query.</span></span>

## <a name="remarks"></a><span data-ttu-id="1eb7f-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1eb7f-105">Remarks</span></span>

<span data-ttu-id="1eb7f-p101">Los objetos **Recordset** se usan para manipular los datos de una base de datos en el nivel de registro. Al usar objetos DAO, los datos se manipulan casi por completo con objetos **Recordset**. Todos los objetos **Recordset** se construyen con registros (filas) y campos (columnas). Hay cinco tipos de objetos **Recordset**:</span><span class="sxs-lookup"><span data-stu-id="1eb7f-p101">You use **Recordset** objects to manipulate data in a database at the record level. When you use DAO objects, you manipulate data almost entirely using **Recordset** objects. All **Recordset** objects are constructed using records (rows) and fields (columns). There are five types of **Recordset** objects:</span></span>

- <span data-ttu-id="1eb7f-110">Conjunto de registros de tipo tabla: la representación en código de una tabla base que puede utilizar para agregar, cambiar o eliminar registros de una sola tabla de base de datos (solo áreas de trabajo de Microsoft Access).</span><span class="sxs-lookup"><span data-stu-id="1eb7f-110">Table-type Recordset— representation in code of a base table that you can use to add, change, or delete records from a single database table (Microsoft Access workspaces only).</span></span>

- <span data-ttu-id="1eb7f-p102">Conjunto de registros de tipo conjunto de registros dinámicos: el resultado de una consulta que puede tener registros actualizables. Un objeto **Recordset** de tipo conjunto de registros dinámicos es un conjunto dinámico de registros que puede usar para agregar, cambiar o eliminar registros de una o varias tablas de base de datos subyacentes. Un objeto **Recordset** de tipo conjunto de registros dinámicos puede contener campos de una o varias tablas de una base de datos. Este tipo corresponde a un cursor de conjunto de claves ODBC.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-p102">Dynaset-type Recordset— the result of a query that can have updatable records. A dynaset-type **Recordset** object is a dynamic set of records that you can use to add, change, or delete records from an underlying database table or tables. A dynaset-type **Recordset** object can contain fields from one or more tables in a database. This type corresponds to an ODBC keyset cursor.</span></span>

- <span data-ttu-id="1eb7f-p103">Conjunto de registros de tipo instantánea: una copia estática de un conjunto de registros que puede utilizar para buscar datos o generar informes. Un objeto **Recordset** de tipo instantánea puede contener campos de una o varias tablas de una base de datos, pero no se puede actualizar. Este tipo corresponde a un cursor estático ODBC.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-p103">Snapshot-type Recordset— a static copy of a set of records that you can use to find data or generate reports. A snapshot-type **Recordset** object can contain fields from one or more tables in a database but can't be updated. This type corresponds to an ODBC static cursor.</span></span>

- <span data-ttu-id="1eb7f-p104">Conjunto de registros de tipo de solo avance: igual que el de tipo instantánea, con la excepción de que no se proporciona ningún cursor. Solo puede avanzar por los registros hacia delante. Mejora el rendimiento en las situaciones en las que solo es necesario pasar una vez por un conjunto de resultados. Este tipo corresponde a un cursor de solo avance ODBC.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-p104">Forward-only-type Recordset— identical to a snapshot except that no cursor is provided. You can only scroll forward through records. This improves performance in situations where you only need to make a single pass through a result set. This type corresponds to an ODBC forward-only cursor.</span></span>

- <span data-ttu-id="1eb7f-p105">Conjunto de datos de tipo dinámico: un conjunto de resultados de una consulta a partir de una o más tablas cuyos registros puede agregar, cambiar o eliminar desde una consulta que devuelve filas. Además, los registros que agreguen, eliminen o editen otros usuarios en las tablas base también aparecerán en el **Recordset**. Este tipo corresponde a un cursor dinámico ODBC (solo áreas de trabajo de ODBCDirect).</span><span class="sxs-lookup"><span data-stu-id="1eb7f-p105">Dynamic-type Recordset— a query result set from one or more base tables in which you can add, change, or delete records from a row-returning query. Further, records other users add, delete, or edit in the base tables also appear in your **Recordset**. This type corresponds to an ODBC dynamic cursor (ODBCDirect workspaces only).</span></span>

> [!NOTE]
> <span data-ttu-id="1eb7f-p106">[!NOTA] Las áreas de trabajo de ODBCDirect no se admiten en Microsoft Access 2013. Utilice ADO si quiere acceder a orígenes de datos externos sin usar el motor de base de datos de Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-p106">ODBCDirect workspaces are not supported in Microsoft Access 2013. Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span>

<span data-ttu-id="1eb7f-127">Puede elegir el tipo de objeto **Recordset** que desea crear con el argumento type del método **OpenRecordset** .</span><span class="sxs-lookup"><span data-stu-id="1eb7f-127">You can choose the type of **Recordset** object you want to create using the type argument of the **OpenRecordset** method.</span></span>

<span data-ttu-id="1eb7f-128">En un área de trabajo de Microsoft Access, si no se especifica un tipo, DAO intenta crear el tipo de **objeto Recordset** con la mayoría de las funciones disponibles, empezando por tabla.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-128">In a Microsoft Access workspace, if you don't specify a type, DAO attempts to create the type of **Recordset** with the most functionality available, starting with table.</span></span> <span data-ttu-id="1eb7f-129">Si este tipo no está disponible, DAO intenta un dynaset, a continuación, una instantánea y, por último, un objeto **Recordset** de tipo de sólo avance.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-129">If this type isn't available, DAO attempts a dynaset, then a snapshot, and finally a forward-only type **Recordset** object.</span></span>

<span data-ttu-id="1eb7f-130">En un área de trabajo de ODBCDirect, si no se especifica un tipo, DAO intenta crear el tipo de **objeto Recordset** con la respuesta de consulta más rápida, comenzando con sólo avance.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-130">In an ODBCDirect workspace, if you don't specify a type, DAO attempts to create the type of **Recordset** with the fastest query response, starting with forward-only.</span></span> <span data-ttu-id="1eb7f-131">Si este tipo no está disponible, DAO intenta una instantánea, a continuación, un dynaset y, finalmente, un objeto de **conjunto de registros** de tipo dinámico.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-131">If this type isn't available, DAO attempts a snapshot, then a dynaset, and finally a dynamic- type **Recordset** object.</span></span>

<span data-ttu-id="1eb7f-p109">Al crear un objeto **Recordset** con un objeto **[TableDef](tabledef-object-dao.md)** no vinculado en un área de trabajo de Microsoft Access, se crean objetos **Recordset** de tipo tabla. Con las tablas vinculadas y las tablas de bases de datos ODBC conectadas a un motor de base de datos de Microsoft Access, solo se pueden crear objetos **Recordset** de tipo conjunto de registros dinámicos o de tipo instantánea.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-p109">When creating a **Recordset** object using a non-linked **[TableDef](tabledef-object-dao.md)** object in a Microsoft Access workspace, table-type **Recordset** objects are created. Only dynaset-type or snapshot-type **Recordset** objects can be created with linked tables or tables in Microsoft Access database engine-connected ODBC databases.</span></span>

<span data-ttu-id="1eb7f-134">Cuando abra el objeto, se agregará automáticamente un nuevo objeto **Recordset** a la colección **Recordsets** y, cuando lo cierre, se quitará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-134">A new **Recordset** object is automatically added to the **Recordsets** collection when you open the object, and is automatically removed when you close it.</span></span>

> [!NOTE]
> <span data-ttu-id="1eb7f-p110">[!NOTA] Si usa variables para representar un objeto **Recordset** y el objeto **Database** que contiene el **Recordset**, asegúrese de que las variables tengan el mismo ámbito, o la misma duración. Por ejemplo, si declara una variable pública que representa un objeto **Recordset**, asegúrese de que la variable que representa al objeto **Database** que contiene el **Recordset** también es pública o está declarada en un procedimiento **Sub** o **Function** con la palabra clave **Static**.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-p110">If you use variables to represent a **Recordset** object and the **Database** object that contains the **Recordset**, make sure the variables have the same scope, or lifetime. For example, if you declare a public variable that represents a **Recordset** object, make sure the variable that represents the **Database** containing the **Recordset** is also public, or is declared in a **Sub** or **Function** procedure using the **Static** keyword.</span></span>

<span data-ttu-id="1eb7f-p111">Puede crear tantas variables de objeto **Recordset** como necesite. Varios objetos **Recordset** pueden acceder a las mismas tablas y consultas y a los mismos campos sin entrar en conflicto.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-p111">You can create as many **Recordset** object variables as needed. Different **Recordset** objects can access the same tables, queries, and fields without conflicting.</span></span>

<span data-ttu-id="1eb7f-139">Dynaset, instantánea y objetos **Recordset** de tipo forward – only se almacenan en la memoria local.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-139">Dynaset–, snapshot–, and forward–only–type **Recordset** objects are stored in local memory.</span></span> <span data-ttu-id="1eb7f-140">Si no hay suficiente espacio en la memoria local para almacenar los datos, el motor de base de datos de Microsoft Access guarda los datos adicionales en el espacio en disco de TEMP.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-140">If there isn't enough space in local memory to store the data, the Microsoft Access database engine saves the additional data to TEMP disk space.</span></span> <span data-ttu-id="1eb7f-141">Si este espacio se agota, se producirá un error capturable.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-141">If this space is exhausted, a trappable error occurs.</span></span>

<span data-ttu-id="1eb7f-p113">La colección predeterminada de un objeto **Recordset** es la colección **Fields**, y la propiedad predeterminada de un objeto **[Field](field-object-dao.md)** es la propiedad **[Value](field-value-property-dao.md)**. Aproveche estas opciones predeterminadas para simplificar el código.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-p113">The default collection of a **Recordset** object is the **Fields** collection, and the default property of a **[Field](field-object-dao.md)** object is the **[Value](field-value-property-dao.md)** property. Use these defaults to simplify your code.</span></span>

<span data-ttu-id="1eb7f-p114">Al crear un objeto **Recordset**, el objeto actual se coloca en el primer registro si hay algún registro. Si no hay ningún registro, el valor de la propiedad **RecordCount** será 0 y los valores de las propiedades **BOF** y **EOF** serán **True**.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-p114">When you create a **Recordset** object, the current record is positioned to the first record if there are any records. If there are no records, the **RecordCount** property setting is 0, and the **BOF** and **EOF** property settings are **True**.</span></span>

<span data-ttu-id="1eb7f-p115">Puede usar los métodos **MoveNext**, **MovePrevious**, **MoveFirst** y **MoveLast** para recolocar el registro actual. Los objetos **Recordset** de tipo de solo avance admiten únicamente el método **MoveNext**. Al usar los métodos Move para visitar cada registro (o “caminar” por el **Recordset**), puede usar las propiedades **BOF** y **EOF** para consultar el principio y el final del objeto **Recordset**.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-p115">You can use the **MoveNext**, **MovePrevious**, **MoveFirst**, and **MoveLast** methods to reposition the current record. Forward–only–type **Recordset** objects support only the **MoveNext** method. When using the Move methods to visit each record (or "walk" through the **Recordset**), you can use the **BOF** and **EOF** properties to check for the beginning or end of the **Recordset** object.</span></span>

<span data-ttu-id="1eb7f-p116">Con los objetos **Recordset** de tipo conjunto de registros dinámicos y de tipo instantánea en un área de trabajo de Microsoft Access, puede usar también los métodos Find, como **FindFirst**, para buscar un determinado registro según ciertos criterios. Si no se encuentra el registro, la propiedad **NoMatch** se configurará como **True**. En el caso de los objetos **Recordset** de tipo tabla, puede examinar los registros con el método **Seek**.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-p116">With dynaset- and snapshot-type **Recordset** objects in a Microsoft Access workspace, you can also use the Find methods, such as **FindFirst**, to locate a specific record based on criteria. If the record isn't found, the **NoMatch** property is set to **True**. For table-type **Recordset** objects, you can scan records using the **Seek** method.</span></span>

<span data-ttu-id="1eb7f-152">La propiedad **Type** indica el tipo de objeto **Recordset** creado, y la propiedad **Updatable** indica si puede cambiar los registros del objeto.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-152">The **Type** property indicates the type of **Recordset** object created, and the **Updatable** property indicates whether you can change the object's records.</span></span>

<span data-ttu-id="1eb7f-153">La información sobre la estructura de una tabla base, como los nombres y los tipos de datos de cada objeto **Field** y los objetos **Index**, se almacena en un objeto **TableDef**.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-153">Information about the structure of a base table, such as the names and data types of each **Field** object and any **Index** objects, is stored in a **TableDef** object.</span></span>

<span data-ttu-id="1eb7f-154">Para hacer referencia a un objeto **Recordset** de una colección por su número ordinal o por su valor de la propiedad **Name**, use uno de los siguientes formatos de sintaxis:</span><span class="sxs-lookup"><span data-stu-id="1eb7f-154">To refer to a **Recordset** object in a collection by its ordinal number or by its **Name** property setting, use any of the following syntax forms:</span></span>

- <span data-ttu-id="1eb7f-155">**Recordsets** (0)</span><span class="sxs-lookup"><span data-stu-id="1eb7f-155">**Recordsets**(0)</span></span>

- <span data-ttu-id="1eb7f-156">**Conjuntos de registros** ("nombre")</span><span class="sxs-lookup"><span data-stu-id="1eb7f-156">**Recordsets**("name")</span></span>

- <span data-ttu-id="1eb7f-157">**Conjuntos de registros**\!\[nombre\]</span><span class="sxs-lookup"><span data-stu-id="1eb7f-157">**Recordsets**\!\[name\]</span></span>

> [!NOTE]
> <span data-ttu-id="1eb7f-p117">[!NOTA] Se puede abrir un objeto **Recordset** desde el mismo origen de datos o base de datos más de una vez, con lo que se crean nombres duplicados en la colección **Recordsets**. Debe asignar los objetos **Recordset** a variables de objeto y hacer referencia a ellos por el nombre de la variable.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-p117">You can open a **Recordset** object from the same data source or database more than once, creating duplicate names in the **Recordsets** collection. You should assign **Recordset** objects to object variables and refer to them by variable name.</span></span>

## <a name="example"></a><span data-ttu-id="1eb7f-160">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1eb7f-160">Example</span></span>

<span data-ttu-id="1eb7f-161">A continuación se ofrece una demostración de objetos **Recordset** y la colección **Recordsets**. En este ejemplo, se abren cuatro tipos diferentes de objetos **Recordsets**, se enumera la colección Recordsets del objeto **Database** actual y se enumera la colección **Properties** de cada objeto **Recordset**.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-161">This example demonstrates **Recordset** objects and the **Recordsets** collection by opening four different types of **Recordsets**, enumerating the Recordsets collection of the current **Database**, and enumerating the **Properties** collection of each **Recordset**.</span></span>

```vb
    Sub RecordsetX() 
     
       Dim dbsNorthwind As Database 
       Dim rstTable As Recordset 
       Dim rstDynaset As Recordset 
       Dim rstSnapshot As Recordset 
       Dim rstForwardOnly As Recordset 
       Dim rstLoop As Recordset 
       Dim prpLoop As Property 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
       With dbsNorthwind 
     
          ' Open one of each type of Recordset object. 
          Set rstTable = .OpenRecordset("Categories", _ 
             dbOpenTable) 
          Set rstDynaset = .OpenRecordset("Employees", _ 
             dbOpenDynaset) 
          Set rstSnapshot = .OpenRecordset("Shippers", _ 
             dbOpenSnapshot) 
          Set rstForwardOnly = .OpenRecordset _  
             ("Employees", dbOpenForwardOnly) 
     
          Debug.Print "Recordsets in Recordsets " & _ 
             "collection of dbsNorthwind" 
     
          ' Enumerate Recordsets collection. 
          For Each rstLoop In .Recordsets 
     
             With rstLoop 
                Debug.Print "  " & .Name 
     
                ' Enumerate Properties collection of each 
                ' Recordset object. Trap for any  
                ' properties whose values are invalid in  
                ' this context. 
                For Each prpLoop In .Properties 
                   On Error Resume Next 
                   If prpLoop <> "" Then Debug.Print _ 
                      "    " & prpLoop.Name & _ 
                      " = " & prpLoop 
                   On Error GoTo 0 
                Next prpLoop 
     
             End With 
     
          Next rstLoop 
     
          rstTable.Close 
          rstDynaset.Close 
          rstSnapshot.Close 
          rstForwardOnly.Close 
     
          .Close 
       End With 
     
    End Sub 
```

<br/>

<span data-ttu-id="1eb7f-p118">En este ejemplo, se usa el método **OpenRecordset** para abrir cinco objetos **Recordset** diferentes y mostrar su contenido. Para que este procedimiento se ejecute, es necesario el procedimiento OpenRecordsetOutput.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-p118">This example uses the **OpenRecordset** method to open five different **Recordset** objects and display their contents. The OpenRecordsetOutput procedure is required for this procedure to run.</span></span>

```vb
    Sub OpenRecordsetX() 
     
       Dim wrkAcc As Workspace 
       Dim wrkODBC As Workspace 
       Dim dbsNorthwind As Database 
       Dim conPubs As Connection 
       Dim rstTemp As Recordset 
       Dim rstTemp2 As Recordset 
     
       ' Open Microsoft Access and ODBCDirect workspaces, Microsoft  
       ' Access database, and ODBCDirect connection. 
       Set wrkAcc = CreateWorkspace("", "admin", "", dbUseJet) 
       Set wrkODBC = CreateWorkspace("", "admin", "", dbUseODBC) 
       Set dbsNorthwind = wrkAcc.OpenDatabase("Northwind.mdb") 
        
       ' Note: The DSN referenced below must be set to  
       '       use Microsoft Windows NT Authentication Mode to  
       '       authorize user access to the Microsoft SQL Server. 
       Set conPubs = wrkODBC.OpenConnection("", , , _ 
          "ODBC;DATABASE=pubs;DSN=Publishers") 
     
       ' Open five different Recordset objects and display the  
       ' contents of each. 
     
       Debug.Print "Opening forward-only-type recordset " & _ 
          "where the source is a QueryDef object..." 
       Set rstTemp = dbsNorthwind.OpenRecordset( _ 
          "Ten Most Expensive Products", dbOpenForwardOnly) 
       OpenRecordsetOutput rstTemp 
     
       Debug.Print "Opening read-only dynaset-type " & _ 
          "recordset where the source is an SQL statement..." 
       Set rstTemp = dbsNorthwind.OpenRecordset( _ 
          "SELECT * FROM Employees", dbOpenDynaset, dbReadOnly) 
       OpenRecordsetOutput rstTemp 
     
       ' Use the Filter property to retrieve only certain  
       ' records with the next OpenRecordset call. 
       Debug.Print "Opening recordset from existing " & _ 
          "Recordset object to filter records..." 
       rstTemp.Filter = "LastName >= 'M'" 
       Set rstTemp2 = rstTemp.OpenRecordset() 
       OpenRecordsetOutput rstTemp2 
     
       Debug.Print "Opening dynamic-type recordset from " & _ 
          "an ODBC connection..." 
       Set rstTemp = conPubs.OpenRecordset( _ 
          "SELECT * FROM stores", dbOpenDynamic) 
       OpenRecordsetOutput rstTemp 
     
       ' Use the StillExecuting property to determine when the  
       ' Recordset is ready for manipulation. 
       Debug.Print "Opening snapshot-type recordset based " & _ 
          "on asynchronous query to ODBC connection..." 
       Set rstTemp = conPubs.OpenRecordset("publishers", _ 
          dbOpenSnapshot, dbRunAsync) 
       Do While rstTemp.StillExecuting 
          Debug.Print "  [still executing...]" 
       Loop 
       OpenRecordsetOutput rstTemp 
     
       rstTemp.Close 
       dbsNorthwind.Close 
       conPubs.Close 
       wrkAcc.Close 
       wrkODBC.Close 
     
    End Sub 
     
    Sub OpenRecordsetOutput(rstOutput As Recordset) 
     
       ' Enumerate the specified Recordset object. 
       With rstOutput 
          Do While Not .EOF 
             Debug.Print , .Fields(0), .Fields(1) 
             .MoveNext 
          Loop 
       End With 
     
    End Sub 
```

<br/>

<span data-ttu-id="1eb7f-164">En este ejemplo, se abre un objeto **Recordset** de tipo dinámico y se enumeran sus registros.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-164">This example opens a dynamic-type **Recordset** object and enumerates its records.</span></span>

```vb
    Sub dbOpenDynamicX() 
     
       Dim wrkMain As Workspace 
       Dim conMain As Connection 
       Dim qdfTemp As QueryDef 
       Dim rstTemp As Recordset 
       Dim strSQL As String 
       Dim intLoop As Integer 
     
       ' Create ODBC workspace and open connection to 
       ' SQL Server database. 
       Set wrkMain = CreateWorkspace("ODBCWorkspace", _ 
          "admin", "", dbUseODBC) 
           
       ' Note: The DSN referenced below must be configured to  
       '       use Microsoft Windows NT Authentication Mode to  
       '       authorize user access to the Microsoft SQL Server.     
       Set conMain = wrkMain.OpenConnection("Publishers", _ 
          dbDriverNoPrompt, False, _ 
          "ODBC;DATABASE=pubs;DSN=Publishers") 
           
       ' Open dynamic-type recordset. 
       Set rstTemp = _ 
          conMain.OpenRecordset("authors", _ 
          dbOpenDynamic) 
     
       With rstTemp 
          Debug.Print "Dynamic-type recordset: " & .Name 
     
          ' Enumerate records. 
          Do While Not .EOF 
             Debug.Print "    " & !au_lname & ", " & _ 
                !au_fname 
             .MoveNext 
          Loop 
     
          .Close 
       End With 
     
       conMain.Close 
       wrkMain.Close 
     
    End Sub 
```

<br/>

<span data-ttu-id="1eb7f-165">En este ejemplo, se abre un **Recordset** de tipo conjunto de registros dinámicos y se muestra hasta qué punto se pueden actualizar sus campos.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-165">This example opens a dynaset-type **Recordset** and shows the extent to which its fields are updatable.</span></span>

```vb
    Sub dbOpenDynasetX() 
     
       Dim dbsNorthwind As Database 
       Dim rstInvoices As Recordset 
       Dim fldLoop As Field 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
       Set rstInvoices = _ 
          dbsNorthwind.OpenRecordset("Invoices", dbOpenDynaset) 
     
       With rstInvoices 
          Debug.Print "Dynaset-type recordset: " & .Name 
     
          If .Updatable Then 
             Debug.Print "  Updatable fields:" 
     
             ' Enumerate Fields collection of dynaset-type 
             ' Recordset object, print only updatable 
             ' fields. 
             For Each fldLoop In .Fields 
                If fldLoop.DataUpdatable Then 
                   Debug.Print "    " & fldLoop.Name 
                End If 
             Next fldLoop 
     
          End If 
     
          .Close 
       End With 
     
       dbsNorthwind.Close 
     
    End Sub 
```

<br/>

<span data-ttu-id="1eb7f-166">En este ejemplo, se abre un **Recordset** de tipo de solo avance, se muestran sus características de solo lectura y se avanza por el **Recordset** con el método **MoveNext**.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-166">This example opens a forward-only-type **Recordset**, demonstrates its read-only characteristics, and steps through the **Recordset** with the **MoveNext** method.</span></span>

```vb 
Sub dbOpenForwardOnlyX() 
 
   Dim dbsNorthwind As Database 
   Dim rstEmployees As Recordset 
   Dim fldLoop As Field 
 
   Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
   ' Open a forward-only-type Recordset object. Only the  
   ' MoveNext and Move methods may be used to navigate  
   ' through the recordset. 
   Set rstEmployees = _ 
      dbsNorthwind.OpenRecordset("Employees", _ 
      dbOpenForwardOnly) 
 
   With rstEmployees 
      Debug.Print "Forward-only-type recordset: " & _ 
         .Name & ", Updatable = " & .Updatable 
 
      Debug.Print "  Field - DataUpdatable" 
      ' Enumerate Fields collection, printing the Name and  
      ' DataUpdatable properties of each Field object. 
      For Each fldLoop In .Fields 
         Debug.Print "    " & _ 
            fldLoop.Name & " - " & fldLoop.DataUpdatable 
      Next fldLoop 
 
      Debug.Print "  Data" 
      ' Enumerate the recordset. 
      Do While Not .EOF 
         Debug.Print "    " & !FirstName & " " & _ 
            !LastName 
         .MoveNext 
      Loop 
 
      .Close 
   End With 
 
   dbsNorthwind.Close 
 
End Sub 
```

<br/>

<span data-ttu-id="1eb7f-167">En este ejemplo, se abre un **Recordset** de tipo instantánea y se muestran sus características de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-167">This example opens a snapshot-type **Recordset** and demonstrates its read-only characteristics.</span></span>

```vb
    Sub dbOpenSnapshotX() 
     
       Dim dbsNorthwind As Database 
       Dim rstEmployees As Recordset 
       Dim prpLoop As Property 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
       Set rstEmployees = _ 
          dbsNorthwind.OpenRecordset("Employees", _ 
          dbOpenSnapshot) 
     
       With rstEmployees 
          Debug.Print "Snapshot-type recordset: " & _ 
             .Name 
     
          ' Enumerate the Properties collection of the 
          ' snapshot-type Recordset object, trapping for 
          ' any properties whose values are invalid in  
          ' this context. 
          For Each prpLoop In .Properties 
             On Error Resume Next 
             Debug.Print "  " & _ 
                prpLoop.Name & " = " & prpLoop 
             On Error Goto 0 
          Next prpLoop 
     
          .Close 
       End With 
     
       dbsNorthwind.Close 
     
    End Sub 
```

<br/>

<span data-ttu-id="1eb7f-168">En este ejemplo, se abre un **Recordset** de tipo tabla, se establece su propiedad **Index** y se enumeran sus registros.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-168">This example opens a table-type **Recordset**, sets its **Index** property, and enumerates its records.</span></span>

```vb
    Sub dbOpenTableX() 
     
       Dim dbsNorthwind As Database 
       Dim rstEmployees As Recordset 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
       ' dbOpenTable is default. 
       Set rstEmployees = _ 
          dbsNorthwind.OpenRecordset("Employees") 
     
       With rstEmployees 
          Debug.Print "Table-type recordset: " & .Name 
     
          ' Use predefined index. 
          .Index = "LastName" 
          Debug.Print "  Index = " & .Index 
     
          ' Enumerate records. 
          Do While Not .EOF 
             Debug.Print "    " & !LastName & ", " & _ 
                !FirstName 
             .MoveNext 
          Loop 
     
          .Close 
       End With 
     
       dbsNorthwind.Close 
     
    End Sub 
```

<br/>

<span data-ttu-id="1eb7f-169">En el siguiente ejemplo, se muestra cómo usar el método Seek para buscar un registro en una tabla vinculada.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-169">The following example shows how to use the Seek method to find a record in a linked table.</span></span>

<span data-ttu-id="1eb7f-170">**Código de ejemplo proporcionado por** la [referencia del programador de Microsoft Access 2010](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span><span class="sxs-lookup"><span data-stu-id="1eb7f-170">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>


```vb
    Sub TestSeek()
        ' Get the path to the external database that contains
        ' the tblCustomers table we're going to search.
        Dim strMyExternalDatabase
        Dim dbs    As DAO.Database
        Dim dbsExt As DAO.Database
        Dim rst    As DAO.Recordset
        Dim tdf    As DAO.TableDef
        
        Set dbs = CurrentDb()
        Set tdf = dbs.TableDefs("tblCustomers")
        strMyExternalDatabase = Mid(tdf.Connect, 11)
        
        'Open the database that contains the table that is linked
        Set dbsExt = OpenDatabase(strMyExternalDatabase)
        
        'Open a table-type recordset against the external table
        Set rst = dbsExt.OpenRecordset("tblCustomers", dbOpenTable)
        
        'Specify which index to search on
        rst.Index = "PrimaryKey"
        
        'Specify the criteria
        rst.Seek "=", 123
        
        'Check the result
        If rst.NoMatch Then
            MsgBox "Record not found."
        Else
            MsgBox "Customer name: " & rst!CustName
        End If
        
        rst.Close
        dbs.Close
        dbsExt.Close
        Set rst = Nothing
        Set tdf = Nothing
        Set dbs = Nothing
        
        
    End Sub
```

<br/>

<span data-ttu-id="1eb7f-171">En el ejemplo siguiente vemos cómo abrir un Recordset basado en una consulta de parámetros.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-171">The following example shows how to open a Recordset that is based on a parameter query.</span></span>

```vb
    Dim dbs As DAO.Database
    Dim qdf As DAO.QueryDef
    Dim rst As DAO.Recordset
    
    Set dbs = CurrentDb
    
    'Get the parameter query
    Set qfd = dbs.QueryDefs("qryMyParameterQuery")
    
    'Supply the parameter value
    qdf.Parameters("EnterStartDate") = Date
    qdf.Parameters("EnterEndDate") = Date + 7
    
    'Open a Recordset based on the parameter query
    Set rst = qdf.OpenRecordset()
```

<br/>

<span data-ttu-id="1eb7f-172">En el siguiente ejemplo, se muestra cómo abrir un Recordset a partir de una tabla o una consulta.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-172">The following example shows how to open a Recordset based on a table or a query.</span></span>

```vb
    Dim dbs As DAO.Database
    Dim rsTable As DAO.Recordset
    Dim rsQuery As DAO.Recordset
    
    Set dbs = CurrentDb
    
    'Open a table-type Recordset
    Set rsTable = dbs.OpenRecordset("Table1", dbOpenTable)
    
    'Open a dynaset-type Recordset using a saved query
    Set rsQuery = dbs.OpenRecordset("qryMyQuery", dbOpenDynaset)
```

<br/>

<span data-ttu-id="1eb7f-173">En el siguiente ejemplo, se muestra cómo abrir un Recordset de acuerdo con una instrucción del Lenguaje de consulta estructurado (SQL).</span><span class="sxs-lookup"><span data-stu-id="1eb7f-173">The following example shows how to open a Recordset based on a Structured Query Language (SQL) statement.</span></span>

```vb
    Dim dbs As DAO.Database
    Dim rsSQL As DAO.Recordset
    Dim strSQL As String
    
    Set dbs = CurrentDb
    
    'Open a snapshot-type Recordset based on an SQL statement
    strSQL = "SELECT * FROM Table1 WHERE Field2 = 33"
    Set rsSQL = dbs.OpenRecordset(strSQL, dbOpenSnapshot)
```

<br/>

<span data-ttu-id="1eb7f-174">En el siguiente ejemplo, se muestra cómo usar los métodos FindFirst y FindNext para buscar un registro en un Recordset.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-174">The following example shows how to use the FindFirst and FindNext methods to find a record in a Recordset.</span></span>

```vb
    Sub FindOrgName()
    
        Dim dbs As DAO.Database
        Dim rst As DAO.Recordset
        
        'Get the database and Recordset
        Set dbs = CurrentDb
        Set rst = dbs.OpenRecordset("tblCustomers")
    
        'Search for the first matching record   
        rst.FindFirst "[OrgName] LIKE '*parts*'"
        
        'Check the result
        If rst.NoMatch Then
            MsgBox "Record not found."
            GotTo Cleanup
        Else
            Do While Not rst.NoMatch
                MsgBox "Customer name: " & rst!CustName
                rst.FindNext "[OrgName] LIKE '*parts*'"
            Loop
    
            'Search for the next matching record
            rst.FindNext "[OrgName] LIKE '*parts*'"
        End If
       
        Cleanup:
            rst.Close
            Set rst = Nothing
            Set dbs = Nothing
    
    End Sub
```

<br/>

<span data-ttu-id="1eb7f-175">En el siguiente ejemplo, se muestra cómo copiar los resultados de una consulta a una hoja de cálculo de un nuevo libro de Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="1eb7f-175">The following example shows how to copy the results of a query to a worksheet in a new Microsoft Excel workbook.</span></span>

```vb
    Public Sub CopyDataFromQuery( _
        xlApp As Excel.Application, _
        strQueryName As String)
    
        ' If the xlApp object exists
        If Not xlApp Is Nothing Then
        
            ' If the Workbook exists
            If xlApp.Workbooks.Count = 1 Then
            
                ' Create Recrodset Object from the Query
                Dim rsQuery As DAO.Recordset
                Set rsQuery = Application.CurrentDb.OpenRecordset(strQueryName)
                
                ' Get the Cells object
                Dim Cells As Object
                Set Cells = xlApp.Workbooks(1).ActiveSheet.Cells
                
                ' Copy the Data from the Query into the Sheet
                Cells.CopyFromRecordset rsQuery
                
            End If
        End If
    
    End Sub
```
