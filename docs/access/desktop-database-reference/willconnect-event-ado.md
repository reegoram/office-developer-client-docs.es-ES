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
# <a name="willconnect-event-ado"></a>WillConnect (evento, ADO)


**Se aplica a**: Access 2013 | Office 2013


Al evento **WillConnect** se le llama antes de iniciarse una conexión.

## <a name="syntax"></a>Sintaxis

WillConnect*ConnectionString*, *UserID*, *contraseña*, *Opciones*, *adStatus*, *pConnection*

## <a name="parameters"></a>Parámetros

  - *ConnectionString*

  - **String** que contiene información de conexión para la conexión pendiente.

  - *UserID*

  - **String** que contiene un nombre de usuario para la conexión pendiente.

  - *Password*

  - **String** que contiene una contraseña para la conexión pendiente.

  - *Options*

  - Valor **Long** que indica cómo debe evaluar el proveedor el valor *ConnectionString*. La única opción es **adAsyncOpen**.

  - *valor de adStatus*

  - [EventStatusEnum](eventstatusenum.md)
    
    Cuando el evento recibe una llamada, este parámetro se establece de forma predeterminada en **adStatusOK**. Si el evento no puede solicitar la cancelación de la operación pendiente, el parámetro se establece en **adStatusCantDeny**.
    
    Antes de que este evento regrese, establezca este parámetro en **adStatusUnwantedEvent** para impedir notificaciones posteriores. Establezca este parámetro como **adStatusCancel** para solicitar la operación de conexión que provocó la cancelación de esta notificación.

  - *pConnection*

  - Objeto [Connection](connection-object-ado.md) al que se aplica esta notificación de eventos. Los cambios en los parámetros de **Connection** debidos al controlador del evento **WillConnect** no tendrán efecto en el objeto **Connection**.

## <a name="remarks"></a>Comentarios

Cuando se llama al evento *WillConnect*, los parámetros **WillConnect**, *UserID*, *Password* y *Options* toman los valores establecidos por la operación que provocó este evento (la conexión pendiente), y se pueden cambiar antes de que el evento vuelva. **WillConnect** puede devolver una petición para cancelar la conexión pendiente.

Cuando este evento se cancela, se realiza una llamada a **ConnectComplete** con su parámetro *adStatus* establecido en ** adStatusErrorsOccurred**.

