---
title: CancelBatch (método, ADO)
TOCTitle: CancelBatch Method (ADO)
ms:assetid: be7bf073-ed0b-e24c-7ec0-b7379236782a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249925(v=office.15)
ms:contentKeyID: 48547463
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: cbc16d01e04bbcff7ff28ccc8e7cb4f3fd6f3dec
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485708"
---
# <a name="cancelbatch-method-ado"></a>CancelBatch (método, ADO)


**Se aplica a**: Access 2013 | Office 2013


Cancela una actualización por lotes que está pendiente.

## <a name="syntax"></a>Sintaxis

*conjunto de registros*. CancelBatch *AffectRecords*

## <a name="parameters"></a>Parámetros

  - *AffectRecords*

  - Es opcional. Valor de [AffectEnum](affectenum.md) que indica el número de registros afectados por el método **CancelBatch**.

## <a name="remarks"></a>Comentarios

Use el método **CancelBatch** para cancelar cualquier actualización pendiente en un objeto [Recordset](recordset-object-ado.md) en modo de actualización por lotes. Si el objeto **Recordset** está en modo de actualización inmediata y se llama a **CancelBatch** sin **adAffectCurrent**, se generará un error.

Si está modificando el registro actual o agregando un registro nuevo cuando llama a **CancelBatch**, ADO llamará primero al método [CancelUpdate](cancelupdate-method-ado.md) para cancelar los cambios almacenados en caché. A continuación, se cancelarán todos los cambios pendientes en el objeto **Recordset**.

Es posible que el registro actual sea indeterminable después de llamar a **CancelBatch**, sobre todo si se estaba agregando un registro nuevo. Por este motivo, se recomienda establecer la posición del registro actual en una ubicación conocida en el objeto **Recordset** después de la llamada a **CancelBatch**, llamando, por ejemplo al método [MoveFirst](movefirst-movelast-movenext-and-moveprevious-methods-ado.md).

Si un intento de cancelar las actualizaciones pendientes genera un error debido a un conflicto con los datos subyacentes (por ejemplo, otro usuario ha eliminado un registro), el proveedor devuelve advertencias a la colección [Errors](errors-collection-ado.md) pero no detiene la ejecución del programa. Se produce un error en tiempo de ejecución sólo si hay conflictos en todos los registros solicitados. Utilice la propiedad [Filter](filter-property-ado.md) (**adFilterAffectedRecords**) y la propiedad [Status](status-property-ado-recordset.md) para localizar los registros con conflictos.

