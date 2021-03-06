---
title: IMAPIOffline IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIOffline
api_type:
- COM
ms.assetid: 211281ff-3c22-1b51-4b72-ca1e313c7202
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 20d8c39765b0dbbfdde530361894d0a27876010a
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25401282"
---
# <a name="imapioffline--iunknown"></a>IMAPIOffline : IUnknown

  
  
**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
Proporciona información de un objeto sin conexión.
  
|||
|:-----|:-----|
|Suministrado por:  <br/> |Consulta en [IMAPIOfflineMgr](imapiofflinemgrimapioffline.md) <br/> |
|Llamado por:  <br/> |Cliente  <br/> |
|Identificador de interfaz:  <br/> |IID_IMAPIOffline  <br/> |
   
## <a name="vtable-order"></a>Orden vtable

|||
|:-----|:-----|
|**[SetCurrentState](imapioffline-setcurrentstate.md)** <br/> |Establece el estado actual de un objeto sin conexión a en línea o sin conexión.  <br/> |
|**[GetCapabilities](imapioffline-getcapabilities.md)** <br/> |Obtiene las condiciones para la que se admiten las devoluciones de llamada por un objeto sin conexión.  <br/> |
|**[GetCurrentState](imapioffline-getcurrentstate.md)** <br/> |Obtiene el estado en línea o sin conexión actual de un objeto sin conexión.  <br/> |
| *Miembro de marcador de posición*  <br/> |Este miembro es un marcador de posición y no se admite.  <br/> |
   
## <a name="remarks"></a>Comentarios

Un cliente usa **[HrOpenOfflineObj](hropenofflineobj.md)** para abrir y obtener un objeto sin conexión que admite **IMAPIOfflineMgr**. Debido a que **IMAPIOfflineMgr** hereda de [IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx), el cliente puede consultar esta interfaz (mediante el uso de [IUnknown:: QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx)) para obtener un puntero al puntero de interfaz para **IMAPIOffline** para el objeto sin conexión. El cliente puede, a continuación, obtener o establecer el estado actual del objeto, u Obtenga información acerca de las funciones de devolución de llamada del objeto (mediante una llamada a **IMAPIOffline::GetCapabilities** ) y elija Configurar las devoluciones de llamada mediante el uso de **[IMAPIOfflineMgr](imapiofflinemgrimapioffline.md)**. 
  
Un miembro de esta interfaz es un marcador de posición reservado para el uso interno de Microsoft Outlook 2013 y está sujeta a cambios. Otros miembros de esta interfaz deben usarse sólo como se indica. 
  
## <a name="see-also"></a>Vea también



[IMAPIOfflineMgr : IMAPIOffline](imapiofflinemgrimapioffline.md)


[Información sobre la API de estado sin conexión](about-the-offline-state-api.md)
  
[Constantes MAPI](mapi-constants.md)
  
[Interfaces MAPI](mapi-interfaces.md)

