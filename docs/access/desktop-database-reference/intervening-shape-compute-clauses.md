---
title: Intervenir en cláusulas COMPUTE de Shape
TOCTitle: Intervening Shape COMPUTE Clauses
ms:assetid: 3e9dcef2-776c-0365-4a92-68e325f7dbb5
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249174(v=office.15)
ms:contentKeyID: 48544380
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e606af30db011a8a2aea4a8799ff312788ece7c5
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25486103"
---
# <a name="intervening-shape-compute-clauses"></a><span data-ttu-id="3db7f-102">Intervenir en cláusulas COMPUTE de Shape</span><span class="sxs-lookup"><span data-stu-id="3db7f-102">Intervening Shape COMPUTE Clauses</span></span>


<span data-ttu-id="3db7f-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="3db7f-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="3db7f-104">Es posible incrustar cláusulas COMPUTE entre el elemento principal y el secundario de un comando Shape parametrizado, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3db7f-104">It is valid to embed one or more COMPUTE clauses between the parent and child in a parameterized shape command, as in the following example:</span></span>

```vb 
 
SHAPE {select au_lname, state from authors} APPEND 
 ((SHAPE 
 (SHAPE 
 {select * from authors where state = ?} rs 
 COMPUTE rs, ANY(rs.state) state, ANY(rs.au_lname) au_lname 
 BY au_id) rs2 
 COMPUTE rs2, ANY(rs2.state) BY au_lname) 
RELATE state TO PARAMETER 0) 
```
