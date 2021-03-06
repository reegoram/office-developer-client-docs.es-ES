---
title: Información general sobre la arquitectura MAPI
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 00d2993c-d66a-4a00-9fb2-98696d29a007
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: a0f2efc17ca8790502f11d677498013cbe10205d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579357"
---
# <a name="mapi-architecture-overview"></a>Información general sobre la arquitectura MAPI
 
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
MAPI define una arquitectura modular, tal como se muestra en la siguiente ilustración.  
  
![Arquitectura de Outlook 2010] (media/amapi_43.gif "Arquitectura de Outlook 2010")
  
La aplicación de MAPI se conoce como una aplicación de cliente porque es un cliente del subsistema MAPI. Las aplicaciones basadas en mensajería emplean mensajería como una parte central de su procesamiento y ofrecen una amplia características de mensajería, como el intercambio de información de diversos tipos en diversos formatos y la capacidad para guardar y organizar la información localmente. Correo electrónico, programación, y las aplicaciones de flujo de trabajo son ejemplos de aplicaciones basadas en mensajería.
  
El subsistema MAPI se compone de una interfaz de usuario comunes y las interfaces de programación. La interfaz de usuario comunes es un conjunto de cuadros de diálogo que le ofrece las aplicaciones cliente de un aspecto coherente y a los usuarios una manera coherente de trabajar.
  
MAPI tiene interfaces que se usan por el subsistema MAPI, por los programadores de software de cliente y los desarrolladores de proveedor de servicio de programación. La interfaz de programación de MAPI es la interfaz de programación basada en objetos principal. La interfaz de programación de MAPI es similar al modelo de objetos de OLE componente y se usa en el subsistema MAPI y las aplicaciones de cliente basadas en mensajería escritas en C o C++. 
  
Como desarrollador de software de cliente, realizar llamadas MAPI directamente a través de la interfaz de programación de MAPI. Puede implementar la mensajería con una sola interfaz de cliente MAPI o una combinación de interfaces. Una sola aplicación puede realizar llamadas a métodos o funciones que pertenezcan a cualquiera de las interfaces.
  
## <a name="see-also"></a>Recursos adicionales

-[Arquitectura y las características MAPI](mapi-features-and-architecture.md)

