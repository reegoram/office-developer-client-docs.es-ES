---
title: Características de almacenamiento de mensajes
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d9167cd2-fc88-46b1-9a26-151955fb606c
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 7e99d9d2e1289ed98ba659e97b05c8ea6d891a74
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581814"
---
# <a name="message-store-features"></a>Características de almacenamiento de mensajes

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Los proveedores de almacén de mensajes son más complejos que otros proveedores de servicios MAPI en que los proveedores de almacén de mensajes tienen una amplia gama de características opcionales que se pueden implementar. La lista de las características necesarias para un proveedor de almacén de mensajes es bastante corta. Sin embargo, un proveedor de almacén de mensajes típico admitirá un número de características opcionales, debido a que muchas de las características opcionales están muy útil o requerido por la mayoría de los clientes MAPI. En la siguiente tabla se enumera las características principales que pueden implementar los proveedores de almacén de mensajes y si cada característica es obligatorio u opcional para el mensaje de todos los proveedores de almacén de mensaje predeterminada de los proveedores de almacén.
  
|**Característica**|**All**|**Default**|
|:-----|:-----|:-----|
|Proporcionar estado con la tabla de estado MAPI.  <br/> |Obligatorio  <br/> |Obligatorio  <br/> |
|Implementación de objetos de carpeta.  <br/> |Obligatorio  <br/> |Obligatorio  <br/> |
|Implementación de objetos de mensaje.  <br/> |Obligatorio  <br/> |Obligatorio  <br/> |
|Proporcionar informes de lectura y nonread.  <br/> |Obligatorio  <br/> |Obligatorio  <br/> |
|Proporcionar una interfaz de progreso.  <br/> |Obligatorio  <br/> |Obligatorio  <br/> |
|Proporcionar una interfaz de configuración.  <br/> |Obligatorio  <br/> |Obligatorio  <br/> |
|Tablas de contenido asociada de soporte para la compatibilidad con el formulario y la vista.  <br/> |Opcional  <br/> |Opcional  <br/> |
|Proveedor de almacén de envío de mensajes con el mensaje.  <br/> |Opcional  <br/> |Obligatorio  <br/> |
|Recibir mensajes con el proveedor de almacén de mensajes.  <br/> |Opcional  <br/> |Obligatorio  <br/> |
|Compatibilidad con datos adjuntos de mensajes.  <br/> |Opcional  <br/> |Opcional  <br/> |
|Compatibilidad con formato de texto enriquecido para los mensajes.  <br/> |Opcional  <br/> |Opcional  <br/> |
|Proporcionar notificaciones.  <br/> |Opcional  <br/> |Opcional  <br/> |
|Compatibilidad con las búsquedas.  <br/> |Opcional  <br/> |Opcional  <br/> |
|Compatibilidad estrechamente con acoplamiento proveedores de almacén y transporte de mensajes.  <br/> |Opcional  <br/> |Opcional  <br/> |
|Compatibilidad con que no sean de reutilización de los identificadores de entrada.  <br/> |Opcional  <br/> |Opcional  <br/> |
   
Muchas de las características opcionales se pueden anunciar a MAPI y las aplicaciones de cliente mediante la configuración de diversos indicadores en el mensaje almacén de propiedad de **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) del objeto. Las características requeridas no tienen indicadores asociados con ellos. **PR_STORE_SUPPORT_MASK** se requiere en el almacén de mensajes, carpetas y objetos de mensaje. 
  
## <a name="see-also"></a>Recursos adicionales



[Desarrollar un proveedor de almac�n de mensajes de MAPI](developing-a-mapi-message-store-provider.md)

