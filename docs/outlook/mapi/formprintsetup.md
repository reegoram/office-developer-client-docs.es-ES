---
title: FORMPRINTSETUP
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FORMPRINTSETUP
api_type:
- COM
ms.assetid: 6e82fe94-47bd-4a25-b25b-0ab6fe2db274
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: c2b9176e21341ef28e6f0bc007757b097a05daee
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25386575"
---
# <a name="formprintsetup"></a>FORMPRINTSETUP

  
  
**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
Se describe la información de configuración de impresión para el objeto de formulario. 
  
|||
|:-----|:-----|
|Archivo de encabezado:  <br/> |MAPIForm.h  <br/> |
   
```cpp
typedef struct
{
  ULONG ulFlags;
  HDEVMODE hDevMode;
  HDEVNAMES hDevNames;
  ULONG ulFirstPageNumber;
  ULONG ulFPrintAttachments;
} FORMPRINTSETUP, FAR * LPFORMPRINTSETUP;

```

## <a name="members"></a>Members

 **ulFlags**
  
> Máscara de bits de indicadores que controla el tipo de las cadenas. Se puede usar la siguiente marca:
    
MAPI_UNICODE. 
  
> Las cadenas están en formato Unicode. Si no está establecido el indicador MAPI_UNICODE., las cadenas están en formato ANSI.
    
 **hDevmode**
  
> Controlar en el modo de la impresora.
    
 **hDevnames**
  
> Identificador de la ruta de acceso de la impresora.
    
 **ulFirstPageNumber**
  
> Número de página de la primera página que debe imprimirse.
    
 **ulFPrintAttachments**
  
> Marca que indica si hay datos adjuntos que se va a imprimir. Si hay datos adjuntos para imprimir, el miembro **ulFPrintAttachments** está establecido en 1. Si no hay ningún datos adjuntos para imprimir, se establece en 0. 
    
## <a name="remarks"></a>Comentarios

La estructura **FORMPRINTSETUP** se usa para describir la información de configuración de impresión de un objeto de formulario. Las implementaciones de [IMAPIViewContext::GetPrintSetup](imapiviewcontext-getprintsetup.md) rellene la estructura **FORMPRINTSETUP** y devuelven en el contenido del parámetro de salida _lppFormPrintSetup_ de **GetPrintSetup**.
  
Si el indicador MAPI_UNICODE se pasa en el parámetro _ulFlags_ de **GetPrintSetup**, las cadenas que se hace referencia a los miembros **hDevmode** y **hDevNames no** deben estar en formato Unicode. De lo contrario, las cadenas deberían estar en formato ANSI. 
  
Visores de formulario implementar **IMAPIViewContext** deben asignar la estructura **FORMPRINTSETUP** mediante la función de asignador MAPI [MAPIAllocateBuffer](mapiallocatebuffer.md), pero asignar a los miembros individuales, **hDevMode** y **hDevNames**, con la función de Windows [GlobalAlloc](https://go.microsoft.com/fwlink/?LinkId=132110). La versión de memoria se administra de forma similar. Los miembros **hDevMode** y **hDevNames no** se deben liberar mediante la función de Windows [GlobalFree](https://go.microsoft.com/fwlink/?LinkId=132108) mientras que la estructura **FORMPRINTSETUP** se debe liberar con la función [MAPIFreeBuffer](mapifreebuffer.md) . 
  
## <a name="see-also"></a>Vea también



[IMAPIViewContext::GetPrintSetup](imapiviewcontext-getprintsetup.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[MAPIAllocateBuffer](mapiallocatebuffer.md)


[Estructuras MAPI](mapi-structures.md)

