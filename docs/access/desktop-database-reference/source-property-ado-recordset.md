---
title: Source (propiedad, Recordset ADO)
TOCTitle: Source Property (ADO Recordset)
ms:assetid: 523ea81e-d011-8d87-436e-084b6eba0908
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249269(v=office.15)
ms:contentKeyID: 48544843
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a3caeef4bb13ac4b68f3d3d5a62e0ce624d9d515
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25483770"
---
# <a name="source-property-ado-recordset"></a><span data-ttu-id="a79a5-102">Source (propiedad, Recordset ADO)</span><span class="sxs-lookup"><span data-stu-id="a79a5-102">Source Property (ADO Recordset)</span></span>


<span data-ttu-id="a79a5-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="a79a5-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="a79a5-104">Indica el origen de datos de un objeto [Recordset](recordset-object-ado.md).</span><span class="sxs-lookup"><span data-stu-id="a79a5-104">Indicates the data source for a [Recordset](recordset-object-ado.md) object.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="a79a5-105">Configuración y valores devueltos</span><span class="sxs-lookup"><span data-stu-id="a79a5-105">Settings and Return Values</span></span>

<span data-ttu-id="a79a5-106">Establece un valor de tipo **String** o una referencia al objeto [Command](command-object-ado.md); sólo devuelve un valor de tipo **String** que indica el origen del objeto **Recordset**.</span><span class="sxs-lookup"><span data-stu-id="a79a5-106">Sets a **String** value or [Command](command-object-ado.md) object reference; returns only a **String** value that indicates the source of the **Recordset**.</span></span>

## <a name="remarks"></a><span data-ttu-id="a79a5-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a79a5-107">Remarks</span></span>

<span data-ttu-id="a79a5-108">Utilice la propiedad **Source** para especificar un origen de datos para un objeto **Recordset** mediante uno de los siguientes: una variable de objeto **Command**, una instrucción SQL, un procedimiento almacenado o un nombre de tabla.</span><span class="sxs-lookup"><span data-stu-id="a79a5-108">Use the **Source** property to specify a data source for a **Recordset** object using one of the following: a **Command** object variable, an SQL statement, a stored procedure, or a table name.</span></span>

<span data-ttu-id="a79a5-p101">Si se establece la propiedad **Source** en un objeto **Command**, la propiedad [ActiveConnection](activeconnection-property-ado.md) del objeto **Recordset** heredará el valor de la propiedad **ActiveConnection** para el objeto **Command** especificado. No obstante, la lectura de la propiedad **Source** no devuelve un objeto **Command**; por el contrario, devuelve la propiedad [CommandText](commandtext-property-ado.md) del objeto **Command** en el que se ha establecido la propiedad **Source**.</span><span class="sxs-lookup"><span data-stu-id="a79a5-p101">If you set the **Source** property to a **Command** object, the [ActiveConnection](activeconnection-property-ado.md) property of the **Recordset** object will inherit the value of the **ActiveConnection** property for the specified **Command** object. However, reading the **Source** property does not return a **Command** object; instead, it returns the [CommandText](commandtext-property-ado.md) property of the **Command** object to which you set the **Source** property.</span></span>

<span data-ttu-id="a79a5-111">Si la propiedad **Source** es una instrucción SQL, un procedimiento almacenado o un nombre de tabla, puede optimizar el rendimiento, se pasa el argumento *Options* adecuado con la llamada al método [Open](open-method-ado-recordset.md) .</span><span class="sxs-lookup"><span data-stu-id="a79a5-111">If the **Source** property is an SQL statement, a stored procedure, or a table name, you can optimize performance by passing the appropriate *Options* argument with the [Open](open-method-ado-recordset.md) method call.</span></span>

<span data-ttu-id="a79a5-112">La propiedad **Source** es de lectura y escritura para los objetos **Recordset** cerrados y de sólo lectura para los objetos **Recordset** abiertos.</span><span class="sxs-lookup"><span data-stu-id="a79a5-112">The **Source** property is read/write for closed **Recordset** objects and read-only for open **Recordset** objects.</span></span>
