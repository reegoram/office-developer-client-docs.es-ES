---
title: Propiedades Recordset, SourceRecordset (RDS)
TOCTitle: Recordset, SourceRecordset Properties (RDS)
ms:assetid: 5f4bb72d-ddfa-41c0-c353-b3a6632b4a91
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249345(v=office.15)
ms:contentKeyID: 48545160
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a66e803738c16d291817eb80e7f680ff9c3c71e9
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25484824"
---
# <a name="recordset-sourcerecordset-properties-rds"></a><span data-ttu-id="a1e73-102">Propiedades Recordset, SourceRecordset (RDS)</span><span class="sxs-lookup"><span data-stu-id="a1e73-102">Recordset, SourceRecordset Properties (RDS)</span></span>


<span data-ttu-id="a1e73-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="a1e73-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="a1e73-104">Indica el objeto **Recordset** devuelto desde un objeto de negocio personalizado.</span><span class="sxs-lookup"><span data-stu-id="a1e73-104">Indicates the **Recordset** object returned from a custom business object.</span></span>

## <a name="syntax"></a><span data-ttu-id="a1e73-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1e73-105">Syntax</span></span>

<span data-ttu-id="a1e73-106">*DataControl*. SourceRecordset = *conjunto de registros*</span><span class="sxs-lookup"><span data-stu-id="a1e73-106">*DataControl*.SourceRecordset = *Recordset*</span></span>

<span data-ttu-id="a1e73-107">*Conjunto de registros* = *DataControl*. Conjunto de registros</span><span class="sxs-lookup"><span data-stu-id="a1e73-107">*Recordset* = *DataControl*.Recordset</span></span>

## <a name="parameters"></a><span data-ttu-id="a1e73-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a1e73-108">Parameters</span></span>

  - <span data-ttu-id="a1e73-109">*DataControl*</span><span class="sxs-lookup"><span data-stu-id="a1e73-109">*DataControl*</span></span>

  - <span data-ttu-id="a1e73-110">Variable de objeto que representa un objeto [RDS.DataControl](datacontrol-object-rds.md).</span><span class="sxs-lookup"><span data-stu-id="a1e73-110">An object variable that represents an [RDS.DataControl](datacontrol-object-rds.md) object.</span></span>

  - <span data-ttu-id="a1e73-111">*Recordset*</span><span class="sxs-lookup"><span data-stu-id="a1e73-111">*Recordset*</span></span>

  - <span data-ttu-id="a1e73-112">Variable de objeto que representa un objeto **Recordset**.</span><span class="sxs-lookup"><span data-stu-id="a1e73-112">An object variable that represents a **Recordset** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="a1e73-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a1e73-113">Remarks</span></span>

<span data-ttu-id="a1e73-114">Es posible establecer la propiedad **SourceRecordset** en un objeto [Recordset](recordset-object-ado.md) devuelto desde un objeto de negocio personalizado.</span><span class="sxs-lookup"><span data-stu-id="a1e73-114">You can set the **SourceRecordset** property to a [Recordset](recordset-object-ado.md) returned from a custom business object.</span></span>

<span data-ttu-id="a1e73-p101">Estas propiedades permiten que una aplicación controle el proceso de enlace por medio de un proceso personalizado. Reciben un conjunto de filas ajustado a un objeto **Recordset** para poder interactuar directamente con el objeto **Recordset**, realizar acciones como establecer propiedades o iterar a lo largo del objeto **Recordset**.</span><span class="sxs-lookup"><span data-stu-id="a1e73-p101">These properties allow an application to handle the binding process by means of a custom process. They receive a rowset wrapped in a **Recordset** so that you can interact directly with the **Recordset**, performing actions such as setting properties or iterating through the **Recordset**.</span></span>

<span data-ttu-id="a1e73-117">Es posible establecer la propiedad **SourceRecordset** o leer la propiedad **Recordset** en tiempo de ejecución en el código de scripting.</span><span class="sxs-lookup"><span data-stu-id="a1e73-117">You can set the **SourceRecordset** property or read the **Recordset** property at run time in scripting code.</span></span>

<span data-ttu-id="a1e73-118">**SourceRecordset** es una propiedad de solo escritura, al contrario que la propiedad **Recordset**, que es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="a1e73-118">**SourceRecordset** is a write-only property, in contrast to the **Recordset** property, which is a read-only property.</span></span>
