---
title: Codificación de un mensaje con TNEF
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6b86d9a9-6876-4885-ae1e-8571b25b85cc
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: cdaa03cfbc0bbd0fcf6a320ecf8fae9f372d5781
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25382529"
---
# <a name="encoding-a-message-with-tnef"></a>Codificación de un mensaje con TNEF

**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
Cuando se envía un mensaje, el proveedor de transporte puede crear un archivo que se utiliza para contener el mensaje durante la transmisión. A continuación, se ajusta una interfaz [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) alrededor del archivo. El proveedor de transporte, a continuación, usa métodos [ITnef](itnefiunknown.md) para escribir las propiedades del mensaje en la secuencia en un formato con etiqueta que permite que las propiedades que desea descodificar fácilmente por los proveedores de transporte receptora. 
  
**Para representar un mensaje completo en un solo archivo**
  
1. Obtener un objeto TNEF pasando un objeto [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) y un mensaje en la función [OpenTnefStreamEx](opentnefstreamex.md) . 
    
2. Para obtener una lista de todas las propiedades definidas para el mensaje llamando al método [IMAPIProp::GetPropList](imapiprop-getproplist.md) . 
    
3. Utilizar los métodos [IMAPIProp](imapipropiunknown.md) para excluir todas las propiedades compatibles con el sistema de mensajería. En un momento adecuado, escribir esas propiedades en el sistema de mensajería en el formato requerido por el sistema de mensajería. 
    
4. Llame a [ITnef::AddProps](itnef-addprops.md) para codificar las propiedades restantes, incluidos todos los datos adjuntos. 
    
5. Llame al método [ITnef::Finish](itnef-finish.md) para codificar el mensaje en la secuencia TNEF después de que se agregan todas las propiedades solicitadas. 
    
6. Llame al método [ITnef::OpenTaggedBody](itnef-opentaggedbody.md) para obtener el texto del mensaje con etiqueta. Este texto etiquetado se escribe en el sistema de mensajería con los métodos de la interfaz [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) OLE. 
    
7. Llame al método [IUnknown:: Release](https://msdn.microsoft.com/library/ms682317%28VS.85%29.aspx) para liberar el objeto **ITnef** . 
    
**Para procesar un mensaje TNEF entrante**
  
1. Obtener un objeto de mensaje MAPI desde la cola MAPI y escribir las propiedades de encabezado de mensaje en el nuevo mensaje MAPI.
    
2. Crear e inicializar un objeto [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) para incluir los datos TNEF desde el mensaje entrante. 
    
3. Pase el mensaje MAPI y el objeto [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) a la función [OpenTnefStreamEx](opentnefstreamex.md) . 
    
4. Descodificar la información de los datos TNEF llamando al método [ITnef::ExtractProps](itnef-extractprops.md) . 
    
   > [!NOTE]
   > Cualquier cosa descodificar **ExtractProps** sobrescribirá propiedades descodificadas de sobre del mensaje entrante. Es decir, las propiedades TNEF extraídas sobrescribirán las propiedades existentes en un mensaje. 
  
5. Procesar el texto del mensaje con etiqueta llamando a [ITnef::OpenTaggedBody](itnef-opentaggedbody.md) y analizar el texto para recuperar las posiciones de los datos adjuntos. 
    
6. Guarde el mensaje mediante una llamada a [IMAPIProp::SaveChanges](imapiprop-savechanges.md).
    
7. Liberar el objeto TNEF llamando al método [IUnknown:: Release](https://msdn.microsoft.com/library/ms682317%28VS.85%29.aspx) . 
    

