---
title: Document Members (DAO)
TOCTitle: Document Members
ms:assetid: 8de770e6-e4d1-372a-3ef8-8539c921b41f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197365(v=office.15)
ms:contentKeyID: 48546270
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: acbae7603615af8d0171715799963ad4d54e6342
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485886"
---
# <a name="document-members-dao"></a><span data-ttu-id="dd99e-102">Document Members (DAO)</span><span class="sxs-lookup"><span data-stu-id="dd99e-102">Document Members (DAO)</span></span>


<span data-ttu-id="dd99e-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="dd99e-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="dd99e-p101">Un objeto Document incluye información sobre una instancia de un objeto. El objeto puede ser una base de datos, una tabla guardada, una consulta o una relación (sólo bases de datos del motor de base de datos de Microsoft Access).</span><span class="sxs-lookup"><span data-stu-id="dd99e-p101">A Document object includes information about one instance of an object. The object can be a database, saved table, query, or relationship (Microsoft Access database engine databases only).</span></span>

## <a name="methods"></a><span data-ttu-id="dd99e-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="dd99e-106">Methods</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="dd99e-107">Nombre</span><span class="sxs-lookup"><span data-stu-id="dd99e-107">Name</span></span></p></th>
<th><p><span data-ttu-id="dd99e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="dd99e-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dd99e-109"><strong><a href="document-createproperty-method-dao.md">CreateProperty</a></strong></span><span class="sxs-lookup"><span data-stu-id="dd99e-109"><strong><a href="document-createproperty-method-dao.md">CreateProperty</a></strong></span></span></p></td>
<td><p><span data-ttu-id="dd99e-110">Crea un nuevo objeto <strong><a href="property-object-dao.md">Property</a></strong> definido por el usuario (sólo áreas de trabajo de Microsoft Access).</span><span class="sxs-lookup"><span data-stu-id="dd99e-110">Creates a new user-defined <strong><a href="property-object-dao.md">Property</a></strong> object (Microsoft Access workspaces only).</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="properties"></a><span data-ttu-id="dd99e-111">Propiedades</span><span class="sxs-lookup"><span data-stu-id="dd99e-111">Properties</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="dd99e-112">Nombre</span><span class="sxs-lookup"><span data-stu-id="dd99e-112">Name</span></span></p></th>
<th><p><span data-ttu-id="dd99e-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="dd99e-113">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dd99e-114"><strong><a href="document-container-property-dao.md">Container</a></strong></span><span class="sxs-lookup"><span data-stu-id="dd99e-114"><strong><a href="document-container-property-dao.md">Container</a></strong></span></span></p></td>
<td><p><span data-ttu-id="dd99e-p102">Devuelve el nombre del objeto <strong><a href="container-object-dao.md">Container</a></strong> al que pertenece un objeto <strong>Document</strong> (solo en áreas de trabajo de Microsoft Access).</span><span class="sxs-lookup"><span data-stu-id="dd99e-p102">Returns the name of the <strong><a href="container-object-dao.md">Container</a></strong> object to which a <strong>Document</strong> object belongs (Microsoft Access workspaces only). .</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd99e-117"><strong><a href="document-datecreated-property-dao.md">DateCreated</a></strong></span><span class="sxs-lookup"><span data-stu-id="dd99e-117"><strong><a href="document-datecreated-property-dao.md">DateCreated</a></strong></span></span></p></td>
<td><p><span data-ttu-id="dd99e-p103">Devuelve la fecha y la hora en que se creó un objeto. <strong>Variant</strong> de sólo lectura.</span><span class="sxs-lookup"><span data-stu-id="dd99e-p103">Returns the date and time that an object was created. Read-only <strong>Variant</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd99e-120"><strong><a href="document-lastupdated-property-dao.md">LastUpdated</a></strong></span><span class="sxs-lookup"><span data-stu-id="dd99e-120"><strong><a href="document-lastupdated-property-dao.md">LastUpdated</a></strong></span></span></p></td>
<td><p><span data-ttu-id="dd99e-p104">Devuelve la fecha y la hora del último cambio efectuado en un objeto. <strong>Variant</strong> de sólo lectura.</span><span class="sxs-lookup"><span data-stu-id="dd99e-p104">Returns the date and time of the most recent change made to an object. Read-only <strong>Variant</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd99e-123"><strong><a href="document-name-property-dao.md">Name</a></strong></span><span class="sxs-lookup"><span data-stu-id="dd99e-123"><strong><a href="document-name-property-dao.md">Name</a></strong></span></span></p></td>
<td><p><span data-ttu-id="dd99e-p105">Devuelve el nombre del objeto especificado. <strong>String</strong> de sólo lectura.</span><span class="sxs-lookup"><span data-stu-id="dd99e-p105">Returns the name of the specified object. Read-only <strong>String</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd99e-126"><strong><a href="document-properties-property-dao.md">Propiedades</a></strong></span><span class="sxs-lookup"><span data-stu-id="dd99e-126"><strong><a href="document-properties-property-dao.md">Properties</a></strong></span></span></p></td>
<td><p><span data-ttu-id="dd99e-p106">Devuelve la colección <strong><a href="properties-collection-dao.md">Properties</a></strong> de un objeto especificado. solo lectura.</span><span class="sxs-lookup"><span data-stu-id="dd99e-p106">Returns the <strong><a href="properties-collection-dao.md">Properties</a></strong> collection of the specified object. Read-only.</span></span></p></td>
</tr>
</tbody>
</table>
