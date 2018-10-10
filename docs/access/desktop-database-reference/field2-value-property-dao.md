---
title: Field2.Value Property (DAO)
TOCTitle: Value Property
ms:assetid: 6ead6ba8-1613-99c7-7968-56f5b81b2385
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195566(v=office.15)
ms:contentKeyID: 48545515
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 8ae14ee13c0b94a477550b0f20cec2e1fc31fdd6
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485224"
---
# <a name="field2value-property-dao"></a><span data-ttu-id="5a9e6-102">Field2.Value Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="5a9e6-102">Field2.Value Property (DAO)</span></span>


<span data-ttu-id="5a9e6-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="5a9e6-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="5a9e6-p101">Establece o devuelve el valor de un objeto. **Variant** de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="5a9e6-p101">Sets or returns the value of an object. Read/write **Variant**.</span></span>

## <a name="syntax"></a><span data-ttu-id="5a9e6-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a9e6-106">Syntax</span></span>

<span data-ttu-id="5a9e6-107">*expresión* . Valor</span><span class="sxs-lookup"><span data-stu-id="5a9e6-107">*expression* .Value</span></span>

<span data-ttu-id="5a9e6-108">*expresión* Variable que representa un objeto **Field2** .</span><span class="sxs-lookup"><span data-stu-id="5a9e6-108">*expression* A variable that represents a **Field2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="5a9e6-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5a9e6-109">Remarks</span></span>

<span data-ttu-id="5a9e6-110">La configuración o el valor devuelto es un tipo de datos Variant que da como resultado un valor apropiado para el tipo de datos, tal como especifica la propiedad **Type** de un objeto.</span><span class="sxs-lookup"><span data-stu-id="5a9e6-110">The setting or return value is a Variant data type that evaluates to a value appropriate for the data type, as specified by the **Type** property of an object.</span></span>

<span data-ttu-id="5a9e6-111">En general, la propiedad **Value** se usa para recuperar y alterar los datos en los objetos **Recordset**.</span><span class="sxs-lookup"><span data-stu-id="5a9e6-111">Generally, the **Value** property is used to retrieve and alter data in **Recordset** objects.</span></span>

<span data-ttu-id="5a9e6-p102">La propiedad **Value** es la propiedad predeterminada de los objetos **Field2**, **Parameter** y **Property**. Por tanto, puede establecer o devolver el valor de uno de esos objetos refiriéndose a ellos directamente en vez de especificar la propiedad **Value**.</span><span class="sxs-lookup"><span data-stu-id="5a9e6-p102">The **Value** property is the default property of the **Field2**, **Parameter**, and **Property** objects. Therefore, you can set or return the value of one of these objects by referring to them directly instead of specifying the **Value** property.</span></span>

<span data-ttu-id="5a9e6-114">Si intenta establecer o devolver la propiedad **Value** en un contexto poco apropiado (por ejemplo, la propiedad **Value** de un objeto **Field2** en la colección **Fields** de un objeto **TableDef**) se producirá un error capturable.</span><span class="sxs-lookup"><span data-stu-id="5a9e6-114">Trying to set or return the **Value** property in an inappropriate context (for example, the **Value** property of a **Field2** object in the **Fields** collection of a **TableDef** object) will cause a trappable error.</span></span>


> [!NOTE]
> <P><span data-ttu-id="5a9e6-115">Cuando se lean valores decimales de una base de datos de Microsoft SQL Server, se les dará formato con notación científica a través de un área de trabajo de Microsoft Access, pero aparecerán como valores decimales normales a través de un área de trabajo de ODBCDirect.</span><span class="sxs-lookup"><span data-stu-id="5a9e6-115">When reading decimal values from a Microsoft SQL Server database, they will be formatted using scientific notation through a Microsoft Access workspace, but will appear as normal decimal values through an ODBCDirect workspace.</span></span></P>

