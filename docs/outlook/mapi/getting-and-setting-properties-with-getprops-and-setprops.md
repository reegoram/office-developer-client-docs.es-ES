---
title: Obtener y establecer propiedades con GetProps y SetProps
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 309d2b3d-dc71-4222-b293-4bfc467b5429
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: 7d11f69c6da8560f5879ebc38498d852486bed8b
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25395010"
---
# <a name="getting-and-setting-properties-with-getprops-and-setprops"></a>Obtener y establecer propiedades con GetProps y SetProps
 
**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
Siempre que sea posible, vuelva a intentar recuperar o modificar una propiedad con los métodos [IMAPIProp::GetProps](imapiprop-getprops.md) y [IMAPIProp::SetProps](imapiprop-setprops.md) . A menos que la propiedad con que trabaja es muy grande, estos métodos deben ser adecuados. La otra alternativa consiste en leer o escribir en un objeto stream con la interfaz [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) . Secuencias de pueden controlar correctamente las propiedades muy grandes, pero son un mayor consumo de recursos debido a que requieren que las bibliotecas COM. Use la interfaz **IStream** sólo después de que se produce un error en la llamada a **IMAPIProp::GetProps** o **IMAPIProp::SetProps** . 
  

