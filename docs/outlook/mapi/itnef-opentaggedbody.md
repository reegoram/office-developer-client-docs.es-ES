---
title: ITnefOpenTaggedBody
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITnef.OpenTaggedBody
api_type:
- COM
ms.assetid: 70d5b34c-85b3-4d1f-860e-2838947ba428
description: '�ltima modificaci�n: s�bado, 23 de julio de 2011'
ms.openlocfilehash: ed433dc1fcf2a366d2ece07ac06d4e12558e4aa7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2018
ms.locfileid: "19817983"
---
# <a name="itnefopentaggedbody"></a>ITnef::OpenTaggedBody

  
  
**Se aplica a**: Outlook 
  
Se abre una interfaz de secuencia en el texto de un mensaje de encapsulado.
  
```cpp
HRESULT OpenTaggedBody(
  LPMESSAGE lpMessage,
  ULONG ulFlags,
  LPSTREAM FAR * lppStream
);
```

## <a name="parameters"></a>Sintaxis

 _lpMessage_
  
> [entrada] Un puntero al mensaje que está asociado el objeto stream. Este mensaje no es necesario que sea el mismo mensaje que se pasa en la llamada a la función [OpenTnefStream](opentnefstream.md) o [OpenTnefStreamEx](opentnefstreamex.md) . 
    
 _ulFlags_
  
> [entrada] Una máscara de bits de indicadores que controla cómo se abre la interfaz de la secuencia. Se pueden establecer los siguientes indicadores:
    
MAPI_CREATE 
  
> Si una propiedad no existe en el mensaje actual, se debe crear. Si la propiedad existe, se deben reemplazar los datos actuales de la propiedad con los datos de la secuencia de formato de encapsulación neutro para el transporte (TNEF). Cuando una implementación establece la marca MAPI_CREATE, también debe establecer la marca MAPI_MODIFY.
    
MAPI_MODIFY 
  
> Las solicitudes de permiso de lectura y escritura. La interfaz predeterminada es de sólo lectura. MAPI_MODIFY se debe establecer siempre que se establezca MAPI_CREATE.
    
 _lppStream_
  
> [out] Un puntero a un puntero a un objeto stream que contiene el texto de la propiedad **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) de en el pasado encapsula el mensaje y admita la interfaz [IStream](http://msdn.microsoft.com/library/stg.istream%28Office.15%29.aspx) . 
    
## <a name="return-value"></a>Valor devuelto

S_OK 
  
> La llamada se ha realizado correctamente y devuelve el valor esperado o los valores.
    
## <a name="remarks"></a>Notas

Los proveedores de transporte, los proveedores de almacén de mensajes y las puertas de enlace llaman al método **ITnef::OpenTaggedBody** para abrir una interfaz de secuencia en el texto de un mensaje de encapsulado (es decir, en un TNEF de objetos). 
  
Como parte de su procesamiento, **OpenTaggedBody** inserta o analiza las etiquetas de datos adjuntos que indican la posición de los datos adjuntos o los objetos OLE en el texto del mensaje. Las etiquetas de datos adjuntos se encuentran en el siguiente formato: 
  
 **[[** _nombre de datos adjuntos_ **:** _n_ **en** _nombre del contenedor de datos adjuntos_ **]]**
  
 _nombre de datos adjuntos_ se describe el objeto de datos adjuntos;  _n_ es un número que identifica los datos adjuntos que forma parte de una secuencia, incremento desde el valor que se pasa en el parámetro _lpKey_ del [OpenTnefStream](opentnefstream.md) o la función de [OpenTnefStreamEx](opentnefstreamex.md) ; y _el nombre del contenedor de datos adjuntos_ se describe el componente físico donde reside el objeto de datos adjuntos. 
  
 **OpenTaggedBody** lee el texto del mensaje y se inserta una etiqueta de datos adjuntos siempre que sea un objeto attachment aparecía originalmente en el texto. No se cambia el texto del mensaje original. 
  
Cuando un mensaje que tiene etiquetas se pasa a una secuencia, se eliminan las etiquetas y los objetos de datos adjuntos se reubican en la posición de las etiquetas en el objeto stream.
  
## <a name="see-also"></a>Ver también



[OpenTnefStream](opentnefstream.md)
  
[OpenTnefStreamEx](opentnefstreamex.md)
  
[Propiedad canónico PidTagBody](pidtagbody-canonical-property.md)
  
[ITnef: IUnknown](itnefiunknown.md)
