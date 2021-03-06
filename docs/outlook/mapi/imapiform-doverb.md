---
title: IMAPIFormDoVerb
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIForm.DoVerb
api_type:
- COM
ms.assetid: 8b582571-b448-4476-91d9-4cc94dbec710
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 60a8c89afe0d70a1737c6ce694c66359fd6aae4f
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25398097"
---
# <a name="imapiformdoverb"></a>IMAPIForm::DoVerb

  
  
**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
Las solicitudes que el formulario realiza tareas con independencia de se asocia a un verbo específico.
  
```cpp
HRESULT DoVerb(
  LONG iVerb,
  LPMAPIVIEWCONTEXT lpViewContext,
  ULONG_PTR hwndParent,
  LPCRECT lprcPosRect
);
```

## <a name="parameters"></a>Parámetros

 _iVerb_
  
> [entrada] El número asociado con uno de los verbos del formulario.
    
 _lpViewContext_
  
> [entrada] Un puntero a un objeto de contexto de la vista. El parámetro _lpViewContext_ puede ser **null**.
    
 _hwndParent_
  
> [entrada] Un identificador de la ventana principal de windows o cuadros de diálogo que muestra este método. El parámetro _hwndParent_ debe ser **null** si la ventana o el cuadro de diálogo no es modal. 
    
 _lprcPosRect_
  
> [entrada] Un puntero a un Win32 estructura de [rectángulo](https://msdn.microsoft.com/library/dd162897%28VS.85%29.aspx) que contiene el tamaño y la posición de la ventana del formulario. 
    
## <a name="return-value"></a>Valor devuelto

S_OK 
  
> Correctamente que se invocó el verbo.
    
OLEOBJ_S_CANNOT_DOVERB_NOW 
  
> El verbo representado por el parámetro _iVerb_ es válido, pero el formulario no puede realizar las operaciones asociadas actualmente con él. 
    
## <a name="remarks"></a>Comentarios

Visores de formulario llamar al método **IMAPIForm::DoVerb** para solicitar que el formulario realice las tareas que asocia con cada verbo que es compatible con el formulario. 
  
Cada uno de los verbos admitidos se identifica mediante un valor numérico, pasado a **DoVerb** en el parámetro _iVerb_ . Las implementaciones típicas de **DoVerb** contienen una instrucción **switch** que comprueba los valores que son válidos para el parámetro _iVerb_ para el formulario. 
  
## <a name="notes-to-implementers"></a>Notas a los implementadores

Si el Visor de formulario especifica un contexto de vista en el parámetro _lpViewContext_ , usar en su implementación **DoVerb** en lugar de al contexto de la vista que se pasan en una llamada anterior al método [IMAPIForm::SetViewContext](imapiform-setviewcontext.md) . Hacer que los cambios son necesarios para las estructuras de datos internos y no guardar el contexto de vista. 
  
En su implementación **DoVerb** , realice las siguientes tareas: 
  
- Ejecutar el código que es necesario para el verbo concreto que está asociado con el parámetro _iVerb_ . 
    
- Si es necesario, restaure el contexto de vista original.
    
- Si se ha pasado un número de verbo desconocido en, devolver MAPI_E_NO_SUPPORT. De lo contrario, devolver un resultado basándose en el éxito o el fracaso de cualquier verbo se ha ejecutado.
    
- Cerrar el formulario. Siempre es su responsabilidad para cerrar el formulario una vez que finaliza una llamada **DoVerb** . 
    
Algunos verbos, como la impresión, deben ser modales con respecto a la llamada **DoVerb** , es decir, la operación indicada se debe finalizar antes de la llamada **DoVerb** devuelve. 
  
Para obtener la estructura de **rectángulo** usada por la ventana de un formulario, llame a la función [GetWindowRect](https://msdn.microsoft.com/library/ms633519) . 
  
No guarde el controlador en el parámetro _hwndParent_ porque, aunque normalmente permanece válido hasta la finalización de **DoVerb**, puede ser destruir inmediatamente tras la devolución de llamada.
  
## <a name="notes-to-callers"></a>Notas para los llamadores

Puede realizar los verbos no modal actuar como verbos modales señalando _lpViewContext_ a una implementación de contexto de vista que devuelve la marca VCSTATUS_MODAL desde su método [IMAPIViewContext::GetViewStatus](imapiviewcontext-getviewstatus.md) . 
  
Para obtener más información acerca de los verbos en MAPI, vea [Verbos de formulario](form-verbs.md). Para obtener más información acerca de cómo se administran los verbos en OLE, vea [OLE y la transferencia de datos](https://msdn.microsoft.com/library/ms693425%28VS.85%29.aspx).
  
## <a name="mfcmapi-reference"></a>Referencia de MFCMAPI

Para obtener un ejemplo de código de MFCMAPI, vea la siguiente tabla.
  
|**File**|**Función**|**Comentario**|
|:-----|:-----|:-----|
|MyMAPIFormViewer.cpp  <br/> |CMyMAPIFormViewer::CallDoVerb  <br/> |MFCMAPI usa el método **IMAPIForm::DoVerb** para invocar un verbo en un formulario.  <br/> |
   
## <a name="see-also"></a>Vea también



[IMAPIForm::SetViewContext](imapiform-setviewcontext.md)
  
[IMAPIViewContext::GetViewStatus](imapiviewcontext-getviewstatus.md)
  
[IMAPIForm : IUnknown](imapiformiunknown.md)


[MFCMAPI como un ejemplo de código](mfcmapi-as-a-code-sample.md)
  
[Verbos de formulario](form-verbs.md)

