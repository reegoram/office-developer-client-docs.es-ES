---
title: Jerarquía de contención de objetos MAPI
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 33747835-6eeb-4e07-8f92-3cfa81eecd0f
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: 6350202eb22edc478f7738bebf6d7f0bc4684ee0
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566246"
---
# <a name="mapi-object-containment-hierarchy"></a>Jerarquía de contención de objetos MAPI
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
La relación de contención entre objetos especifica las dependencias que algunos objetos tienen en otros objetos de access. Para una aplicación cliente, el acceso a determinados objetos habilita el acceso a otros usuarios. En algunos casos, la relación de contención entre objetos de implementada por un proveedor de servicios sigue una jerarquía lógica. En otros casos, es arbitrario. 
  
Un cliente debe obtener acceso a un objeto de sesión MAPI antes de que pueden usar muchos otros objetos (por ejemplo, los proveedores de servicios y la libreta de direcciones MAPI).
  
Contención de almacén de mensajes se basa en la relación jerárquica entre los objetos en el almacén de mensajes: el almacén de mensajes de objetos propio, carpetas, mensajes y datos adjuntos. Como es lógico, los datos adjuntos están contenidos en los mensajes, los mensajes en carpetas y carpetas en el almacén de mensajes. La relación de contención coincide con esta jerarquía lógica. Para obtener acceso a un mensaje, por ejemplo, un cliente debe tener acceso a la carpeta que contiene el mensaje. Perfiles y objetos de estado son ejemplos de una relación de contención más arbitrario. Estos dos objetos están disponibles a través de la sesión. 
  
Con algunos objetos, los contenedores proporcionan el acceso de solo. Los datos adjuntos y los destinatarios son ejemplos de objetos que son totalmente dependientes en sus contenedores. Es el único acceso a un archivo adjunto o un destinatario a través del mensaje a la que pertenece. Otros objetos tienen las rutas de acceso alternativas. Estos objetos se asignan identificadores binarios, conocidos como los identificadores de entrada, por los proveedores de servicios que crean. Identificadores de entrada se pueden utilizar para tener acceso a sus objetos directamente, habilitar los clientes omitir el árbol de la contención. 
  
En la siguiente ilustración muestra la jerarquía de contención de MAPI. La sesión está en la parte superior del árbol de porque es que un cliente obtiene acceso a todos los demás objetos a través de la sesión. El siguiente nivel incluye la tabla de almacenamiento de mensajes, un objeto table que se enumera las propiedades para todos los proveedores de almacén de mensajes en la sesión actual y para proporcionar acceso a todos los proveedores de la libreta de direcciones de la libreta de direcciones. La libreta de direcciones y tabla de almacén de mensajes se utilizan para tener acceso a los objetos que implementan los proveedores de servicio en particular, se muestra a continuación, en orden de contención.
  
**Jerarquía de contención de MAPI**
  
![Jerarquía de contención de MAPI] (media/amapi_41.gif "Jerarquía de contención de MAPI")
  
## <a name="see-also"></a>Recursos adicionales

- [Objeto MAPI e Introducción a la interfaz](mapi-object-and-interface-overview.md)

