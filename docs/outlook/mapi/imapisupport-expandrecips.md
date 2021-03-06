---
title: IMAPISupportExpandRecips
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.ExpandRecips
api_type:
- COM
ms.assetid: 78edd549-d557-489a-85f5-adfb5c44a7d4
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: 379fdc47f35fb183dd0bf551e421422abb106c0e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591016"
---
# <a name="imapisupportexpandrecips"></a>IMAPISupport::ExpandRecips

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Finaliza la lista de destinatarios de un mensaje, expansión de las listas de distribución en particular.
  
```cpp
HRESULT ExpandRecips(
  LPMESSAGE lpMessage,
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a>Parámetros

 _lpMessage_
  
> [entrada] Un puntero al mensaje que tiene la lista de destinatarios que va a procesar.
    
 _lpulFlags_
  
> [out] Un puntero a una máscara de bits de indicadores que controla el tipo de procesamiento que se produce. Se pueden establecer los siguientes indicadores:
    
NEEDS_PREPROCESSING 
  
> El mensaje debe ser preprocesan antes de enviarlo.
    
NEEDS_SPOOLER 
  
> La cola MAPI (en lugar de a la que el autor de la llamada se complementa el proveedor de transporte) debe enviar el mensaje.
    
## <a name="return-value"></a>Valor devuelto

S_OK 
  
> Lista de destinatarios del mensaje se ha procesado correctamente.
    
## <a name="remarks"></a>Comentarios

El método **IMAPISupport::ExpandRecips** se implementa para objetos de soporte técnico de proveedor de almacén de mensajes. Los proveedores de almacén de mensajes llamada **ExpandRecips** para que solicite MAPI para llevar a cabo las siguientes tareas: 
  
- Expanda algunas listas de distribución personales a los destinatarios de componente.
    
- Reemplace todos los nombres para mostrar que se han cambiado por los nombres originales.
    
- Marcar las entradas duplicadas.
    
- Resolver todas las direcciones de uso único. 
    
- Compruebe si el mensaje necesita preprocesamiento y, si es así, establezca la marca que señala _lpulFlags_ a NEEDS_PREPROCESSING. 
    
 **ExpandRecips** se expande las listas de distribución que tengan el tipo de dirección de mensajería de MAPIPDL. 
  
## <a name="notes-to-callers"></a>Notas para los llamadores

Llame siempre a **ExpandRecips** como parte de su procesamiento del mensaje. Realizar una llamada a **ExpandRecips** uno de la primera llamadas en la implementación del método [IMessage::SubmitMessage](imessage-submitmessage.md) . 
  
## <a name="see-also"></a>Recursos adicionales



[IMessage::SubmitMessage](imessage-submitmessage.md)
  
[IMAPISupport: IUnknown](imapisupportiunknown.md)

