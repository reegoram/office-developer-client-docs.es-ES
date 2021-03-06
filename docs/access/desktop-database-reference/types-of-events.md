---
title: Tipos de eventos (referencia de escritorio de la base de datos de Access)
TOCTitle: Types of Events
ms:assetid: 94660fc1-65c3-1d21-c451-f3898014e0b6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249660(v=office.15)
ms:contentKeyID: 48546414
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ffb3bd48db4d8071e56553f4ea5bf79b83952466
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25484998"
---
# <a name="types-of-events"></a>Tipos de eventos


**Se aplica a**: Access 2013 | Office 2013



Hay dos tipos básicos de eventos. Los "eventos Will", a los que se llama antes de iniciarse una operación, normalmente incluyen "Will" en su nombre; por ejemplo, **WillChangeRecordset** o **WillConnect**. Los eventos a los que se llama después de finalizar un evento suelen incluir "Complete" en su nombre; por ejemplo, **RecordChangeComplete** o **ConnectComplete**. Hay excepciones, como **InfoMessage**, pero éstas se producen después de finalizar la operación asociada.

## <a name="will-events"></a>Eventos Will

Los controladores de eventos a los que se llama antes de iniciarse la operación permiten examinar o modificar los parámetros de la operación y, a continuación, cancelar la operación o permitir que finalice. Estas rutinas de controlador de eventos suele tener nombres de la forma * evento ****será*.

## <a name="complete-events"></a>Eventos Complete

Los controladores de eventos a los que se llama después de finalizar una operación pueden notificar a la aplicación la finalización de la operación. Estos controladores de eventos también reciben una notificación cuando un controlador de eventos Will cancela una operación pendiente. Estas rutinas de controlador de eventos suele tener nombres de la forma ***evento * completo**.

Los eventos Will y Complete suelen utilizarse emparejados.

## <a name="other-events"></a>Otros eventos

Los otros controladores de eventos, es decir, los eventos cuyos nombres no tienen el formato **va a * (evento)*** o ***(evento) * completo:** se llama sólo una vez que finaliza una operación. Estos eventos son **Disconnect**, **EndOfRecordset** e **InfoMessage**.

