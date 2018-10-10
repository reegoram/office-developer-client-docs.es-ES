---
title: WillConnect (evento, ADO)
TOCTitle: WillConnect Event (ADO)
ms:assetid: 8b0e9955-4e7a-7af8-ce6c-7a4ba569a5bb
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249611(v=office.15)
ms:contentKeyID: 48546208
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c5493593998bf5484bd2247b32e114809b805fda
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25486675"
---
# <a name="willconnect-event-ado"></a><span data-ttu-id="be4ab-102">WillConnect (evento, ADO)</span><span class="sxs-lookup"><span data-stu-id="be4ab-102">WillConnect Event (ADO)</span></span>


<span data-ttu-id="be4ab-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="be4ab-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="be4ab-104">Al evento **WillConnect** se le llama antes de iniciarse una conexión.</span><span class="sxs-lookup"><span data-stu-id="be4ab-104">The **WillConnect** event is called before a connection starts.</span></span>

## <a name="syntax"></a><span data-ttu-id="be4ab-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="be4ab-105">Syntax</span></span>

<span data-ttu-id="be4ab-106">WillConnect*ConnectionString*, *UserID*, *contraseña*, *Opciones*, *adStatus*, *pConnection*</span><span class="sxs-lookup"><span data-stu-id="be4ab-106">WillConnect*ConnectionString*, *UserID*, *Password*, *Options*, *adStatus*, *pConnection*</span></span>

## <a name="parameters"></a><span data-ttu-id="be4ab-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="be4ab-107">Parameters</span></span>

  - <span data-ttu-id="be4ab-108">*ConnectionString*</span><span class="sxs-lookup"><span data-stu-id="be4ab-108">*ConnectionString*</span></span>

  - <span data-ttu-id="be4ab-109">**String** que contiene información de conexión para la conexión pendiente.</span><span class="sxs-lookup"><span data-stu-id="be4ab-109">A **String** that contains connection information for the pending connection.</span></span>

  - <span data-ttu-id="be4ab-110">*UserID*</span><span class="sxs-lookup"><span data-stu-id="be4ab-110">*UserID*</span></span>

  - <span data-ttu-id="be4ab-111">**String** que contiene un nombre de usuario para la conexión pendiente.</span><span class="sxs-lookup"><span data-stu-id="be4ab-111">A **String** that contains a user name for the pending connection.</span></span>

  - <span data-ttu-id="be4ab-112">*Password*</span><span class="sxs-lookup"><span data-stu-id="be4ab-112">*Password*</span></span>

  - <span data-ttu-id="be4ab-113">**String** que contiene una contraseña para la conexión pendiente.</span><span class="sxs-lookup"><span data-stu-id="be4ab-113">A **String** that contains a password for the pending connection.</span></span>

  - <span data-ttu-id="be4ab-114">*Options*</span><span class="sxs-lookup"><span data-stu-id="be4ab-114">*Options*</span></span>

  - <span data-ttu-id="be4ab-p101">Valor **Long** que indica cómo debe evaluar el proveedor el valor *ConnectionString*. La única opción es **adAsyncOpen**.</span><span class="sxs-lookup"><span data-stu-id="be4ab-p101">A **Long** value that indicates how the provider should evaluate the *ConnectionString*. Your only option is **adAsyncOpen**.</span></span>

  - <span data-ttu-id="be4ab-117">*valor de adStatus*</span><span class="sxs-lookup"><span data-stu-id="be4ab-117">*adStatus*</span></span>

  - [<span data-ttu-id="be4ab-118">EventStatusEnum</span><span class="sxs-lookup"><span data-stu-id="be4ab-118">EventStatusEnum</span></span>](eventstatusenum.md)
    
    <span data-ttu-id="be4ab-p102">Cuando el evento recibe una llamada, este parámetro se establece de forma predeterminada en **adStatusOK**. Si el evento no puede solicitar la cancelación de la operación pendiente, el parámetro se establece en **adStatusCantDeny**.</span><span class="sxs-lookup"><span data-stu-id="be4ab-p102">When this event is called, this parameter is set to **adStatusOK** by default. It is set to **adStatusCantDeny** if the event cannot request cancellation of the pending operation.</span></span>
    
    <span data-ttu-id="be4ab-p103">Antes de que este evento regrese, establezca este parámetro en **adStatusUnwantedEvent** para impedir notificaciones posteriores. Establezca este parámetro como **adStatusCancel** para solicitar la operación de conexión que provocó la cancelación de esta notificación.</span><span class="sxs-lookup"><span data-stu-id="be4ab-p103">Before this event returns, set this parameter to **adStatusUnwantedEvent** to prevent subsequent notifications. Set this parameter to **adStatusCancel** to request the connection operation that caused cancellation of this notification.</span></span>

  - <span data-ttu-id="be4ab-123">*pConnection*</span><span class="sxs-lookup"><span data-stu-id="be4ab-123">*pConnection*</span></span>

  - <span data-ttu-id="be4ab-p104">Objeto [Connection](connection-object-ado.md) al que se aplica esta notificación de eventos. Los cambios en los parámetros de **Connection** debidos al controlador del evento **WillConnect** no tendrán efecto en el objeto **Connection**.</span><span class="sxs-lookup"><span data-stu-id="be4ab-p104">The [Connection](connection-object-ado.md) object for which this event notification applies. Changes to the parameters of the **Connection** by the **WillConnect** event handler will have no effect on the **Connection**.</span></span>

## <a name="remarks"></a><span data-ttu-id="be4ab-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="be4ab-126">Remarks</span></span>

<span data-ttu-id="be4ab-p105">Cuando se llama al evento *WillConnect*, los parámetros **WillConnect**, *UserID*, *Password* y *Options* toman los valores establecidos por la operación que provocó este evento (la conexión pendiente), y se pueden cambiar antes de que el evento vuelva. **WillConnect** puede devolver una petición para cancelar la conexión pendiente.</span><span class="sxs-lookup"><span data-stu-id="be4ab-p105">When **WillConnect** is called, the *ConnectionString*, *UserID*, *Password*, and *Options* parameters are set to the values established by the operation that caused this event (the pending connection), and can be changed before the event returns. **WillConnect** may return a request that the pending connection be canceled.</span></span>

<span data-ttu-id="be4ab-129">Cuando este evento se cancela, se realiza una llamada a **ConnectComplete** con su parámetro *adStatus* establecido en \*\* adStatusErrorsOccurred\*\*.</span><span class="sxs-lookup"><span data-stu-id="be4ab-129">When this event is canceled, **ConnectComplete** will be called with its *adStatus* parameter set to **adStatusErrorsOccurred**.</span></span>
