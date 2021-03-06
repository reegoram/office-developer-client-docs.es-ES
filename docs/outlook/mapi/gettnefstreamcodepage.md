---
title: GetTnefStreamCodepage
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 0f22ccf2-1004-4731-9d68-f66c01b4588b
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: 1e3d384f35726ff28bb47f3d537c8a7a1dda6dce
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25399658"
---
# <a name="gettnefstreamcodepage"></a>GetTnefStreamCodepage

  
  
**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
Determina la página de códigos para una secuencia de formato de encapsulación neutro para el transporte (TNEF).
  
|||
|:-----|:-----|
|Archivo de encabezado:  <br/> |TNEF.h  <br/> |
|Implementado por:  <br/> |MAPI  <br/> |
|Llamado por:  <br/> |Las aplicaciones de cliente y los proveedores de servicios.  <br/> |
   
```cpp
HRESULT GetTnefStreamCodepage(
  LPSTREAM lpStream,
  ULONG FAR * lpulCodepage,
  ULONG FAR * lpulSubCodepage
);
```

## <a name="parameters"></a>Parámetros

 _lpStream_
  
> [entrada] Puntero a una interfaz **IStream** OLE de almacenamiento secuencia objeto proporcionar una fuente para un mensaje de secuencia TNEF. 
    
 _lpulCodepage_
  
> [out] Puntero a la página de códigos de la secuencia.
    
 _lpulSubCodepage_
  
> [out] Puntero a la página subcode del objeto stream.
    
## <a name="return-value"></a>Valor devuelto

 **S_OK**
  
> La llamada se ha realizado correctamente y devuelva el valor esperado o los valores.
    
 **MAPI_E_NOT_ENOUGH_DISK**
  
> Se ha producido un error al leer un atributo en la secuencia TNEF.
    
 **MAPI_E_CORRUPT_DATA**
  
> La secuencia no era una secuencia TNEF o se ha producido un error al leer el atributo attOemCodepage.
    
## <a name="remarks"></a>Comentarios

Use la función **GetTnefStreamCodepage** para leer el atributo **attOemCodepage** de la secuencia TNEF para determinar la página de subcode y página de códigos. Si no se encuentra **attOemCodepage** , **GetTnefStreamCodepage** devuelve una página de códigos de 437 y una página subcode de 0. 
  
## <a name="see-also"></a>Vea también



[attOemCodepage](https://msdn.microsoft.com/library/ee158667%28EXCHG.80%29.aspx)

