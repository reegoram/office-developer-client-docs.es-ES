---
title: Implementación de seguridad
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 62db34a0-887c-4607-94ad-d8cae68b35c2
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: c2926e7c94178d5a3135f34e2ab3b3ae11d145dd
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568486"
---
# <a name="implementing-security"></a>Implementación de seguridad

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Si el sistema de mensajería lo requiere, el proveedor de transporte es responsable de implementar un nivel adecuado de seguridad para el acceso al sistema de mensajería. Cada mensaje entrante o saliente enviado a través de un proveedor de transporte por la cola MAPI se administra en el contexto de una sesión de inicio de sesión del proveedor. El proveedor de transporte puede mostrar un cuadro de diálogo de inicio de sesión para el usuario que solicita las credenciales de un usuario antes de establecer una conexión de este tipo. Como alternativa, el proveedor de transporte puede almacenar las credenciales del usuario especificadas anteriormente en el intervalo de la propiedad segura dentro de una sección de perfil y usar para el acceso sin preguntar al usuario.
  
Al implementar la seguridad de su proveedor de transporte, tenga en cuenta lo siguiente:
  
- Con varios proveedores de servicio instalado, puede haber una gran variedad de nombres y contraseñas asociadas a un usuario.
    
- MAPI permite varias sesiones con varias identidades. Los proveedores se recomienda para admitir varias sesiones pero no son necesarios para hacerlo.
    
- Cada sesión con un proveedor de transporte está asociada por MAPI con una sección discreta en el perfil del usuario. El proveedor de transporte puede usar el método [IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md) para obtener acceso a esta sección, que se puede utilizar para almacenar cualquier información asociada con esta sesión, incluidas las credenciales. 
    
- Con varios proveedores de transporte instalados, no es necesariamente true que el usuario sólo tiene una dirección de correo electrónico única. Un usuario puede tener una dirección de correo electrónico independiente para cada proveedor de transporte instalada o puede tener una dirección distinta para cada sesión en un único proveedor.
    
Para obtener más información sobre cómo almacenar credenciales en secciones del perfil, vea [Servicios de mensajes y los perfiles](message-services-and-profiles.md) y [IProfSect: IMAPIProp](iprofsectimapiprop.md).
  

