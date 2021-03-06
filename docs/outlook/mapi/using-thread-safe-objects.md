---
title: Utilizar objetos seguros para subprocesos
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e688db5e-d1a1-4afc-998f-b3d31eb6239b
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: 49a94b785a51b4b0c3082832145250eec0745a19
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580981"
---
# <a name="using-thread-safe-objects"></a>Utilizar objetos seguros para subprocesos

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Las aplicaciones cliente pueden asumir que objetos usan directamente o como las devoluciones de llamada siempre son seguros para subprocesos, excepto en los casos siguientes:
  
- Objeto de estado del proveedor de transporte obtenido a través de una llamada de cliente a [IMAPISession::OpenEntry](imapisession-openentry.md) con un identificador de entrada de fila de tabla de estado del proveedor. 
    
- Todos los objetos de formulario MAPI obtenidos a través de una llamada de cliente a [MAPIOpenFormMgr](mapiopenformmgr.md). Objetos de formulario siguen las reglas del modelo de apartamento y deben usar los clientes ellas y todos los objetos contenidos por ellos sólo en el subproceso que los creó.
    
Cuando un cliente obtiene acceso a la fila del proveedor de transporte de la tabla de estado que incluye el identificador de entrada del objeto de estado asociado, el cliente puede llamar a **OpenEntry** con ese identificador de entrada para abrir el objeto de estado. Este objeto de estado no es seguros para subprocesos, debido a que los proveedores de transporte se ejecutan en el contexto de la cola MAPI y no mantienen un contexto independiente para su objeto de estado. El objeto de estado presta atención a las reglas del modelo de apartamento y clientes deben usar sólo en el subproceso que lo creó. 
  
Un cliente también debe invocar [MAPIInitialize](mapiinitialize.md) en cada subproceso antes de usar los objetos MAPI y [MAPIUninitialize](mapiuninitialize.md) una vez finalizada que usan. Estas llamadas deben realizarse incluso si los objetos que se va a utilizar se pasan al subproceso de un origen externo. **MAPIInitialize** y **MAPIUninitialize** se pueden llamar desde cualquier parte excepto desde dentro de una función de Win32 **DllMain** , una función que se invoca mediante el sistema cuando se inicializan y se termina procesos y subprocesos, o tras las llamadas a la ** LoadLibrary** y funciones de **FreeLibrary** . 
  
Nunca se deben suponer indirecta utilizar objetos como seguros para subprocesos. Uso indirecto objetos son devueltos por los métodos que requieren punteros de interfaz de destino como parámetros de entrada. Ejemplos de estos métodos son **IMAPIProp::CopyTo** y **CopyProps**, **IMAPIFolder::CopyFolder** y **CopyMessage**y **IMsgServiceAdmin::CopyMsgService**. Si desea que un proveedor de servicios para llamar a este tipo de objeto desde un subproceso distinto de aquél en el que se ha pasado, el proveedor es responsable de forma explícita el cálculo de referencias del objeto.
  

