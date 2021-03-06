---
title: Apagar un proveedor de almacén de archivos PST ajustado
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 0c9e5917-1b96-323d-bf8b-1d3aa1f677d0
description: 'Última modificación: 02 de julio de 2012'
ms.openlocfilehash: 43a65548bedc1729ff2bcb62bc3df78d2408bf12
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571748"
---
# <a name="shutting-down-a-wrapped-pst-store-provider"></a>Apagar un proveedor de almacén de archivos PST ajustado

 
  
**Se aplica a**: Outlook 2013 | Outlook 2016 
  
Cuando termine de usar un proveedor de almacén de archivo (.pst) de carpetas personales ajustado, debe cerrar correctamente el proveedor de almacén de archivos PST ajustado. Para obtener más información acerca de cómo utilizar el proveedor de almacén de archivos PST ajustado, vea [uso de un proveedor de almacén de archivos PST ajustado](using-a-wrapped-pst-store-provider.md).
  
Para cerrar un proveedor de almacén de archivos PST ajustado, debe llamar a la función **[IMSProvider::Shutdown](imsprovider-shutdown.md)** . Esta funciones se cierra el proveedor de almacenamiento de archivos PST ajustado de forma ordenada. 
  
En este tema, se muestra la función **IMSProvider::Shutdown** mediante el uso de un ejemplo de código desde el proveedor de almacén de archivos PST ajustado de ejemplo. En el ejemplo se implementa un proveedor de PST ajustado que está pensado para usarse junto con la API de replicación. Para obtener más información sobre cómo descargar e instalar al proveedor de almacén de archivos PST ajustado de ejemplo, vea [instalar el proveedor de almacén de archivos PST ajustado de ejemplo](installing-the-sample-wrapped-pst-store-provider.md). Para obtener más información acerca de la API de replicación, vea [Acerca de la API de replicación](about-the-replication-api.md).
  
## <a name="shut-down-routine"></a>Apague la rutina

La cola MAPI llama a la función **[IMSProvider::Shutdown](imsprovider-shutdown.md)** justo antes de que libera el proveedor de almacén de archivos PST ajustado para que el proveedor de almacén de archivos PST ajustado puede apagar correctamente. La función termina todos los objetos de sesión asociados con el proveedor de almacén de archivos PST ajustado. 
  
## <a name="cmsprovidershutdown-example"></a>Ejemplo de CMSProvider::ShutDown()

```cpp
STDMETHODIMP CMSProvider::Shutdown(ULONG * pulFlags) 
{ 
    HRESULT hRes = S_OK; 
    Log(true,"CMSProvider::Shutdown\n"); 
    hRes =m_pPSTMS->Shutdown(pulFlags); 
    Log(true,"CMSProvider::Shutdown returned: 0x%08X\n", hRes); 
    return hRes ;  
}
```

## <a name="see-also"></a>Recursos adicionales



[Información sobre el proveedor de almacén de archivos PST ajustado de muestra](about-the-sample-wrapped-pst-store-provider.md)
  
[Instalar la muestra de proveedor de almacén de archivos PST ajustado](installing-the-sample-wrapped-pst-store-provider.md)
  
[Inicializar un proveedor de almacén de archivos PST ajustado](initializing-a-wrapped-pst-store-provider.md)
  
[Iniciar sesión en un proveedor de almacén de archivos PST ajustado](logging-on-to-a-wrapped-pst-store-provider.md)
  
[Usar un proveedor de almacén de archivos PST ajustado](using-a-wrapped-pst-store-provider.md)

