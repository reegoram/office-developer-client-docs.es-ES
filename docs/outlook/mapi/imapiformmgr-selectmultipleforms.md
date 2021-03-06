---
title: IMAPIFormMgrSelectMultipleForms
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormMgr.SelectMultipleForms
api_type:
- COM
ms.assetid: 172f8f53-b837-4286-9236-3f72806d7f1f
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: b974b733c24e61cb256ac0cf7b377d5630966fdf
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579294"
---
# <a name="imapiformmgrselectmultipleforms"></a>IMAPIFormMgr::SelectMultipleForms

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Presenta un cuadro de diálogo que permite al usuario seleccionar varios formularios y devuelve una matriz de formulario objetos de información que se describen dichos formularios.
  
```cpp
HRESULT SelectMultipleForms(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPCSTR pszTitle,
  LPMAPIFOLDER pfld,
  LPMAPIFORMINFOARRAY pfrminfoarray,
  LPMAPIFORMINFOARRAY FAR * ppfrminfoarray
);
```

## <a name="parameters"></a>Parámetros

 _ulUIParam_
  
> [entrada] Identificador de la ventana principal del cuadro de diálogo que se muestra. 
    
 _ulFlags_
  
> [entrada] Una máscara de bits de indicadores que controla el tipo de las cadenas que se pasan en. Se puede establecer la marca siguiente:
    
MAPI_UNICODE. 
  
> Las cadenas que se pasan en están en formato Unicode. Si no está establecido el indicador MAPI_UNICODE., las cadenas están en formato ANSI.
    
 _pszTitle_
  
> [entrada] Un puntero a una cadena que contiene el título del cuadro de diálogo. Si el parámetro _pszTitle_ es NULL, el proveedor de la biblioteca de formulario que proporciona los formularios proporciona un título predeterminado. 
    
 _pfld_
  
> [entrada] Un puntero a la carpeta desde la que se va a seleccionar los formularios. Si el parámetro _pfld_ es NULL, se seleccionan los formularios desde el contenedor de forma local, el personal o la organización. 
    
 _pfrminfoarray_
  
> [entrada] Un puntero a una matriz de objetos de información de formulario que se preseleccionado para el usuario.
    
 _ppfrminfoarray_
  
> [out] Un puntero a un puntero a la matriz devuelta de objetos de información del formulario.
    
## <a name="return-value"></a>Valor devuelto

S_OK 
  
> La llamada se ha realizado correctamente y devuelve el valor esperado o los valores.
    
MAPI_E_BAD_CHARWIDTH 
  
> Se ha establecido el indicador MAPI_UNICODE y la implementación no es compatible con Unicode, o bien, no se ha establecido MAPI_UNICODE y la implementación admite sólo Unicode.
    
MAPI_E_USER_CANCEL 
  
> El usuario canceló la operación, normalmente haciendo clic en el botón **Cancelar** en el cuadro de diálogo. 
    
## <a name="remarks"></a>Comentarios

Visores de formulario llamar al método **IMAPIFormMgr::SelectMultipleForms** a presenta primero un cuadro de diálogo que permite al usuario seleccionar varios formularios y, a continuación, para recuperar una matriz de formulario de información de los objetos que se describen los formularios seleccionados. El cuadro de diálogo **SelectMultipleForms** muestra todos los formularios, independientemente de si están ocultos (es decir, si sus propiedades ocultas son claros). 
  
## <a name="notes-to-implementers"></a>Notas para los implementadores

Si un visor de formulario, pasa el indicador MAPI_UNICODE el parámetro _ulFlags_ , todas las cadenas son cadenas Unicode. Proveedores de biblioteca de formulario que no admiten cadenas Unicode deben devolver MAPI_E_BAD_CHARWIDTH si se pasa MAPI_UNICODE.. 
  
## <a name="see-also"></a>Recursos adicionales



[IMAPIFormMgr : IUnknown](imapiformmgriunknown.md)

