---
title: IMAPISessionOpenAddressBook
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.OpenAddressBook
api_type:
- COM
ms.assetid: 2b6a4c6a-bb71-4ea1-a3b6-90a2722880fb
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 51bf5f8455d4cb790d0c955e96249b0f9deef1af
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396977"
---
# <a name="imapisessionopenaddressbook"></a>IMAPISession::OpenAddressBook

  
  
**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
Se abre la libreta de direcciones integrada de MAPI, la devolución de un puntero [IAddrBook](iaddrbookimapiprop.md) para aún más el acceso. 
  
```cpp
HRESULT OpenAddressBook(
  ULONG_PTR ulUIParam,
  LPCIID lpInterface,
  ULONG ulFlags,
  LPADRBOOK FAR * lppAdrBook
);
```

## <a name="parameters"></a>Parámetros

 _ulUIParam_
  
> [entrada] Un identificador de la ventana primaria del cuadro de diálogo dirección común y otros relacionados con la muestra.
    
 _lpInterface_
  
> [entrada] Un puntero al identificador de interfaz (IID) que representa la interfaz que se usará para tener acceso a la libreta de direcciones. Si se pasa **null** devuelve un puntero a la interfaz estándar de la libreta de direcciones, [IAddrBook: IMAPIProp](iaddrbookimapiprop.md). 
    
 _ulFlags_
  
> [entrada] Una máscara de bits de indicadores que controla la apertura de la libreta de direcciones. Se puede establecer la marca siguiente:
    
AB_NO_DIALOG 
  
> Suprime la visualización de cuadros de diálogo. Si no está establecido el indicador AB_NO_DIALOG, los proveedores de la libreta de direcciones que contribuyen a la libreta de direcciones integrada pueden pedir al usuario para toda la información necesaria. 
    
 _lppAdrBook_
  
> [out] Un puntero a un puntero a la libreta de direcciones.
    
## <a name="return-value"></a>Valor devuelto

S_OK 
  
> La libreta de direcciones se abrió correctamente.
    
MAPI_W_ERRORS_RETURNED 
  
> La llamada se ha realizado correctamente, pero no se podrían abrir los contenedores de uno o varios proveedores de libreta de direcciones. Cuando se devuelve esta advertencia, la llamada se debe controlarse como correcta. Para probar esta advertencia, utilice la macro **HR_FAILED** . Para obtener más información, vea [Uso de Macros para el control de errores](using-macros-for-error-handling.md).
    
## <a name="remarks"></a>Comentarios

El método **IMAPISession::OpenAddressBook** abre la libreta de direcciones integrada de MAPI, una colección de los contenedores de nivel superior de todos los proveedores de la libreta de direcciones en el perfil. El puntero que se devuelve en el parámetro _lppAdrBook_ aún más proporciona acceso al contenido de la libreta de direcciones. Esto permite que el autor de la llamada realizar tareas como contenedores individuales de apertura, los usuarios de mensajería de buscar y mostrar cuadros de diálogo comunes de dirección. 
  
## <a name="notes-to-callers"></a>Notas para los llamadores

 **OpenAddressBook** devuelve MAPI_W_ERRORS_RETURNED si no puede cargar uno o varios de los proveedores de la libreta de direcciones en el perfil. Este valor es una advertencia, no es un valor de error; controlarla como lo haría S_OK. **OpenAddressBook** siempre devuelve un puntero válido en el parámetro _lppAdrBook_ , independientemente de cómo muchos de los proveedores de la libreta de direcciones no se pudo cargar. Por lo tanto, debe llamar siempre (método [IUnknown:: Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx) ) de la libreta de direcciones en algún momento antes de cerrar la sesión. 
  
Cuando **OpenAddressBook** devuelve MAPI_W_ERRORS_RETURNED, llame a [IMAPISession::GetLastError](imapisession-getlasterror.md) para obtener una estructura [MAPIERROR](mapierror.md) que contiene información acerca de los proveedores con errores. Se devuelve una única estructura **MAPIERROR** que contiene la información proporcionada por todos los proveedores. 
  
## <a name="mfcmapi-reference"></a>Referencia de MFCMAPI

Para obtener un ejemplo de código de MFCMAPI, vea la siguiente tabla.
  
|**File**|**Función**|**Comentario**|
|:-----|:-----|:-----|
|MAPIObjects.cpp  <br/> |CMapiObjects::GetAddrBook  <br/> |MFCMAPI utiliza el método **IMAPISession::OpenAddressBook** para obtener la libreta de direcciones integrada.  <br/> |
   
## <a name="see-also"></a>Vea también



[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)
  
[IMAPISession::GetLastError](imapisession-getlasterror.md)
  
[MAPIERROR](mapierror.md)
  
[IMAPISession: IUnknown](imapisessioniunknown.md)


[MFCMAPI como un ejemplo de c�digo](mfcmapi-as-a-code-sample.md)

