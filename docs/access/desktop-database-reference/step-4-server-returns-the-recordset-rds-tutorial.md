---
title: 'Paso 4: El servidor devuelve el objeto Recordset (Tutorial de RDS)'
TOCTitle: 'Step 4: Server Returns the Recordset (RDS Tutorial)'
ms:assetid: 4503151d-de8b-98d1-1aa8-11f1b6e6b55c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249209(v=office.15)
ms:contentKeyID: 48544542
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 41fd4a1aabda0887d265e3aa0ec9201b1abbbde7
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25486446"
---
# <a name="step-4-server-returns-the-recordset-rds-tutorial"></a><span data-ttu-id="4a95e-102">Paso 4: El servidor devuelve el objeto Recordset (Tutorial de RDS)</span><span class="sxs-lookup"><span data-stu-id="4a95e-102">Step 4: Server Returns the Recordset (RDS Tutorial)</span></span>


<span data-ttu-id="4a95e-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="4a95e-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="4a95e-p101">RDS convierte el objeto **Recordset** recuperado en un formulario que se puede devolver al cliente (es decir, *reorganiza* el objeto **Recordset**). La forma exacta de la conversión y de cómo se envía depende de si el servidor está en Internet o en una intranet, en una red de área local, o de si se trata de una biblioteca de vínculos dinámicos (dll). No obstante, este detalle no es crítico: lo que importa es que RDS devuelva el objeto **Recordset** al cliente.</span><span class="sxs-lookup"><span data-stu-id="4a95e-p101">RDS converts the retrieved **Recordset** object to a form that can be sent back to the client (that is, it *marshals* the **Recordset**). The exact form of the conversion and how it is sent depends on whether the server is on the Internet or an intranet, a local area network, or is a dynamic-link library. However, this detail is not critical; all that matters is that RDS sends the **Recordset** back to the client.</span></span>

<span data-ttu-id="4a95e-107">En el cliente, se recibe un objeto **Recordset** y se asigna a una variable local.</span><span class="sxs-lookup"><span data-stu-id="4a95e-107">On the client side, a **Recordset** object is returned and assigned to a local variable.</span></span>

```vb 
 
Sub RDSTutorial4() 
 Dim DS as New RDS.DataSpace 
 Dim RS as ADODB.Recordset 
 Dim DF as Object 
 Set DF = DS.CreateObject("RDSServer.DataFactory", "https://yourServer") 
 Set RS = DF.Query("DSN=Pubs", "SELECT * FROM Authors") 
... 
```
