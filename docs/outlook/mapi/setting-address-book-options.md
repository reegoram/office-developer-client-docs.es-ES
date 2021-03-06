---
title: Configurar opciones de libreta de direcciones
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9bd31233-fc8d-4e0a-9f1b-218c5ecb6d1b
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: 0d93fde7d654f0ee56dcda9f2fb69ad622e476dd
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22593623"
---
# <a name="setting-address-book-options"></a>Configurar opciones de libreta de direcciones

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Puede establecer tres propiedades que se describen las opciones para el uso de la libreta de direcciones:
  
- **PR_AB_SEARCH_PATH** ([PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md))
    
    La propiedad **PR_AB_SEARCH_PATH** se usa en [IAddrBook::ResolveName](iaddrbook-resolvename.md) para determinar los contenedores a estar involucradas en la resolución de nombres y el orden en que deben estar involucradas. Para cada contenedor de **PR_AB_SEARCH_PATH**, **IAddrBook::ResolveName** llama a su método [IABContainer:: ResolveNames](iabcontainer-resolvenames.md) . Contenedores al principio de **PR_AB_SEARCH_PATH** se buscan antes de contenedores al final de **PR_AB_SEARCH_PATH**. 
    
    El orden de búsqueda en **PR_AB_SEARCH_PATH** se especifica mediante una estructura [SRowSet](srowset.md) , la misma estructura que se usa para representar las filas de una tabla. Puede ver la ruta de acceso de búsqueda actual llamando al método [IAddrBook::GetSearchPath](iaddrbook-getsearchpath.md) y cambiar llamando al método [IAddrBook::SetSearchPath](iaddrbook-setsearchpath.md) . 
    
- **PR_AB_DEFAULT_DIR** ([PidTagAbDefaultDir](pidtagabdefaultdir-canonical-property.md))
    
    La propiedad **PR_AB_DEFAULT_DIR** es el identificador de entrada del contenedor de la libreta de direcciones que se mostrará inicialmente cuando se muestra la libreta de direcciones. La configuración de Active directory predeterminada permanece en vigor hasta que la cambie llamando al método [IAddrBook::SetDefaultDir](iaddrbook-setdefaultdir.md) . Puede ver el directorio predeterminado llamando al método [IAddrBook::GetDefaultDir](iaddrbook-getdefaultdir.md) . 
    
- **PR_AB_DEFAULT_PAB** ([PidTagAbDefaultPab](pidtagabdefaultpab-canonical-property.md))
    
Estas tres propiedades son especiales porque no puede trabajar con ellos mediante los métodos **IMAPIProp** estándares. En su lugar, debe usar los métodos de **IAddrBook** . Debido a que ninguna de estas propiedades se pueden cambiar con **IMAPIProp::SetProps**, no es necesario llamar a **IMAPIProp::SaveChanges** para realizar cambios permanentes. Las modificaciones realizadas a través de los métodos **IAddrBook** surtan efecto inmediatamente. 
  
## <a name="see-also"></a>Recursos adicionales



[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)

