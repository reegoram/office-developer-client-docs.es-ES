---
title: Field.SourceTable Property (DAO)
TOCTitle: SourceTable Property
ms:assetid: 9564ea1c-eafd-0b72-fd68-d88fcc3ea189
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197694(v=office.15)
ms:contentKeyID: 48546429
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052900
f1_categories:
- Office.Version=v15
ms.openlocfilehash: b29437a459d29e5238e8bd915901339d87005612
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25486571"
---
# <a name="fieldsourcetable-property-dao"></a><span data-ttu-id="f62c0-102">Field.SourceTable Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="f62c0-102">Field.SourceTable Property (DAO)</span></span>


<span data-ttu-id="f62c0-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="f62c0-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="f62c0-p101">Devuelve un valor que indica el nombre de la tabla que es la fuente original de los datos para un objeto **Field**. **String** de sólo lectura.</span><span class="sxs-lookup"><span data-stu-id="f62c0-p101">Returns a value that indicates the name of the table that is the original source of the data for a **Field** object. Read-only **String**.</span></span>

## <a name="syntax"></a><span data-ttu-id="f62c0-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f62c0-106">Syntax</span></span>

<span data-ttu-id="f62c0-107">*expresión* . SourceTable</span><span class="sxs-lookup"><span data-stu-id="f62c0-107">*expression* .SourceTable</span></span>

<span data-ttu-id="f62c0-108">*expresión* Variable que representa un objeto **Field** .</span><span class="sxs-lookup"><span data-stu-id="f62c0-108">*expression* A variable that represents a **Field** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="f62c0-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f62c0-109">Remarks</span></span>

<span data-ttu-id="f62c0-110">Para un objeto **Field**, utilice las propiedades **SourceField** y **SourceTable** dependiendo del objeto que contenga la colección **Fields** al que el objeto **Field** está anexado, como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="f62c0-110">For a **Field** object, use of the **SourceField** and **SourceTable** properties depends on the object that contains the **Fields** collection that the **Field** object is appended to, as shown in the following table.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f62c0-111">Objeto anexado a</span><span class="sxs-lookup"><span data-stu-id="f62c0-111">Object appended to</span></span></p></th>
<th><p><span data-ttu-id="f62c0-112">Uso</span><span class="sxs-lookup"><span data-stu-id="f62c0-112">Usage</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f62c0-113"><strong>Index</strong></span><span class="sxs-lookup"><span data-stu-id="f62c0-113"><strong>Index</strong></span></span></p></td>
<td><p><span data-ttu-id="f62c0-114">No admitido</span><span class="sxs-lookup"><span data-stu-id="f62c0-114">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f62c0-115"><strong>Objeto QueryDef</strong></span><span class="sxs-lookup"><span data-stu-id="f62c0-115"><strong>QueryDef</strong></span></span></p></td>
<td><p><span data-ttu-id="f62c0-116">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="f62c0-116">Read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f62c0-117"><strong>Recordset</strong></span><span class="sxs-lookup"><span data-stu-id="f62c0-117"><strong>Recordset</strong></span></span></p></td>
<td><p><span data-ttu-id="f62c0-118">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="f62c0-118">Read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f62c0-119"><strong>Relación</strong></span><span class="sxs-lookup"><span data-stu-id="f62c0-119"><strong>Relation</strong></span></span></p></td>
<td><p><span data-ttu-id="f62c0-120">No admitido</span><span class="sxs-lookup"><span data-stu-id="f62c0-120">Not supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f62c0-121"><strong>TableDef</strong></span><span class="sxs-lookup"><span data-stu-id="f62c0-121"><strong>TableDef</strong></span></span></p></td>
<td><p><span data-ttu-id="f62c0-122">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="f62c0-122">Read-only</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f62c0-p102">Estas propiedades indican que el campo original y los nombres de tabla están asociados con un objeto **Field**. Por ejemplo, podría utilizar estas propiedades para determinar el origen inicial de los datos en un campo de consulta cuyo nombre no está relacionado con el nombre del campo de una tabla base.</span><span class="sxs-lookup"><span data-stu-id="f62c0-p102">These properties indicate the original field and table names associated with a **Field** object. For example, you could use these properties to determine the original source of the data in a query field whose name is unrelated to the name of the field in the underlying table.</span></span>


> [!NOTE]
> <P><span data-ttu-id="f62c0-125">[!NOTA] La propiedad <STRONG>SourceTable</STRONG> no devolverá un nombre de tabla significativo si se usa en un objeto <STRONG>Field</STRONG> de la colección <STRONG>Fields</STRONG> de un objeto <STRONG>Recordset</STRONG> de tipo tabla.</span><span class="sxs-lookup"><span data-stu-id="f62c0-125">The <STRONG>SourceTable</STRONG> property will not return a meaningful table name if used on a <STRONG>Field</STRONG> object in the <STRONG>Fields</STRONG> collection of a table-type <STRONG>Recordset</STRONG> object.</span></span></P>

