---
title: Evitar el uso de IStreamSetSize para extender una secuencia
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b6de594f-e331-4421-956b-86ee0b5518fe
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: 9245d4913c2832b8c942093e65cf088643a1947c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592083"
---
# <a name="avoiding-using-istreamsetsize-to-extend-a-stream"></a>Evite usar IStream::SetSize para extender una secuencia

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Al escribir en secuencias, en ocasiones, es necesario ampliar ellos porque su tamaño inicial ya no es suficiente. Usar el método OLE **IStream::Write** para hacerlo en lugar de **IStream:: SetSize**. **IStream::Write** extiende automáticamente la secuencia, realizar ** IStream:: SetSize ** innecesarios. Al llamar a **IStream::Write** sin **IStream:: SetSize** puede ser más rápido que hacer el **SetSize** llamada antes de **escribir**hasta tres veces.
  

