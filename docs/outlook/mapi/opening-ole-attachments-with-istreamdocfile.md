---
title: Datos adjuntos OLE de apertura con IStreamDocfile
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f91df63c-ff6d-4c63-a665-5bcfdabe7e0e
description: 'Última modificación: 06 de julio de 2012'
ms.openlocfilehash: 2de13be34e8d81f88bfba872dda6e5534eb431bd
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25386554"
---
# <a name="opening-ole-attachments-with-istreamdocfile"></a>Datos adjuntos OLE de apertura con IStreamDocfile

**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
Al abrir datos adjuntos objeto OLE, use la interfaz de **IStreamDocfile** en lugar de [IStream](https://msdn.microsoft.com/library/windows/desktop/aa380034%28v=vs.85%29.aspx) o [IStorage](https://msdn.microsoft.com/library/windows/desktop/aa380015%28v=vs.85%29.aspx). 

**IStreamDocfile** proporciona un acceso directo al objeto mediante almacenamiento estructurado, lo que elimina la necesidad de realizar una operación de copia y reducir la sobrecarga. **IStreamDocfile** es una implementación específica de **IStream** con el contenido del objeto stream que garantiza que se aplicar formato de almacenamiento estructurado. **IStreamDocfile** se implementa mediante los proveedores de almacén de mensajes. 
  

