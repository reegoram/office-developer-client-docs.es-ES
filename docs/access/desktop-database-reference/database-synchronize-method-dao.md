---
title: Database.Synchronize Method (DAO)
TOCTitle: Synchronize Method
ms:assetid: 5e716a4a-2430-8106-5c34-a02dd28bc4f6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194659(v=office.15)
ms:contentKeyID: 48545137
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053357
f1_categories:
- Office.Version=v15
ms.openlocfilehash: c55eab611cae8431a3ff3f2220cdfa8b1923d891
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485018"
---
# <a name="databasesynchronize-method-dao"></a><span data-ttu-id="cf8ac-102">Database.Synchronize Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="cf8ac-102">Database.Synchronize Method (DAO)</span></span>


<span data-ttu-id="cf8ac-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="cf8ac-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="cf8ac-p101">Sincroniza dos réplicas (sólo áreas de trabajo de Microsoft Access).</span><span class="sxs-lookup"><span data-stu-id="cf8ac-p101">Synchronizes two replicas. (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="cf8ac-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf8ac-106">Syntax</span></span>

<span data-ttu-id="cf8ac-107">*expresión* . Sincronizar (***DbPathName***, ***ExchangeType***)</span><span class="sxs-lookup"><span data-stu-id="cf8ac-107">*expression* .Synchronize(***DbPathName***, ***ExchangeType***)</span></span>

<span data-ttu-id="cf8ac-108">*expresión* Variable que representa un objeto de **base de datos** .</span><span class="sxs-lookup"><span data-stu-id="cf8ac-108">*expression* A variable that represents a **Database** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="cf8ac-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cf8ac-109">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="cf8ac-110">Nombre</span><span class="sxs-lookup"><span data-stu-id="cf8ac-110">Name</span></span></p></th>
<th><p><span data-ttu-id="cf8ac-111">Necesario/Opcional</span><span class="sxs-lookup"><span data-stu-id="cf8ac-111">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="cf8ac-112">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="cf8ac-112">Data Type</span></span></p></th>
<th><p><span data-ttu-id="cf8ac-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="cf8ac-113">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf8ac-114">DbPathName</span><span class="sxs-lookup"><span data-stu-id="cf8ac-114">DbPathName</span></span></p></td>
<td><p><span data-ttu-id="cf8ac-115">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="cf8ac-115">Required</span></span></p></td>
<td><p><span data-ttu-id="cf8ac-116"><strong>String</strong></span><span class="sxs-lookup"><span data-stu-id="cf8ac-116"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="cf8ac-117">Ruta de acceso a la réplica de destino con la que la base de datos estará sincronizada.</span><span class="sxs-lookup"><span data-stu-id="cf8ac-117">The path to the target replica with which database will be synchronized.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf8ac-118">ExchangeType</span><span class="sxs-lookup"><span data-stu-id="cf8ac-118">ExchangeType</span></span></p></td>
<td><p><span data-ttu-id="cf8ac-119">Opcional</span><span class="sxs-lookup"><span data-stu-id="cf8ac-119">Optional</span></span></p></td>
<td><p><span data-ttu-id="cf8ac-120"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="cf8ac-120"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="cf8ac-121">Constante <strong><a href="synchronizetypeenum-enumeration-dao.md">SynchronizeTypeEnum</a></strong> que indica la dirección para sincronizar los cambios entre las dos bases de datos.</span><span class="sxs-lookup"><span data-stu-id="cf8ac-121">A <strong><a href="synchronizetypeenum-enumeration-dao.md">SynchronizeTypeEnum</a></strong> constant indicating which direction to synchronize changes between the two databases.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="cf8ac-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cf8ac-122">Remarks</span></span>

<span data-ttu-id="cf8ac-123">Utilice **Synchronize** para intercambiar datos y cambios de diseño entre dos bases de datos.</span><span class="sxs-lookup"><span data-stu-id="cf8ac-123">You use **Synchronize** to exchange data and design changes between two databases.</span></span> <span data-ttu-id="cf8ac-124">Los cambios de diseño siempre se ejecutan primero.</span><span class="sxs-lookup"><span data-stu-id="cf8ac-124">Design changes always happen first.</span></span> <span data-ttu-id="cf8ac-125">Ambas bases de datos deben estar en el mismo nivel de diseño antes de que puedan intercambiar datos.</span><span class="sxs-lookup"><span data-stu-id="cf8ac-125">Both databases must be at the same design level before they can exchange data.</span></span> <span data-ttu-id="cf8ac-126">Por ejemplo, un intercambio de tipo **dbRepExportChanges** puede provocar cambios de diseño en una réplica incluso aunque los cambios de datos flujo sólo desde la base de datos a DbPathName.</span><span class="sxs-lookup"><span data-stu-id="cf8ac-126">For example, an exchange of type **dbRepExportChanges** might cause design changes at a replica even though data changes flow only from the database to DbPathName.</span></span>

<span data-ttu-id="cf8ac-127">La réplica identificada en DbPathName debe formar parte del mismo conjunto de réplicas.</span><span class="sxs-lookup"><span data-stu-id="cf8ac-127">The replica identified in DbPathName must be part of the same replica set.</span></span> <span data-ttu-id="cf8ac-128">Si ambas réplicas tienen el mismo valor de la propiedad **ReplicaID** o son Diseños principales para dos conjuntos de réplicas distintos, la sincronización produce un error.</span><span class="sxs-lookup"><span data-stu-id="cf8ac-128">If both replicas have the same **ReplicaID** property setting or are Design Masters for two different replica sets, the synchronization fails.</span></span>

<span data-ttu-id="cf8ac-129">Al sincronizar dos réplicas a través de Internet, debe utilizar la constante **dbRepSyncInternet**.</span><span class="sxs-lookup"><span data-stu-id="cf8ac-129">When you synchronize two replicas over the Internet, you must use the **dbRepSyncInternet** constant.</span></span> <span data-ttu-id="cf8ac-130">En este caso, especifique una dirección de localizador de recursos uniforme (URL) para el argumento DbPathName en lugar de especificar una ruta de acceso de red de área local.</span><span class="sxs-lookup"><span data-stu-id="cf8ac-130">In this case, you specify a Uniform Resource Locator (URL) address for the DbPathName argument instead of specifying a local area network path.</span></span>


> [!NOTE]
> <P><span data-ttu-id="cf8ac-p105">[!NOTA] No puede sincronizar réplicas parciales con otras réplicas parciales. Vea el método <STRONG><A href="database-populatepartial-method-dao.md">PopulatePartial</A></STRONG> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="cf8ac-p105">You can't synchronize partial replicas with other partial replicas. See the <STRONG><A href="database-populatepartial-method-dao.md">PopulatePartial</A></STRONG> method for more information.</span></span></P>

