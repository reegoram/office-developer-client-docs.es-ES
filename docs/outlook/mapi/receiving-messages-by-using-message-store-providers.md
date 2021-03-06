---
title: Recibir mensajes usando proveedores de almacenamiento de mensajes
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4763951e-ccfd-453e-b99c-5c7d5efb90c2
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: 8a5df2e8f50d8de05ec43b03ae5b56887e76d505
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590193"
---
# <a name="receiving-messages-by-using-message-store-providers"></a>Recibir mensajes usando proveedores de almacenamiento de mensajes

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Los proveedores de almacén de mensajes no es necesario que admitir los envíos de mensajes entrantes (es decir, la compatibilidad con la capacidad de los proveedores de transporte y la cola de MAPI para utilizar el mensaje de proveedor de almacén como punto de entrega de mensajes). Sin embargo, si su proveedor de almacén de mensajes no es compatible con los envíos de mensajes entrantes, no puede usarse como el almacén de mensajes predeterminado.
  
Para admitir los envíos de mensajes entrantes, su proveedor de almacén de mensajes debe hacer lo siguiente:
  
- Admite los métodos [IMsgStore::GetReceiveFolderTable](imsgstore-getreceivefoldertable.md) y [IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md) para que las aplicaciones cliente pueden encontrar los mensajes entrantes. 
    
- Admite el método [IMsgStore::NotifyNewMail](imsgstore-notifynewmail.md) para que la cola MAPI puede informar al proveedor de almacenamiento de mensaje que ha llegado un mensaje nuevo. 
    
- Implementar notificaciones de modo que los clientes pueden registrar para la notificación de mensaje nuevo. Las notificaciones son opcionales, pero su proveedor debe implementarlos.
    
La secuencia de llamadas a métodos que se produce cuando se entrega un mensaje entrante a un almacén de mensajes es el siguiente:
  
1. La cola MAPI llama a [IMsgStore::OpenEntry](imsgstore-openentry.md) con la [propiedad EntryID](entryid.md) de bandeja de entrada para obtener una interfaz [IMAPIFolder](imapifolderimapicontainer.md) . 
    
2. La cola MAPI llama a [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) para obtener un nuevo objeto de mensaje. 
    
3. La cola MAPI pasa el objeto de mensaje para el proveedor de transporte.
    
4. El proveedor de transporte se rellena en las propiedades del mensaje con datos desde el sistema de mensajería subyacente y llama al método [IMAPIProp::SaveChanges](imapiprop-savechanges.md) del objeto del mensaje. 
    
5. El proveedor de almacén de mensajes utiliza su método de notificación para informar a los clientes registrados que ha llegado un mensaje nuevo.
    
6. La cola MAPI llama (método) [IMsgStore::NotifyNewMail](imsgstore-notifynewmail.md) del almacén de mensajes. 
    
## <a name="see-also"></a>Recursos adicionales



[Caracter�sticas de almac�n de mensajes](message-store-features.md)

