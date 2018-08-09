---
title: IProxyStoreObject
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProxyStoreObject
api_type:
- COM
ms.assetid: 567bede4-39a3-bfb4-af85-ba678e2cf4a5
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: f6566f567c228b6416a64dbd58653561bb592e6d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2018
ms.locfileid: "19817925"
---
# <a name="iproxystoreobject"></a>IProxyStoreObject

  
  
**Hace referencia a**: Outlook 
  
Proporciona un objeto de almacén de protocolo de acceso a mensajes de Internet (IMAP) que ha sido no ajustado y que permite el acceso a los elementos en el archivo de carpetas personales (PST) sin invocar la sincronización y descarga de los elementos.
  
## <a name="quick-info"></a>Información rápida

|||
|:-----|:-----|
|Heredado de:  <br/> |[IUnknown](http://msdn.microsoft.com/en-us/library/ms680509%28v=VS.85%29.aspx) <br/> |
|Proporcionado por:  <br/> |Proveedor de almacén de mensajes  <br/> |
|Identificador de interfaz:  <br/> |**IID_IProxyStoreObject** <br/> |
   
## <a name="vtable-order"></a>Orden vtable

|||
|:-----|:-----|
| *Miembro de marcador de posición*  <br/> | *No se admiten o documentado.*  <br/> |
|[IProxyStoreObject::UnwrapNoRef](iproxystoreobject-unwrapnoref.md) <br/> |Obtiene un puntero a un almacén IMAP no ajustado.  <br/> |
| *Miembro de marcador de posición*  <br/> | *No se admiten o documentado.*  <br/> |
   
## <a name="remarks"></a>Comentarios

Llamar a [IUnknown:: QueryInterface](http://msdn.microsoft.com/en-us/library/ms682521%28v=VS.85%29.aspx) en el almacén de mensajes de origen para obtener la interfaz **IProxyStoreObject** . A continuación, llame a **IProxyStoreObject::UnwrapNoRef** para obtener el objeto de almacén no ajustado. Si **QueryInterface** devuelve el error **MAPI_E_INTERFACE_NOT_SUPPORTED**, el almacén no se ha ajustado. 
  
Debido a que **UnwrapNoRef** no incrementa el recuento de referencias para este nuevo puntero al objeto de almacén no ajustado, después de llamar correctamente a **UnwrapNoRef**, se debe llamar a [IUnknown:: AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28v=VS.85%29.aspx) para mantener el recuento de referencia. 
  
