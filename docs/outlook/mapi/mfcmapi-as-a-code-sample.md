---
title: MFCMAPI como un ejemplo de código
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f98eb842-fe76-4f60-b5e2-d2217d1a66ad
description: 'Última modificación: 09 de marzo de 2015'
ms.openlocfilehash: d72c224db8b3ae4bb6fee3d34f73d9949cda6b8d
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25391664"
---
# <a name="mfcmapi-as-a-code-sample"></a>MFCMAPI como un ejemplo de código
 
**Hace referencia a**: Outlook 2013 | Outlook 2016 
  
En el ejemplo MFCMAPI usa la API de mensajería para proporcionar acceso a los almacenes MAPI a través de una interfaz gráfica de usuario. Después de descargar este ejemplo, puede utilizar los archivos de origen para examinar los casos de uso de ejemplo para muchas de las interfaces MAPI y referencias. Para obtener más información, vea [Interfaces de MAPI](mapi-interfaces.md).
  
|||
|:-----|:-----|
|Plataformas:  <br/> |Microsoft Visual Studio 2008 para compilar para Windows 7, Windows Vista, Windows Server 2008, Windows XP SP2 y Windows Server 2003 SP1  <br/> |
   
### <a name="to-download-mfcmapi"></a>Para descargar MFCMAPI
  
1. En la página [MFCMAPI](https://codeplex.com/MFCMAPI) , haga clic en la ficha de **Código fuente** . 
    
2. **Protecciones recientes**, haga clic en **Descargar** para la compilación más reciente. 
    
3. Lea el contrato de licencia y, a continuación, haga clic en **acepto**.
    
4. En el cuadro de diálogo **Descarga de archivos** , haga clic en **Guardar**. En el cuadro de diálogo **Guardar como** , busque la carpeta en la que desea guardar los archivos de origen y, a continuación, haga clic en **Guardar**.
    
5. En el cuadro de diálogo **Descarga completa** , haga clic en **Abrir la carpeta**. También puede hacer clic en **Cerrar** para cerrar el cuadro de diálogo y busque los archivos de origen comprimidos en la carpeta que guardó en. 
    
6. Haga clic en el **MFCMAPI -\<número de versión\>.zip** de archivo y, a continuación, haga clic en **Extraer todos**. En el cuadro de diálogo que aparece, haga clic en **extraer** para extraer los archivos a la carpeta que se muestra. También puede hacer clic en **Examinar** para seleccionar o crear una carpeta diferente. 
    
7. Ejecute Visual Studio 2008 como administrador.
    
   > [!NOTE]
   > Si su equipo está ejecutando Windows XP, debe haber iniciado sesión como administrador. Si su equipo ejecuta Windows Vista, debe haber iniciado sesión como administrador y debe (ratón) en el icono de Visual Studio 2008 y, a continuación, haga clic en **Ejecutar como administrador**. 
  
8. En Visual Studio 2008, haga clic en **archivo**, elija **Abrir**y, a continuación, haga clic en **Proyecto o solución**.
    
9. Vaya a la ubicación donde guardó el ejemplo, seleccione **MFCMapi.vcproj**y, a continuación, haga clic en **Abrir**.
    
10. On the **Build** menu, click **Build Solution**.
    
11. En el cuadro de diálogo **Guardar archivo como** , haga clic en **Guardar**.
    
### <a name="to-use-mfcmapi-as-a-code-sample"></a>Para usar MFCMAPI como un ejemplo de código
  
En el **Explorador de soluciones**, expanda el proyecto **MFCMapi** y examine los archivos de los nodos de **Archivos de encabezado**, **Archivos de recursos**y **Archivos de origen** para escenarios de programación. 
  
Elija los archivos de origen MFCMAPI para ver ejemplos de programación temas muchos de los métodos en la sección de [Interfaces de MAPI](mapi-interfaces.md) . Por ejemplo, en [IMsgStore::GetReceiveFolderTable](imsgstore-getreceivefoldertable.md) que se indique examine la función `CMsgStoreDlg::OnDisplayReceiveFolderTable` en el archivo MsgStoreDlg.cpp. 
  
## <a name="see-also"></a>Vea también

- [Ejemplos de MAPI](mapi-samples.md)

