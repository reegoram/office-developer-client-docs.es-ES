---
title: Database.ReplicaID Property (DAO)
TOCTitle: ReplicaID Property
ms:assetid: cf2ca8a1-d13f-30e0-2ca1-dd32ac736c56
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834672(v=office.15)
ms:contentKeyID: 48547805
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053375
f1_categories:
- Office.Version=v15
ms.openlocfilehash: ca879a3c56d23a67987d86b7fbc21421cd8db843
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25483357"
---
# <a name="databasereplicaid-property-dao"></a>Database.ReplicaID Property (DAO)


**Se aplica a**: Access 2013 | Office 2013


Devuelve un valor de 16 bytes que identifica de forma exclusiva una réplica de base de datos (sólo para áreas de trabajo de Microsoft Access).

## <a name="syntax"></a>Sintaxis

*expresión* . ReplicaID

*expresión* Variable que representa un objeto de **base de datos** .

## <a name="remarks"></a>Observaciones

El valor devuelto es un valor **GUID** que identifica de forma exclusiva la réplica o el Diseño principal.

El motor de base de datos Microsoft Access genera de forma automática este valor cuando se crea una nueva réplica.

La propiedad **ReplicaID** de cada réplica, y del Diseño principal, se almacena en la tabla de sistema MSysReplicas.

## <a name="example"></a>Ejemplo

En este ejemplo se crea un réplica desde el Diseño principal de Neptuno.mdb y después se devuelve la **ReplicaID** de la réplica, que crea automáticamente el motor de base de datos Microsoft Access. (Si todavía no ha creado un Diseño principal de Neptuno, vea la propiedad **Replicable** o cambie el nombre de la base de datos en el código de un Diseño principal existente).

```vb 
Sub MakeReplicaReplicaIDX() 
 
 Dim dbsNorthwind As Database 
 Dim prpReplicaID As Property 
 Dim dbsReplica As Database 
 
 Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
 
 ' Makes a new replica. 
 dbsNorthwind.MakeReplica "Nwreplica2.mdb", _ 
 "second replica" 
 dbsNorthwind.Close 
 
 ' Opens the new replica to read its ReplicaID. 
 Set dbsReplica = OpenDatabase("Nwreplica2.mdb") 
 
 Debug.Print dbsReplica.ReplicaID 
 dbsReplica.Close 
 
End Sub 
 
```

