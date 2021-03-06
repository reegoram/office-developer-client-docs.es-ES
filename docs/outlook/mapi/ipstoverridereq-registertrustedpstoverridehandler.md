---
title: IPSTOVERRIDEREQRegisterTrustedPSTOverrideHandler
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPSTOVERRIDEREQ.RegisterTrustedPSTOverrideHandler
api_type:
- COM
ms.assetid: 4a73c77c-7e32-4302-bffe-a1ea13574731
description: 'Última modificación: 24 de febrero de 2013'
ms.openlocfilehash: acc0986dd80b549b0cb2b941a6937d47a4a959fe
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25393876"
---
# <a name="ipstoverridereqregistertrustedpstoverridehandler"></a>IPSTOVERRIDEREQ::RegisterTrustedPSTOverrideHandler

 
  
**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
Inicia el procedimiento de desbloqueo para un archivo de carpetas personales (.pst).
  
```cpp
HRESULT RegisterTrustedPSTOverrideHandler (
  LPCWSTR pwzDllPath, 
  LPVOID pvClientData
); 

```

## <a name="parameters"></a>Parámetros

 _pwzDllPath_
  
> [entrada] Un puntero a la ruta de acceso de una biblioteca de vínculos dinámicos (DLL) de otro fabricante.
    
 _pvClientData_
  
> [entrada] Un puntero a datos de cliente, que se pasa por el proveedor de PST en llamadas posteriores a la función de archivo DLL HrTrustedPSTOverrideHandlerCallback. Estos datos de cliente pueden usar el archivo DLL para ayudarle a comprobar si se debe desbloquear el archivo PST.
    
## <a name="return-value"></a>Valor devuelto

S_OK
  
> La llamada a la función fue correcta.
    
## <a name="remarks"></a>Comentarios

El archivo DLL especificado por el parámetro wzDllPath debe haber iniciado sesión con un certificado digital. El archivo DLL también debe exportar una función con la siguiente firma.
  
```
extern "C" HRESULT __cdecl HrTrustedPSTOverrideHandlerCallback(IMsgStore *pmstore, IUnknown *pOverride, LPVOID pvClientData)
```

Esta función se llamará con un puntero al objeto IMsgStore para los archivos PST, un puntero a un objeto IUnknown que implementa la interfaz IPSTOVERRIDE1 y un puntero a los datos proporcionados originalmente a través de pvClientData.
  
Para obtener más información, vea [cómo implementar un controlador de reemplazo de PST para que omita la directiva de PSTDisableGrow en Outlook 2007](https://support.microsoft.com/kb/956070).
  
## <a name="see-also"></a>Vea también



[IPSTOVERRIDE1 : IUnknown](ipstoverride1iunknown.md)
  
[IPSTOVERRIDEREQ : IUnknown](ipstoverridereqiunknown.md)

