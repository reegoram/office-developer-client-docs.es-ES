---
title: Copiar un perfil
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b722a157-0d92-404d-9075-39547241dbb7
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: 53b7099ae74828a97eb703b865ba30ab385e9a5f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564937"
---
# <a name="copying-a-profile"></a>Copiar un perfil

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Es una forma de crear un perfil copiar de un perfil existente y modifique los servicios de mensajes es necesario y proveedores de servicios. Copiar un perfil de implica el uso de un objeto de administración de perfiles, proporcionado por MAPI a través de la función [MAPIAdminProfiles](mapiadminprofiles.md) . 
  
 **Para copiar un perfil**
  
1. Llame a **MAPIAdminProfiles** para recuperar un puntero de interfaz **IProfAdmin** . 
    
2. Llame a [IProfAdmin::GetProfileTable](iprofadmin-getprofiletable.md) para obtener acceso a la tabla de perfil. 
    
3. Crear una restricción de propiedad con una estructura de [SPropertyRestriction](spropertyrestriction.md) para que coincida con **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) con el nombre del perfil que se va a copiar. 
    
4. Llamar a [IMAPITable:: FindRow](imapitable-findrow.md) para localizar la fila apropiada en la tabla de perfil. 
    
5. Llame a [IProfAdmin::CopyProfile](iprofadmin-copyprofile.md), pasando el valor de la columna **PR_DISPLAY_NAME** como el parámetro _lpszOldProfileName_ . 
    

