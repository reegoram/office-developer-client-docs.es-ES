---
title: Carpetas de la vista MAPI
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a1936ec2-bf8a-4242-a41d-64d26b813bd0
description: '�ltima modificaci�n: s�bado, 23 de julio de 2011'
ms.openlocfilehash: 3a89588294f07dca97fb48e56d2cde890c3f80ae
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568822"
---
# <a name="mapi-view-folders"></a>Carpetas de la vista MAPI

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Ver carpetas son las carpetas de ra�z que contienen informaci�n asociada para definir dise�os de presentaci�n alternativo para el contenido de carpetas de mensajes interpersonales (IPM). Ver carpetas residen en el directorio ra�z para el almac�n de mensajes y, por lo tanto, no est�n visibles en la aplicaci�n cliente t�pica. No cada almac�n de mensajes incluye carpetas de vista; deben incluir s�lo los almacenes de mensajes que est�n configurados para funcionar como almac�n de mensajes predeterminado para la sesi�n de ellos.  
  
MAPI es compatible con dos carpetas de vista:
  
- Com�n: La carpeta de vista comunes contiene vistas que son est�ndar para el almac�n de mensajes y pueden ser usadas por cualquier usuario de un cliente que tiene acceso el almac�n de mensajes. El identificador de entrada de la carpeta común de vista se almacena en la propiedad de **PR_COMMON_VIEWS_ENTRYID** ([PidTagCommonViewsEntryId](pidtagcommonviewsentryid-canonical-property.md)) de la tienda.
    
- Personal: La carpeta de la vista personal contiene las vistas definidas por un usuario en particular. MAPI define la propiedad **PR_VIEWS_ENTRYID** ([PidTagViewsEntryId](pidtagviewsentryid-canonical-property.md)) para contener el identificador de entrada de la carpeta de la vista personal. Usar vistas personales, por ejemplo, un usuario podr�a ser en un grupo de mensajes ordenados por remitente, listado s�lo el asunto y la recepci�n de fecha del mensaje; otro usuario podr�a buscar en el mismo grupo ordenado por fecha, el asunto, el remitente y el tama�o de los mensajes de la lista.
    
## <a name="see-also"></a>Vea tambi�n



[Carpetas de MAPI](mapi-folders.md)

