---
title: Trabajar con vistas usando el modelo de objetos de InfoPath 2003
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
keywords:
- infopath 2003-compatible form templates, views,views [InfoPath 2007], InfoPath 2003-compatible form templates
localization_priority: Normal
ms.assetid: feb1bfcb-1cb1-4d5c-bc84-df86a33a5934
description: Cuando se trabaja con una plantilla de formulario de InfoPath, es posible escribir código para tener acceso a las vistas del formulario y, a continuación, efectuar diversas acciones con los datos que contienen. El modelo de objetos compatible con InfoPath 2003 admite el acceso a las vistas de un formulario mediante el uso de los miembros de la interfaz ViewObject .
ms.openlocfilehash: 1cbc472993ff18b26f31e3bc28b12a75e559644a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2018
ms.locfileid: "19815884"
---
# <a name="work-with-views-using-the-infopath-2003-object-model"></a>Trabajar con vistas usando el modelo de objetos de InfoPath 2003

Cuando se trabaja con una plantilla de formulario de InfoPath, es posible escribir código para tener acceso a las vistas del formulario y, a continuación, efectuar diversas acciones con los datos que contienen. El modelo de objetos compatible con InfoPath 2003 admite el acceso a las vistas de un formulario mediante el uso de los miembros de la interfaz [ViewObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewObject.aspx) . 
  
## <a name="overview-of-the-viewobject-interface"></a>Información general sobre la interfaz ViewObject

La interfaz [ViewObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewObject.aspx) proporciona el método y las propiedades siguientes que los desarrolladores de formularios pueden utilizar para interactuar con una vista de InfoPath. 
  
> [!NOTE]
> [!NOTA] Los métodos y las propiedades de la interfaz [ViewObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewObject.aspx) no están disponibles durante el evento [OnLoad](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnLoad.aspx) . 
  
|**Nombre**|**Descripción**|
|:-----|:-----|
|Método [DisableAutoUpdate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.DisableAutoUpdate.aspx)  <br/> |Deshabilita la sincronización entre Document Object Model (DOM) XML y la vista.  <br/> |
|Método [EnableAutoUpdate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.EnableAutoUpdate.aspx)  <br/> |Habilita la sincronización entre el XML DOM y la vista.  <br/> |
|Método [ExecuteAction](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.ExecuteAction.aspx)  <br/> |Ejecuta una acción de edición de InfoPath.  <br/> |
|Método [Export](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.Export.aspx)  <br/> |Exporta la vista como archivo del formato especificado.  <br/> |
|[ForceUpdate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.ForceUpdate.aspx) (método)  <br/> |Sincroniza el XML DOM y la vista.  <br/> |
|Método [GetContextNodes](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.GetContextNodes.aspx)  <br/> |Devuelve una referencia a la interfaz [XMLNodesCollection](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XMLNodesCollection.aspx) , basándose en el contexto de vista y de nodo XML especificado o en la selección actual en la vista.  <br/> |
|Método [GetSelectedNodes](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.GetSelectedNodes.aspx)  <br/> |Devuelve una referencia a la interfaz **XMLNodesCollection**, basándose en la selección actual de la vista.  <br/> |
|[SelectNodes](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.SelectNodes.aspx) (método)  <br/> |Selecciona un rango de nodos XML de la vista.  <br/> |
|Método [SelectText](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.SelectText.aspx)  <br/> |Selecciona el texto contenido en el nodo XML especificado de la vista.  <br/> |
|Método [SwitchView](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.SwitchView.aspx)  <br/> |Cambia el formulario de InfoPath a la vista especificada  <br/> |
|[Nombre](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.Name.aspx) (propiedad)  <br/> |Devuelve un valor de cadena que indica el nombre de la vista actual.  <br/> |
|[Ventana](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.Window.aspx) (propiedad)  <br/> |Devuelve una referencia a la interfaz de [WindowObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.WindowObject.aspx) que tiene acceso a la **ventana** asociada con la vista.  <br/> |
   
> [!NOTE]
> [!NOTA] El modelo de objetos compatible con InfoPath 2003 también proporciona la interfaz [ViewInfosCollection](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewInfosCollection.aspx) , que se puede utilizar para obtener información sobre todas las vistas implementadas en un formulario. 
  
## <a name="using-the-viewobject-interface"></a>Uso de la interfaz ViewObject

El acceso a la interfaz [ViewObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewObject.aspx) se obtiene a través de la propiedad [View](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.View.aspx) de la interfaz [XDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XDocument.aspx) (a la que se obtiene acceso a través de la variable  `thisXDocument` que se inicializa en el método  `_Startup` de la clase de código del formulario). Por ejemplo, el siguiente ejemplo de código muestra cómo utilizar el método [Alert](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.Alert.aspx) de la interfaz [UIObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UIObject.aspx) para mostrar un cuadro de mensaje con el nombre de la vista actual asociada al documento XML subyacente del formulario. 
  
```cs
thisXDocument.UI.Alert("Current view name: " + 
   thisXDocument.View.Name);
```

```vb
thisXDocument.UI.Alert("Current view name: " &amp; _
   thisXDocument.View.Name)
```

Todos los formularios de InfoPath contienen al menos una vista predeterminada; sin embargo, InfoPath admite también la creación de varias vistas del documento XML subyacente de un formulario. Cuando un formulario tiene varias vistas, el objeto **View** se puede utilizar para trabajar con la que esté activa. Es posible cambiar mediante programación la vista activa utilizando el método **SwitchView** del objeto **View**, como demuestra el ejemplo de código siguiente: 
  
```cs
thisXDocument.View.SwitchView("MySecondView");
```

```vb
thisXDocument.View.SwitchView("MySecondView")
```

El ejemplo anterior (cambiar a una vista) sólo funcionará una vez abierto el formulario. Para establecer una vista predeterminada durante el evento **OnLoad**, utilice la propiedad [IsDefault](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewInfo.IsDefault.aspx) de la interfaz [ViewInfoObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewInfoObject.aspx) , como se muestra en el ejemplo siguiente: 
  
```cs
thisXDocument.ViewInfos["MyDefaultView"].IsDefault = true;
```

```vb
thisXDocument.ViewInfos("MyDefaultView").IsDefault = True
```


