---
title: Proveedor de transporte y modelo operativo de administrador de trabajos en cola MAPI
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b0f8d8f0-fed7-4a7c-bc40-e935f159591d
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: 26d9982248fde015a584eb79cc248bafc5afc6bb
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594036"
---
# <a name="transport-provider-and-mapi-spooler-operational-model"></a>Proveedor de transporte y modelo operativo de administrador de trabajos en cola MAPI

  
  
**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
Inicialización del proveedor de transporte, inicio, procesamiento, cierre y deinitialization se llevan a cabo mediante una serie de llamadas desde la cola de MAPI para el proveedor de transporte. Las llamadas se ordenan de la siguiente manera:
  
1. La cola MAPI llama a la función [XPProviderInit](xpproviderinit.md) , pasa un objeto de soporte técnico, obtiene el objeto de proveedor y comprueba que el proveedor de transporte y la cola MAPI admiten un números de versión compatible de intervalo de MAPI. 
    
2. La cola MAPI llama al método [IXPProvider::TransportLogon](ixpprovider-transportlogon.md) de la [IXPProvider: IUnknown](ixpprovideriunknown.md) interfaz. Se establece una sesión entre la cola MAPI y el proveedor de transporte con las credenciales en la sección del perfil actual. El proveedor de transporte devuelve un objeto de inicio de sesión. 
    
3. La cola MAPI llama al método de [IXPLogon::AddressTypes](ixplogon-addresstypes.md) . El proveedor de transporte devuelve una lista de los identificadores únicos (UID) y tipos de direcciones de correo electrónico que acepte. 
    
4. El proveedor de transporte llama al método [IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md) para crear la fila correspondiente en la tabla de estado MAPI. 
    
5. La cola MAPI llama al método de [IXPLogon::TransportNotify](ixplogon-transportnotify.md) para habilitar la recepción y transmisión de mensajes. 
    
6. Si solicitada por el proveedor de transporte de su devuelto de la llamada **TransportLogon** , la cola MAPI llama periódicamente el método [IXPLogon::Idle](ixplogon-idle.md) . Procesamiento en inactividad es útil si el proveedor de transporte necesita sondean el sistema de mensajería subyacente para los mensajes nuevos o realizar otras tareas de prioridad baja. 
    
7. La cola MAPI y el proveedor de transporte envían y reciben mensajes. Para obtener más información, vea [Modelo de envío de mensajes](message-submission-model.md) y [Modelo de recepción de mensajes](message-reception-model.md). La cola MAPI atiende las solicitudes de transporte y llama a los objetos de soporte técnico, mensajes y datos adjuntos.
    
8. La cola MAPI llama el método **TransportNotify** para deshabilitar la recepción y transmisión de mensajes. 
    
9. La cola MAPI libera los objetos de inicio de sesión y proveedor. Para obtener más información, vea el método [IXPProvider::Shutdown](ixpprovider-shutdown.md) . 
    

