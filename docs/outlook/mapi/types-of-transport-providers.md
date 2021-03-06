---
title: Tipos de proveedores de transporte
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 772ecab1-7e91-415b-bae8-af8ffb7b7ed9
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: a9bba55b585b09d6a5779ba41a283b20c645656f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576235"
---
# <a name="types-of-transport-providers"></a>Tipos de proveedores de transporte

  
  
**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
Todos los proveedores de transporte admiten una gama de características estándares, como:
  
- Proporcionar seguridad adecuada para el sistema de mensajería subyacente.
    
- Enviar y recibir mensajes desde el sistema de mensajería subyacente.
    
- Exposición de los tipos de direcciones compatible con los proveedores de transporte para que la cola MAPI y las aplicaciones cliente pueden usarlas de forma apropiada.
    
- Aceptación de entrega para destinatarios concretos.
    
Además, MAPI admite dos tipos especializados de proveedores para sistemas de mensajería específicos.
  
|**Tipo de transporte**|**Funcionalidad agregada**|
|:-----|:-----|
|Transporte remoto  <br/> |Permite la interoperabilidad con los clientes conectados de forma remota.  <br/> |
|Transporte TNEF  <br/> |Permite que las propiedades MAPI que se conserven en sistemas de mensajería que no es compatible.  <br/> |
   
Los transportes TNEF se usan para traducir los mensajes entre los sistemas de mensajería que admiten distintos conjuntos de propiedades MAPI. Los transportes TNEF usan la MAPI [ITnef: IUnknown](itnefiunknown.md) interfaz para convertir todas las propiedades que el sistema de destino no se puede representar directamente en una secuencia de datos binarios que se puede adjuntar al mensaje. Más adelante, otro transporte TNEF puede usar **ITnef** para descodificar la secuencia de datos y que las propiedades MAPI originales esté disponible para las aplicaciones cliente. Además, la compatibilidad con TNEF se requiere si su transporte necesita admitir clases de mensaje personalizadas. Para obtener información acerca de cómo implementar los transportes TNEF, vea [desarrollar un proveedor de transporte TNEF-Enabled](developing-a-tnef-enabled-transport-provider.md).
  
Si su proveedor de transporte no es uno de estos tipos, debe implementar con las funciones básicas de MAPI y funciones de red disponibles en la plataforma de destino.
  

