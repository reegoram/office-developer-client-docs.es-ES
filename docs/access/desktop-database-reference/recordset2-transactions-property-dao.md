---
title: Recordset2.Transactions Property (DAO)
TOCTitle: Transactions Property
ms:assetid: f2169565-f782-4089-0e4b-bc5d58d37db5
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836614(v=office.15)
ms:contentKeyID: 48548642
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 936fff4988b086c4029fa4d933af3a9b9c299157
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25486283"
---
# <a name="recordset2transactions-property-dao"></a>Recordset2.Transactions Property (DAO)


**Se aplica a**: Access 2013 | Office 2013

Devuelve un valor que indica si un objeto admite transacciones. **Boolean** de solo lectura.

## <a name="syntax"></a>Sintaxis

*expresión* . Transacciones

*expresión* Variable que representa un objeto **Recordset2** .

## <a name="remarks"></a>Observaciones

En un área de trabajo de Microsoft Access, también puede usar la propiedad **Transactions** con objetos **Recordset** de tipo Dynaset o de tabla. Objetos **[Recordset](recordset-object-dao.md)** de tipo Snapshot y forward – only siempre devuelven **False**.

Si un objeto **Recordset** de tipo Dynaset o Table se basa en una tabla de motor de base de datos de Microsoft Access, la propiedad **Transactions** será **True** y se pueden usar las transacciones. Puede ser que otros motores de bases de datos no admitan transacciones. Por ejemplo, no se pueden usar transacciones en un objeto **Recordset** de tipo Dynaset basado en una tabla de Paradox.

Compruebe la propiedad **Transactions** antes de usar el método **[BeginTrans](dbengine-begintrans-method-dao.md)** en el objeto [**Workspace**](workspace-object-dao.md) del objeto **Recordset** para asegurarse de que se admiten transacciones. El uso de los métodos **BeginTrans**, **CommitTrans** o **Rollback** no tiene ningún efecto en un objeto no admitido.

## <a name="example"></a>Ejemplo

En este ejemplo se muestra la propiedad **Transactions** en áreas de trabajo de Microsoft Access.

```vb 
Sub TransactionsX() 
 
 Dim wrkAcc As Workspace 
 Dim dbsNorthwind As Database 
 Dim conPubs As Connection 
 Dim rstTemp As Recordset 
 
 Set wrkAcc = CreateWorkspace("", "admin", "", dbUseJet) 
 Set dbsNorthwind = wrkAcc.OpenDatabase("Northwind.mdb") 
 
 ' Open two different Recordset objects and display the 
 ' Transactions property of each. 
 
 Debug.Print "Opening Microsoft Access table-type " & _ 
 "recordset..." 
 Set rstTemp = dbsNorthwind.OpenRecordset( _ 
 "Employees", dbOpenTable) 
 Debug.Print " Transactions = " & rstTemp.Transactions 
 
 Debug.Print "Opening forward-only-type " & _ 
 "recordset where the source is an SQL statement..." 
 Set rstTemp = dbsNorthwind.OpenRecordset( _ 
 "SELECT * FROM Employees", dbOpenForwardOnly) 
 Debug.Print " Transactions = " & rstTemp.Transactions 
 
 rstTemp.Close 
 dbsNorthwind.Close 
 conPubs.Close 
 wrkAcc.Close 
End Sub 
 
```

