---
title: Ejemplo de método Create (VB)
TOCTitle: Create Method Example (VB)
ms:assetid: 3e6a4f3d-3b25-2dfb-5ef3-6a4c5326b78f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249171(v=office.15)
ms:contentKeyID: 48544372
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: df55297ecc4ebd6875b4b28cc7bc45038789d83c
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485873"
---
# <a name="create-method-example-vb"></a><span data-ttu-id="c4ec4-102">Ejemplo de método Create (VB)</span><span class="sxs-lookup"><span data-stu-id="c4ec4-102">Create Method Example (VB)</span></span>


<span data-ttu-id="c4ec4-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="c4ec4-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="c4ec4-104">El código siguiente muestra cómo crear una nueva base de datos de Microsoft Jet con el método [Create](create-method-adox.md).</span><span class="sxs-lookup"><span data-stu-id="c4ec4-104">The following code shows how to create a new Microsoft Jet database with the [Create](create-method-adox.md) method.</span></span>

```vb 
 
' BeginCreateDatabseVB 
Sub CreateDatabase() 
 On Error GoTo CreateDatabaseError 
 
 Dim cat As New ADOX.Catalog 
 cat.Create "Provider='Microsoft.Jet.OLEDB.4.0';Data Source='c:\new.mdb'" 
 
 'Clean up 
 Set cat = Nothing 
 Exit Sub 
 
CreateDatabaseError: 
 Set cat = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
' EndCreateDatabaseVB 
```
