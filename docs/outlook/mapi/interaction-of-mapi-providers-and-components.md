---
title: Interacción de componentes y proveedores MAPI
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2c0e010b-0432-4ef7-a243-3a4b46f0a19d
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: c81da7673d6c0c59de6992bc46362069daf71b42
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592629"
---
# <a name="interaction-of-mapi-providers-and-components"></a>Interacción de componentes y proveedores MAPI

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Proveedores de servicios de MAPI de ningún tipo deben seguir ciertas instrucciones para trabajar con otros componentes MAPI. Cada proveedor de servicios debe:
  
- Usar los objetos de proveedor y el inicio de sesión correctos para la inicialización.
    
- Devolver una tabla de distribución de proveedor de puntos de entrada para el sistema de mensajería en la inicialización.
    
- Registrar una fila de tabla de estado MAPI para cada recurso propiedad por el proveedor y llame al método [IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md) en los momentos adecuados. 
    
- Use el método [IMAPISupport::NewUID](imapisupport-newuid.md) para obtener los identificadores exclusivos válidos (UID). 
    
- Admite las interfaces MAPI comunes en los objetos que se devuelve.
    
- Use las funciones de asignación de memoria MAPI para asignar la memoria que se devuelven a las aplicaciones de cliente y para liberar memoria asignada por otros elementos del subsistema MAPI.
    
- Mantener una sección de perfil, si es necesario, para almacenar las credenciales para el sistema de mensajería subyacente.
    
- Utilice el método [IMAPISupport::RegisterPreprocessor](imapisupport-registerpreprocessor.md) para registrar los mensajes de las funciones de preprocesamiento. 
    
- Incluyen los archivos de encabezado adecuado (incluido mapispi.h) que definición constantes comunes, estructuras, interfaces y valores devuelven.
    
- Siga las convenciones de formato de dirección para los tipos de dirección comunes.
    

