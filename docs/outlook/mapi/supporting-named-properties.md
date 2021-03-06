---
title: Admitir propiedades con nombre
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2e742ecd-2dcd-46a8-9d4e-2cec2c6f795e
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: 9ee41469914e52295af219428f26854662c9e2f9
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582251"
---
# <a name="supporting-named-properties"></a>Admitir propiedades con nombre

  
  
**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
Any object that implements the [IMAPIProp: IUnknown](imapipropiunknown.md) interface can support named properties. Es necesario para la compatibilidad con las propiedades con nombre: 
  
- Proveedores de libreta de direcciones que permiten las entradas de otros proveedores que se copiarán a sus contenedores.
    
- Los proveedores que se pueden usar para crear tipos de mensaje arbitrario del almacén de mensajes.
    
Compatibilidad con la propiedad con nombre es opcional para todos los demás proveedores de servicio. Proveedores de servicios que admiten las propiedades con nombre deben implementar la asignación de nombre a identificador en los métodos [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) y [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) . Los clientes llaman **GetNamesFromIDs** para recuperar los nombres correspondientes para uno o varios identificadores de propiedad en el intervalo de 0 x 8000 sobre y **a GetIDsFromNames** para crear o recuperar los identificadores de uno o varios nombres. 
  
Proveedores de servicios que no admiten las propiedades con nombre deben:
  
- Producirá un error en las llamadas a [IMAPIProp::SetProps](imapiprop-setprops.md) para establecer las propiedades con identificadores de 0 x 8000 o posterior mediante la devolución de MAPI_E_UNEXPECTED_ID en la matriz [SPropProblem](spropproblem.md) . 
    
- Devolver MAPI_E_NO_SUPPORT de los métodos [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) y [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) . 
    

