---
title: Eventos WillChangeField y FieldChangeComplete (ADO)
TOCTitle: WillChangeField and FieldChangeComplete Events (ADO)
ms:assetid: bc4455a6-2925-33dc-d04f-8ea570e5e370
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249904(v=office.15)
ms:contentKeyID: 48547407
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 40e9572988ca3335ef93ecf46d00a716ba29c595
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485520"
---
# <a name="willchangefield-and-fieldchangecomplete-events-ado"></a><span data-ttu-id="e5c0b-102">Eventos WillChangeField y FieldChangeComplete (ADO)</span><span class="sxs-lookup"><span data-stu-id="e5c0b-102">WillChangeField and FieldChangeComplete Events (ADO)</span></span>


<span data-ttu-id="e5c0b-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="e5c0b-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="e5c0b-p101">Al evento **WillChangeField** se le llama antes de que una operación pendiente cambie el valor de uno o varios objetos [Field](field-object-ado.md) en el objeto [Recordset](recordset-object-ado.md). Al evento **FieldChangeComplete** se le llama después de que el valor de uno o varios objetos **Field** haya cambiado.</span><span class="sxs-lookup"><span data-stu-id="e5c0b-p101">The **WillChangeField** event is called before a pending operation changes the value of one or more [Field](field-object-ado.md) objects in the [Recordset](recordset-object-ado.md). The **FieldChangeComplete** event is called after the value of one or more **Field** objects has changed.</span></span>

## <a name="syntax"></a><span data-ttu-id="e5c0b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5c0b-106">Syntax</span></span>

<span data-ttu-id="e5c0b-107">De*cFields*, *campos*, WillChangeField *adStatus*, *pRecordset*</span><span class="sxs-lookup"><span data-stu-id="e5c0b-107">WillChangeField*cFields*, *Fields*, *adStatus*, *pRecordset*</span></span>

<span data-ttu-id="e5c0b-108">FieldChangeComplete*cFields*, *campos*, *pError*, *adStatus*, *pRecordset*</span><span class="sxs-lookup"><span data-stu-id="e5c0b-108">FieldChangeComplete*cFields*, *Fields*, *pError*, *adStatus*, *pRecordset*</span></span>

## <a name="parameters"></a><span data-ttu-id="e5c0b-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e5c0b-109">Parameters</span></span>

  - <span data-ttu-id="e5c0b-110">*cFields*</span><span class="sxs-lookup"><span data-stu-id="e5c0b-110">*cFields*</span></span>

  - <span data-ttu-id="e5c0b-111">Valor **Long** que indica el número de objetos **Field** en *Fields*.</span><span class="sxs-lookup"><span data-stu-id="e5c0b-111">A **Long** that indicates the number of **Field** objects in *Fields*.</span></span>

  - <span data-ttu-id="e5c0b-112">*Fields*</span><span class="sxs-lookup"><span data-stu-id="e5c0b-112">*Fields*</span></span>

  - <span data-ttu-id="e5c0b-113">Para **WillChangeField**, el parámetro *Fields* es una matriz de **valores de tipo Variant** que contiene objetos **Field** con los valores originales.</span><span class="sxs-lookup"><span data-stu-id="e5c0b-113">For **WillChangeField**, the *Fields* parameter is an array of **Variants** that contains **Field** objects with the original values.</span></span>  
      
    <span data-ttu-id="e5c0b-114">Para **FieldChangeComplete**, el parámetro *Fields* es una matriz de **valores de tipo Variant** que contiene objetos **Field** con los valores modificados.</span><span class="sxs-lookup"><span data-stu-id="e5c0b-114">For **FieldChangeComplete**, the *Fields* parameter is an array of **Variants** that contains **Field** objects with the changed values.</span></span>

  - <span data-ttu-id="e5c0b-115">*pError*</span><span class="sxs-lookup"><span data-stu-id="e5c0b-115">*pError*</span></span>

  - <span data-ttu-id="e5c0b-p102">Objeto [Error](error-object-ado.md). Describe el error que se produjo si el valor de *adStatus* es **adStatusErrorsOccurred**; de lo contrario, no se establece ningún valor.</span><span class="sxs-lookup"><span data-stu-id="e5c0b-p102">An [Error](error-object-ado.md) object. It describes the error that occurred if the value of *adStatus* is **adStatusErrorsOccurred**; otherwise it is not set.</span></span>

  - <span data-ttu-id="e5c0b-118">*valor de adStatus*</span><span class="sxs-lookup"><span data-stu-id="e5c0b-118">*adStatus*</span></span>

  - [<span data-ttu-id="e5c0b-119">EventStatusEnum</span><span class="sxs-lookup"><span data-stu-id="e5c0b-119">EventStatusEnum</span></span>](eventstatusenum.md)
    
    <span data-ttu-id="e5c0b-p103">Cuando se llama a **WillChangeField**, este parámetro se establece en **adStatusOK** si la operación que provocó el evento se realizó correctamente. Se establece en **adStatusCantDeny** si este evento no puede solicitar la cancelación de la operación pendiente.</span><span class="sxs-lookup"><span data-stu-id="e5c0b-p103">When **WillChangeField** is called, this parameter is set to **adStatusOK** if the operation that caused the event was successful. It is set to **adStatusCantDeny** if this event cannot request cancellation of the pending operation.</span></span>
    
    <span data-ttu-id="e5c0b-122">Cuando se llama a **FieldChangeComplete**, este parámetro se establece en **adStatusOK** si la operación que provocó el evento se realizó correctamente, o en **adStatusErrorsOccurred** si se produjo un error en la operación.</span><span class="sxs-lookup"><span data-stu-id="e5c0b-122">When **FieldChangeComplete** is called, this parameter is set to **adStatusOK** if the operation that caused the event was successful, or to **adStatusErrorsOccurred** if the operation failed.</span></span>
    
    <span data-ttu-id="e5c0b-123">Antes de que **WillChangeField** vuelva, establezca este parámetro en **adStatusCancel** para solicitar la cancelación de la operación pendiente.</span><span class="sxs-lookup"><span data-stu-id="e5c0b-123">Before **WillChangeField** returns, set this parameter to **adStatusCancel** to request cancellation of the pending operation.</span></span>
    
    <span data-ttu-id="e5c0b-124">Antes de que **FieldChangeComplete** vuelva, establezca este parámetro en **adStatusUnwantedEvent** para impedir notificaciones posteriores.</span><span class="sxs-lookup"><span data-stu-id="e5c0b-124">Before **FieldChangeComplete** returns, set this parameter to **adStatusUnwantedEvent** to prevent subsequent notifications.</span></span>

  - <span data-ttu-id="e5c0b-125">*Connection*</span><span class="sxs-lookup"><span data-stu-id="e5c0b-125">*pRecordset*</span></span>

  - <span data-ttu-id="e5c0b-p104">Objeto **Recordset**. El objeto **Recordset** para el que se produjo este evento.</span><span class="sxs-lookup"><span data-stu-id="e5c0b-p104">A **Recordset** object. The **Recordset** for which this event occurred.</span></span>

## <a name="remarks"></a><span data-ttu-id="e5c0b-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e5c0b-128">Remarks</span></span>

<span data-ttu-id="e5c0b-129">Un evento **WillChangeField** o **FieldChangeComplete** se puede producir al establecer la propiedad [Value](value-property-ado.md) y llamar al método [Update](update-method-ado.md) con parámetros de tipo array (matriz) para field (campo) y value (valor).</span><span class="sxs-lookup"><span data-stu-id="e5c0b-129">A **WillChangeField** or **FieldChangeComplete** event may occur when setting the [Value](value-property-ado.md) property and calling the [Update](update-method-ado.md) method with field and value array parameters.</span></span>
