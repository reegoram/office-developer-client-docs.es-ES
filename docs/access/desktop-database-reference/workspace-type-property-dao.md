---
title: Workspace.Type Property (DAO)
TOCTitle: Type Property
ms:assetid: 89e59280-d2cd-b6a2-16c5-9f14f42fdd99
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197086(v=office.15)
ms:contentKeyID: 48546177
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d062adbde4e9d7053e61342b7433939d4fbffcb8
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25483983"
---
# <a name="workspacetype-property-dao"></a><span data-ttu-id="8f10f-102">Workspace.Type Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="8f10f-102">Workspace.Type Property (DAO)</span></span>


<span data-ttu-id="8f10f-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="8f10f-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="8f10f-p101">Establece o devuelve un valor que indica el tipo operativo o el tipo de datos de un objeto. **Integer** de sólo lectura.</span><span class="sxs-lookup"><span data-stu-id="8f10f-p101">Sets or returns a value that indicates the operational type or data type of an object. Read-only **Integer**.</span></span>

## <a name="syntax"></a><span data-ttu-id="8f10f-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8f10f-106">Syntax</span></span>

<span data-ttu-id="8f10f-107">*expresión* . Tipo de</span><span class="sxs-lookup"><span data-stu-id="8f10f-107">*expression* .Type</span></span>

<span data-ttu-id="8f10f-108">*expresión* Variable que representa un objeto **Workspace** .</span><span class="sxs-lookup"><span data-stu-id="8f10f-108">*expression* A variable that represents a **Workspace** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="8f10f-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8f10f-109">Remarks</span></span>

<span data-ttu-id="8f10f-110">Para un objeto **Workspace**, los posibles valores de configuración y devueltos son los siguientes.</span><span class="sxs-lookup"><span data-stu-id="8f10f-110">For a **Workspace** object, the possible settings and return values are as follows.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8f10f-111">Constante</span><span class="sxs-lookup"><span data-stu-id="8f10f-111">Constant</span></span></p></th>
<th><p><span data-ttu-id="8f10f-112">Tipo de área de trabajo</span><span class="sxs-lookup"><span data-stu-id="8f10f-112">Workspace type</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f10f-113"><strong>dbUseJet</strong></span><span class="sxs-lookup"><span data-stu-id="8f10f-113"><strong>dbUseJet</strong></span></span></p></td>
<td><p><span data-ttu-id="8f10f-114">El objeto <strong>Workspace</strong> está conectado al motor de base de datos de Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="8f10f-114">The <strong>Workspace</strong> is connected to the Microsoft Access database engine.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f10f-115"><strong>dbUseODBC</strong></span><span class="sxs-lookup"><span data-stu-id="8f10f-115"><strong>dbUseODBC</strong></span></span></p></td>
<td><p><span data-ttu-id="8f10f-116">El objeto <strong>Workspace</strong> está conectado a un origen de datos ODBC.</span><span class="sxs-lookup"><span data-stu-id="8f10f-116">The <strong>Workspace</strong> is connected to an ODBC data source.</span></span></p></td>
</tr>
</tbody>
</table>
