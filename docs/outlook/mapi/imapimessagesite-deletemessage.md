---
title: IMAPIMessageSiteDeleteMessage
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIMessageSite.DeleteMessage
api_type:
- COM
ms.assetid: 09955996-b904-4c0d-8ba5-954a8875c055
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 7b2761e20444c51d08380aee01c41eee797733eb
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396494"
---
# <a name="imapimessagesitedeletemessage"></a>IMAPIMessageSite::DeleteMessage

  
  
**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
Elimina el mensaje actual.
  
```cpp
HRESULT DeleteMessage(
  LPMAPIVIEWCONTEXT pViewContext,
  LPCRECT prcPosRect
);
```

## <a name="parameters"></a>Parámetros

 _pViewContext_
  
> [entrada] Un puntero a un objeto de contexto de la vista.
    
 _prcPosRect_
  
> [entrada] Un puntero a una estructura de [rectángulo](https://msdn.microsoft.com/library/dd162897%28VS.85%29.aspx) que contiene el tamaño de la ventana y la posición del formulario actual. El siguiente formulario que muestra también usa este rectángulo de la ventana. 
    
## <a name="return-value"></a>Valor devuelto

S_OK 
  
> La llamada se ha realizado correctamente y devuelva el valor esperado o los valores.
    
MAPI_E_NO_SUPPORT 
  
> La operación no es compatible con este sitio de mensaje.
    
## <a name="remarks"></a>Comentarios

Un objeto de formulario llama al método de **IMAPIMessageSite::DeleteMessage** para eliminar el mensaje que el formulario se muestra actualmente. 
  
## <a name="notes-to-callers"></a>Notas para los llamadores

Después de la devolución de **DeleteMessage**, objetos de formulario deben comprobar para un nuevo mensaje y descartar a sí mismos si no existe ninguno. Para determinar si el mensaje **en que deletemessage** actúa fue eliminado o movido a una carpeta de **Elementos eliminados** , un objeto de formulario puede llamar al método de [IMAPIMessageSite::GetSiteStatus](imapimessagesite-getsitestatus.md) para determinar si se ha devuelto la marca DELETE_IS_MOVE. 
  
## <a name="notes-to-implementers"></a>Notas a los implementadores

Si la implementación del Visor de un formulario del método **DeleteMessage** se mueve hasta el siguiente mensaje después de que elimina un mensaje, la implementación debe llamar al método [IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md) y pase el indicador VCDIR_DELETE antes de realizar la eliminación real. Si la implementación de un visor formulario de **DeleteMessage** mueve el mensaje eliminado (por ejemplo, en una carpeta de **Elementos eliminados** ), la implementación debe guardar cambios en el mensaje, si se modificó el mensaje. 
  
Una implementación típica de **DeleteMessage** realiza las tareas siguientes: 
  
1. Si la implementación traslada el mensaje, se llama al método [IPersistMessage::Save](ipersistmessage-save.md) , pasando **null** en el parámetro _pMessage_ y **true** en el parámetro _fSameAsLoad_ . 
    
2. Llama al método **IMAPIViewContext::ActivateNext** , pasando el indicador VCDIR_DELETE en el parámetro _ulDir_ . 
    
3. Si se produce un error en la llamada **ActivateNext** , devuelve. Si **ActivateNext** devuelve S_FALSE, llama al método [IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md) . 
    
4. Elimina o se mueve el mensaje.
    
Para obtener la estructura de **rectángulo** usada por la ventana de un formulario, llame a la función de Windows [GetWindowRect](https://msdn.microsoft.com/library/ms633519) . 
  
Para obtener una lista de las interfaces relacionadas con los servidores de formulario, vea [Interfaces de formulario MAPI](mapi-form-interfaces.md).
  
## <a name="mfcmapi-reference"></a>Referencia de MFCMAPI

Para obtener un ejemplo de código de MFCMAPI, vea la siguiente tabla.
  
|**File**|**Función**|**Comentario**|
|:-----|:-----|:-----|
|MyMAPIFormViewer.cpp  <br/> |CMyMAPIFormViewer::DeleteMessage  <br/> |No se ha implementado.  <br/> |
   
## <a name="see-also"></a>Vea también



[IMAPIMessageSite::GetSiteStatus](imapimessagesite-getsitestatus.md)
  
[IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md)
  
[IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md)
  
[IPersistMessage::Save](ipersistmessage-save.md)
  
[IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md)


[MFCMAPI como un ejemplo de código](mfcmapi-as-a-code-sample.md)
  
[Interfaces de formulario de MAPI](mapi-form-interfaces.md)

