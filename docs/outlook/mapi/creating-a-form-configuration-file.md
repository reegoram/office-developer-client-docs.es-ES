---
title: Crear un archivo de configuración de formulario
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: aaf3b33d-ad2d-4ef8-847f-1ab1eaf08706
description: 'Última modificación: 23 de julio de 2011'
ms.openlocfilehash: d8159d93aef020d7c9c1b56be4cf6256f80b8aa3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584176"
---
# <a name="creating-a-form-configuration-file"></a>Crear un archivo de configuración de formulario

  
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Un archivo de configuración de formulario proporciona información acerca de un formulario para el Administrador de formulario que se usa y a las aplicaciones cliente. Un archivo de configuración de formulario contiene una especificación de una amplia para un formulario, incluidas las propiedades publicadas por el formulario para su uso por parte de mensajería los clientes, los verbos de implementada por el formulario y las plataformas compatibles con el formulario.
  
Un archivo de configuración de formulario es un archivo con una extensión .cfg y tiene un formato similar a un archivo de inicialización de Windows. Es un archivo de texto sin formato con un número de secciones. Cada sección comienza con un nombre de sección, entre corchetes. Cada sección contiene una o varias líneas que definen los valores y opciones relevantes para esa sección. Los valores de tengan uno de los siguientes tipos:
  
- String
    
- Cadena que se muestra
    
- Cadena de plataforma
    
- Nombre de ruta de acceso
    
- Entero
    
- GUID
    
Para obtener más información acerca de las secciones de un archivo .cfg, vea el [Archivo de formato de formulario de los archivos de configuración](file-format-of-form-configuration-files.md).
  
## <a name="see-also"></a>Recursos adicionales



[Desarrollar servidores de formulario MAPI](developing-mapi-form-servers.md)

