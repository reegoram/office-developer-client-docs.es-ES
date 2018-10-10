---
title: Direction (propiedad, ADO)
TOCTitle: Direction Property (ADO)
ms:assetid: 51a94abb-7ce9-9adb-2b76-5391eb9f6863
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249262(v=office.15)
ms:contentKeyID: 48544823
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 611e5efbe53964c5ba255380e2659f024bd6be9a
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485305"
---
# <a name="direction-property-ado"></a><span data-ttu-id="eac2b-102">Direction (propiedad, ADO)</span><span class="sxs-lookup"><span data-stu-id="eac2b-102">Direction Property (ADO)</span></span>


<span data-ttu-id="eac2b-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="eac2b-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="eac2b-104">Indica si [Parameter](parameter-object-ado.md) representa un parámetro de entrada, de salida, de entrada y salida o si es el valor devuelto por un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="eac2b-104">Indicates whether the [Parameter](parameter-object-ado.md) represents an input parameter, an output parameter, an input and an output parameter, or if the parameter is the return value from a stored procedure.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="eac2b-105">Configuración y valores devueltos</span><span class="sxs-lookup"><span data-stu-id="eac2b-105">Settings and Return Values</span></span>

<span data-ttu-id="eac2b-106">Establece o devuelve un valor de tipo [ParameterDirectionEnum](parameterdirectionenum.md).</span><span class="sxs-lookup"><span data-stu-id="eac2b-106">Sets or returns a [ParameterDirectionEnum](parameterdirectionenum.md) value.</span></span>

## <a name="remarks"></a><span data-ttu-id="eac2b-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="eac2b-107">Remarks</span></span>

<span data-ttu-id="eac2b-p101">Use la propiedad **Direction** para especificar cómo pasa un parámetro a un procedimiento o desde este. La propiedad **Direction** es de lectura y escritura, lo que le permite trabajar con proveedores que no devuelven dicha información o establecerla cuando no se desea que ADO realice una llamada adicional al proveedor para recuperar información del parámetro.</span><span class="sxs-lookup"><span data-stu-id="eac2b-p101">Use the **Direction** property to specify how a parameter is passed to or from a procedure. The **Direction** property is read/write; this allows you to work with providers that don't return this information or to set this information when you don't want ADO to make an extra call to the provider to retrieve parameter information.</span></span>

<span data-ttu-id="eac2b-p102">No todos los proveedores pueden determinar la dirección de los parámetros de los procedimientos almacenados. En estos casos, es necesario establecer la propiedad **Direction** antes de ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="eac2b-p102">Not all providers can determine the direction of parameters in their stored procedures. In these cases, you must set the **Direction** property before you execute the query.</span></span>
