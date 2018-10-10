---
title: Database.PopulatePartial Method (DAO)
TOCTitle: PopulatePartial Method
ms:assetid: fa3227a2-c961-6a98-32b3-5b6e5329a21d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837034(v=office.15)
ms:contentKeyID: 48548834
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1101186
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 11c999fcac3b77ddc4eeb9ef8f4414a5f8aa1559
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25484258"
---
# <a name="databasepopulatepartial-method-dao"></a><span data-ttu-id="74333-102">Database.PopulatePartial Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="74333-102">Database.PopulatePartial Method (DAO)</span></span>


<span data-ttu-id="74333-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="74333-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="74333-p101">Sincroniza cualquier cambio en una réplica parcial con la réplica completa, desactiva todos los registros en la réplica parcial y, a continuación, vuelve a llenar la réplica parcial en función de los filtros de la réplica activa. (Solo bases de datos del motor de base de datos de Microsoft Access).</span><span class="sxs-lookup"><span data-stu-id="74333-p101">Synchronizes any changes in a partial replica with the full replica, clears all records in the partial replica, and then repopulates the partial replica based on the current replica filters. (Microsoft Access database engine databases only.).</span></span>

## <a name="syntax"></a><span data-ttu-id="74333-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74333-106">Syntax</span></span>

<span data-ttu-id="74333-107">*expresión* . PopulatePartial (***DbPathName***)</span><span class="sxs-lookup"><span data-stu-id="74333-107">*expression* .PopulatePartial(***DbPathName***)</span></span>

<span data-ttu-id="74333-108">*expresión* Variable que representa un objeto de **base de datos** .</span><span class="sxs-lookup"><span data-stu-id="74333-108">*expression* A variable that represents a **Database** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="74333-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="74333-109">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="74333-110">Nombre</span><span class="sxs-lookup"><span data-stu-id="74333-110">Name</span></span></p></th>
<th><p><span data-ttu-id="74333-111">Necesario/Opcional</span><span class="sxs-lookup"><span data-stu-id="74333-111">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="74333-112">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="74333-112">Data Type</span></span></p></th>
<th><p><span data-ttu-id="74333-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="74333-113">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74333-114">DbPathName</span><span class="sxs-lookup"><span data-stu-id="74333-114">DbPathName</span></span></p></td>
<td><p><span data-ttu-id="74333-115">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="74333-115">Required</span></span></p></td>
<td><p><span data-ttu-id="74333-116"><strong>String</strong></span><span class="sxs-lookup"><span data-stu-id="74333-116"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="74333-117">Ruta y nombre de la réplica completa a partir de la cual se llenan los registros.</span><span class="sxs-lookup"><span data-stu-id="74333-117">The path and name of the full replica from which to populate records.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="74333-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="74333-118">Remarks</span></span>

<span data-ttu-id="74333-119">Al sincronizar una réplica parcial con una réplica completa, es posible crear registros "huérfanos" en la réplica parcial.</span><span class="sxs-lookup"><span data-stu-id="74333-119">When you synchronize a partial replica with a full replica, it is possible to create "orphaned" records in the partial replica.</span></span> <span data-ttu-id="74333-120">Por ejemplo, suponga que tiene una tabla de clientes con **[ReplicaFilter](tabledef-replicafilter-property-dao.md)** establecido en "región = 'CA'".</span><span class="sxs-lookup"><span data-stu-id="74333-120">For example, suppose you have a Customers table with its **[ReplicaFilter](tabledef-replicafilter-property-dao.md)** set to "Region = 'CA'".</span></span> <span data-ttu-id="74333-121">Si un usuario cambia una región de cliente de CA a NY en la réplica parcial y luego se produce una sincronización a través del método **[Synchronize](database-synchronize-method-dao.md)**, el cambio se propaga a la réplica completa pero el registro que contiene NY en la réplica parcial está huérfano porque ya no cumple los criterios de filtro de la réplica.</span><span class="sxs-lookup"><span data-stu-id="74333-121">If a user changes a customer's region from CA to NY in the partial replica, and then a synchronization occurs via the **[Synchronize](database-synchronize-method-dao.md)** method, the change is propagated to the full replica but the record containing NY in the partial replica is orphaned because it now doesn't meet the replica filter criteria.</span></span>

<span data-ttu-id="74333-p103">Para resolver el problema de los registros huérfanos, puede utilizar el método **PopulatePartial**. El método **PopulatePartial** es similar al método **Synchronize** pero sincroniza cualquier cambio con la réplica completa, elimina todos los registros en la réplica parcial y luego rellena dicha réplica basándose en los filtros de la réplica activa. Incluso si los filtros de la réplica no han cambiado, **PopulatePartial** borrará siempre todos los registros de la réplica parcial y la rellenará basándose en los filtros activos.</span><span class="sxs-lookup"><span data-stu-id="74333-p103">To solve the problem of orphaned records, you can use the **PopulatePartial** method. The **PopulatePartial** method is similar to the **Synchronize** method, but it synchronizes any changes with the full replica, removes all records in the partial replica, and then repopulates the partial replica based on the current replica filters. Even if your replica filters have not changed, **PopulatePartial** will always clear all records in the partial replica and repopulate it based on the current filters.</span></span>

<span data-ttu-id="74333-p104">En general, debe utilizar el método **PopulatePartial** cuando crea una réplica parcial y siempre que cambie los filtros de la réplica. Si la aplicación cambia los filtros de la réplica, debe seguir estos pasos:</span><span class="sxs-lookup"><span data-stu-id="74333-p104">Generally, you should use the **PopulatePartial** method when you create a partial replica and whenever you change your replica filters. If your application changes replica filters, you should follow these steps:</span></span>

1.  <span data-ttu-id="74333-127">Sincronice la réplica completa con la réplica parcial en la que se están cambiando los filtros.</span><span class="sxs-lookup"><span data-stu-id="74333-127">Synchronize your full replica with the partial replica in which the filters are being changed.</span></span>

2.  <span data-ttu-id="74333-128">Utilice las propiedades **ReplicaFilter** y **[PartialReplica](relation-partialreplica-property-dao.md)** para hacer los cambios que desee en el filtro de réplica.</span><span class="sxs-lookup"><span data-stu-id="74333-128">Use the **ReplicaFilter** and **[PartialReplica](relation-partialreplica-property-dao.md)** properties to make the desired changes to the replica filter.</span></span>

3.  <span data-ttu-id="74333-129">Llame al método **PopulatePartial** para eliminar todos los registros de la réplica parcial y transferir los registros desde la réplica completa que cumplen los criterios del nuevo filtro de réplica.</span><span class="sxs-lookup"><span data-stu-id="74333-129">Call the **PopulatePartial** method to remove all records from the partial replica and transfer all records from the full replica that meet the new replica filter criteria.</span></span>

<span data-ttu-id="74333-130">Si se cambia un filtro de réplica y se abre el método **Synchronize** sin abrir primero **PopulatePartial**, se produce un error capturable.</span><span class="sxs-lookup"><span data-stu-id="74333-130">If a replica filter has changed, and the **Synchronize** method is invoked without first invoking **PopulatePartial**, a trappable error occurs.</span></span>

<span data-ttu-id="74333-p105">El método **PopulatePartial** sólo se puede abrir en una réplica parcial que se haya abierto para un acceso exclusivo. Además, no puede llamar al método **PopulatePartial** desde un código que se ejecuta en la misma réplica parcial. En su lugar, abra la réplica parcial de forma exclusiva desde la réplica completa u otra base de datos y llame luego a **PopulatePartial**.</span><span class="sxs-lookup"><span data-stu-id="74333-p105">The **PopulatePartial** method can only be invoked on a partial replica that has been opened for exclusive access. Furthermore, you can't call the **PopulatePartial** method from code running within the partial replica itself. Instead, open the partial replica exclusively from the full replica or another database, then call **PopulatePartial**.</span></span>


> [!NOTE]
> <P><span data-ttu-id="74333-p106">[!NOTA] Aunque <STRONG>PopulatePartial</STRONG> realiza una sincronización de sentido único antes de borrar y rellenar la réplica parcial, resulta recomendable llamar a <STRONG>Synchronize</STRONG> antes de a <STRONG>PopulatePartial</STRONG>. Esto se debe a que si ocurre un error en la llamada a <STRONG>Synchronize</STRONG>, se produce un error capturable. Puede utilizar este error para decidir si prosigue o no con el método <STRONG>PopulatePartial</STRONG> (que elimina todos los registros de la réplica parcial). Si <STRONG>PopulatePartial</STRONG> se llama a sí mismo y se produce un error mientras se sincronizan los registros, se borrarán los registros de la réplica parcial, lo que quizá no sea el resultado esperado.</span><span class="sxs-lookup"><span data-stu-id="74333-p106">Although <STRONG>PopulatePartial</STRONG> performs a one-way synchronization before clearing and repopulating the partial replica, it is still a good idea to call <STRONG>Synchronize</STRONG> before calling <STRONG>PopulatePartial</STRONG>. This is because if the call to <STRONG>Synchronize</STRONG> fails, a trappable error occurs. You can use this error to decide whether or not to proceed with the <STRONG>PopulatePartial</STRONG> method (which removes all records in the partial replica). If <STRONG>PopulatePartial</STRONG> is called by itself and an error occurs while records are being synchronized, records in the partial replica will still be cleared, which may not be the desired result.</span></span></P>



## <a name="example"></a><span data-ttu-id="74333-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="74333-138">Example</span></span>

<span data-ttu-id="74333-139">En el ejemplo siguiente se utiliza el método **PopulatePartial** después de cambiar un filtro de réplica.</span><span class="sxs-lookup"><span data-stu-id="74333-139">The following example uses the **PopulatePartial** method after changing a replica filter.</span></span>

```vb 
Sub PopulatePartialX() 
 
 Dim tdfCustomers As TableDef 
 Dim strFilter As String 
 Dim dbsTemp As Database 
 
 ' Open the partial replica in exclusive mode. 
 Set dbsTemp = OpenDatabase("F:\SALES\FY96CA.MDB", True) 
 
 With dbsTemp 
 Set tdfCustomers = .TableDefs("Customers") 
 
 ' Synchronize with full replica 
 ' before setting replica filter. 
 .Synchronize "C:\SALES\FY96.MDB" 
 
 strFilter = "Region = 'CA'" 
 tdfCustomers.ReplicaFilter = strFilter 
 
 ' Populate records from the full replica. 
 .PopulatePartial "C:\SALES\FY96.MDB" 
 
 .Close 
 End With 
 
End Sub 
 
```
