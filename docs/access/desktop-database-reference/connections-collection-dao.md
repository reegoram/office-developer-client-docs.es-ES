---
title: Connections Collection (DAO)
TOCTitle: Connections Collection
ms:assetid: 65d073be-a84b-e3f2-cb43-b87ffa60e497
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195178(v=office.15)
ms:contentKeyID: 48545330
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: cb8c41917ab6834cda15a706ae550751698543eb
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485369"
---
# <a name="connections-collection-dao"></a><span data-ttu-id="54225-102">Connections Collection (DAO)</span><span class="sxs-lookup"><span data-stu-id="54225-102">Connections Collection (DAO)</span></span>


<span data-ttu-id="54225-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="54225-103">**Applies to**: Access 2013 | Office 2013</span></span>


> [!NOTE]
> <span data-ttu-id="54225-p101">[!NOTA] No se admiten áreas de trabajo de ODBCDirect en Microsoft Access 2013. Use ADO si quiere acceder a orígenes de datos externos sin usar el motor de base de datos de Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="54225-p101">ODBCDirect workspaces are not supported in Microsoft Access 2013. Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span>



<span data-ttu-id="54225-p102">Una colección **Connections** contiene los objetos **Connection** actuales de un objeto **Workspace** (sólo las áreas de trabajo de ODBCDirect).</span><span class="sxs-lookup"><span data-stu-id="54225-p102">A **Connections** collection contains the current **Connection** objects of a **Workspace** object. (ODBCDirect workspaces only).</span></span>

## <a name="remarks"></a><span data-ttu-id="54225-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="54225-108">Remarks</span></span>

<span data-ttu-id="54225-p103">Al abrir un objeto **Connection**, éste se anexa automáticamente a la colección **Connections** del objeto **Workspace**. Al cerrar un objeto **Connection** con el método **[Close](connection-close-method-dao.md)**, este objeto se quita de la colección **Connections**. Debe cerrar todos los objetos **[Recordset](recordset-object-dao.md)** abiertos dentro de **Connection** antes de cerrar el objeto.</span><span class="sxs-lookup"><span data-stu-id="54225-p103">When you open a **Connection** object, it is automatically appended to the **Connections** collection of the **Workspace**. When you close a **Connection** object with the **[Close](connection-close-method-dao.md)** method, it is removed from the **Connections** collection. You should close all open **[Recordset](recordset-object-dao.md)** objects within the **Connection** before closing it.</span></span>

<span data-ttu-id="54225-p104">Al mismo tiempo que abre un objeto **Connection**, se crea el objeto **[Database](database-object-dao.md)** correspondiente y se agrega a la colección **[Databases](databases-collection-dao.md)** en el mismo objeto **Workspace**, y viceversa. De igual forma, al cerrar el objeto **Connection**, se elimina el objeto **Database** correspondiente de la colección **Databases**, y viceversa.</span><span class="sxs-lookup"><span data-stu-id="54225-p104">At the same time you open a **Connection** object, a corresponding **[Database](database-object-dao.md)** object is created and appended to the **[Databases](databases-collection-dao.md)** collection in the same **Workspace**, and vice versa. Similarly, when you close the **Connection**, the corresponding **Database** is deleted from the **Databases** collection, and so on.</span></span>

<span data-ttu-id="54225-p105">El valor de la propiedad **Name** de un objeto **Connection** es una cadena que especifica la ruta del archivo de base de datos. Para hacer referencia a un objeto **Connection** en una colección mediante su número ordinal o mediante el valor de la propiedad **Name**, utilice una de las formas sintácticas siguientes:</span><span class="sxs-lookup"><span data-stu-id="54225-p105">The **Name** property setting of a **Connection** is a string that specifies the path of the database file. To refer to a **Connection** object in a collection by its ordinal number or by its **Name** property setting, use any of the following syntax forms:</span></span>

  - <span data-ttu-id="54225-116">**Connections**(0)</span><span class="sxs-lookup"><span data-stu-id="54225-116">**Connections**(0)</span></span>

  - <span data-ttu-id="54225-117">**Conexiones** ("*nombre*")</span><span class="sxs-lookup"><span data-stu-id="54225-117">**Connections**("*name*")</span></span>

  - <span data-ttu-id="54225-118">**Conexiones de**\!\[*nombre*\]</span><span class="sxs-lookup"><span data-stu-id="54225-118">**Connections**\!\[*name*\]</span></span>


> [!NOTE]
> <P><span data-ttu-id="54225-p106">[!NOTA] Puede abrir el mismo origen de datos varias veces creando nombres duplicados en la colección <STRONG>Connections</STRONG>. Debe asignar objetos <STRONG>Connection</STRONG> a variables de objeto y hacer referencia a ellas mediante el nombre de variable.</span><span class="sxs-lookup"><span data-stu-id="54225-p106">You can open the same data source more than once, creating duplicate names in the <STRONG>Connections</STRONG> collection. You should assign <STRONG>Connection</STRONG> objects to object variables and refer to them by variable name.</span></span></P>



## <a name="example"></a><span data-ttu-id="54225-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="54225-121">Example</span></span>

<span data-ttu-id="54225-122">En este ejemplo se utiliza el objeto **Connection** y la colección **Connections** para abrir un objeto **Database** y dos objetos **Connection** de ODBCDirect y especificar las propiedades disponibles para cada objeto.</span><span class="sxs-lookup"><span data-stu-id="54225-122">This example demonstrates the **Connection** object and **Connections** collection by opening a **Database** object and two ODBCDirect **Connection** objects and listing the properties available to each object.</span></span>

```vb 
Sub ConnectionObjectX() 
 
   Dim wrkAcc as Workspace 
   Dim dbsNorthwind As Database 
   Dim wrkODBC As Workspace 
   Dim conPubs As Connection 
   Dim conPubs2 As Connection 
   Dim conLoop As Connection 
   Dim prpLoop As Property 
 
   ' Open a Database object. 
   Set wrkAcc = CreateWorkspace("NewWorkspace", _ 
      "admin", "", dbUseJet) 
   Set dbsNorthwind = wrkAcc.OpenDatabase("Northwind.mdb") 
 
   ' Create ODBCDirect Workspace object and open Connection 
   ' objects. 
   Set wrkODBC = CreateWorkspace("NewODBCWorkspace", _ 
      "admin", "", dbUseODBC) 
       
   ' Note: The DSNs referenced below must be configured to  
   '       use Microsoft Windows NT Authentication Mode to  
   '       authorize user access to the Microsoft SQL Server. 
   Set conPubs = wrkODBC.OpenConnection("Connection1", , , _ 
      "ODBC;DATABASE=pubs;DSN=Publishers") 
       
   Set conPubs2 = wrkODBC.OpenConnection("Connection2", , _ 
      True, "ODBC;DATABASE=pubs;DSN=Publishers") 
 
   Debug.Print "Database properties:" 
 
   With dbsNorthwind 
      ' Enumerate Properties collection of Database object. 
      For Each prpLoop In .Properties 
         On Error Resume Next 
         Debug.Print "  " & prpLoop.Name & " = " & _ 
            prpLoop.Value 
         On Error GoTo 0 
      Next prpLoop 
   End With 
 
   ' Enumerate the Connections collection. 
   For Each conLoop In wrkODBC.Connections 
      Debug.Print "Connection properties for " & _ 
         conLoop.Name & ":" 
 
      With conLoop 
         ' Print property values by explicitly calling each 
         ' Property object; the Connection object does not 
         ' support a Properties collection. 
         Debug.Print "  Connect = " & .Connect 
         ' Property actually returns a Database object. 
         Debug.Print "  Database[.Name] = " & _ 
            .Database.Name 
         Debug.Print "  Name = " & .Name 
         Debug.Print "  QueryTimeout = " & .QueryTimeout 
         Debug.Print "  RecordsAffected = " & _ 
            .RecordsAffected 
         Debug.Print "  StillExecuting = " & _ 
            .StillExecuting 
         Debug.Print "  Transactions = " & .Transactions 
         Debug.Print "  Updatable = " & .Updatable 
      End With 
 
   Next conLoop 
 
   dbsNorthwind.Close 
   conPubs.Close 
   conPubs2.Close 
   wrkAcc.Close 
   wrkODBC.Close 
 
End Sub 
 
```

<span data-ttu-id="54225-123">En este ejemplo se utiliza el método **OpenConnection** con distintos parámetros para abrir tres objetos **Connection** diferentes.</span><span class="sxs-lookup"><span data-stu-id="54225-123">This example uses the **OpenConnection** method with different parameters to open three different **Connection** objects.</span></span>

```vb 
Sub OpenConnectionX() 
 
   Dim wrkODBC As Workspace 
   Dim conPubs As Connection 
   Dim conPubs2 As Connection 
   Dim conPubs3 As Connection 
   Dim conLoop As Connection 
 
   ' Create ODBCDirect Workspace object. 
   Set wrkODBC = CreateWorkspace("NewODBCWorkspace", _ 
      "admin", "", dbUseODBC) 
 
   ' Open Connection object using supplied information in  
   ' the connect string. If this information were  
   ' insufficient, you could trap for an error rather than  
   ' go to an ODBC Driver Manager dialog box. 
   MsgBox "Opening Connection1..." 
       
    ' Note: The DSN referenced below must be set to  
    '       use Microsoft Windows NT Authentication Mode to  
    '       authorize user access to the Microsoft SQL Server. 
    Set conPubs = wrkODBC.OpenConnection("Connection1", _ 
       dbDriverNoPrompt, , _ 
       "ODBC;DATABASE=pubs;DSN=Publishers") 
 
   ' Open read-only Connection object based on information  
   ' you enter in the ODBC Driver Manager dialog box. 
   MsgBox "Opening Connection2..." 
   Set conPubs2 = wrkODBC.OpenConnection("Connection2", _ 
      dbDriverPrompt, True, "ODBC;DSN=Publishers;") 
 
   ' Open read-only Connection object by entering only the  
   ' missing information in the ODBC Driver Manager dialog  
   ' box. 
   MsgBox "Opening Connection3..." 
   Set conPubs3 = wrkODBC.OpenConnection("Connection3", _ 
      dbDriverCompleteRequired, True, _ 
      "ODBC;DATABASE=pubs;DSN=Publishers;") 
 
   ' Enumerate the Connections collection. 
   For Each conLoop In wrkODBC.Connections 
      Debug.Print "Connection properties for " & _ 
         conLoop.Name & ":" 
 
      With conLoop 
         ' Print property values by explicitly calling each 
         ' Property object; the Connection object does not 
         ' support a Properties collection. 
         Debug.Print "  Connect = " & .Connect 
         ' Property actually returns a Database object. 
         Debug.Print "  Database[.Name] = " & _ 
            .Database.Name 
         Debug.Print "  Name = " & .Name 
         Debug.Print "  QueryTimeout = " & .QueryTimeout 
         Debug.Print "  RecordsAffected = " & _ 
            .RecordsAffected 
         Debug.Print "  StillExecuting = " & _ 
            .StillExecuting 
         Debug.Print "  Transactions = " & .Transactions 
         Debug.Print "  Updatable = " & .Updatable 
      End With 
 
   Next conLoop 
 
   conPubs.Close 
   conPubs2.Close 
   conPubs3.Close 
   wrkODBC.Close 
 
End Sub 
 
```
