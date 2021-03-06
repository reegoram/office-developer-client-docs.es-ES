---
title: Quitar entradas de la libreta de direcciones
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 107ebcd7-b612-4139-b676-c3851f15bc74
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: 2c5d7a2114f4a85b9f63cd778e899a83d335ff45
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581282"
---
# <a name="removing-address-book-entries"></a>Quitar entradas de la libreta de direcciones
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Método de [IABContainer::DeleteEntries](iabcontainer-deleteentries.md) de su contenedor se llama para quitar a uno o más destinatarios. **DeleteEntries** tiene dos parámetros: una matriz de identificadores de entrada que representa los destinatarios que se eliminará y un valor de indicadores reservados. Eliminación de un destinatario afecta a la tabla de contenido de su contenedor. Además de eliminar al destinatario, el contenedor debe eliminar la fila de tabla de contenido que representa al destinatario. Cuando se ha quitado la fila de la tabla, el contenedor debe emitir una notificación de la tabla para cada cliente registrado. 
  
### <a name="to-implement-iabcontainerdeleteentries"></a>Para implementar IABContainer::DeleteEntries
  
1. Eliminación de cada destinatario representado por el identificador de entrada de su contenedor.
    
2. Si la tabla de contenido de su contenedor está abierto:
    
   - Enviar una notificación de _fnevTableModified_ con el **ulTableEvent** conjunto de miembros a TABLE_ROW_DELETED a los clientes registrados para cada fila de la tabla de contenido eliminado. Si su proveedor usa la utilidad de notificación, llame a [IMAPISupport::Notify](imapisupport-notify.md) para enviar estas notificaciones. 
    
   - Si el proveedor admite las notificaciones de objeto, también enviar una notificación de _fnevObjectDeleted_ . 
    

