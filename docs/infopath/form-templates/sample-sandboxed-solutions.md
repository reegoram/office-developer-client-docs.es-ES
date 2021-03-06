---
title: Soluciones de espacio aislado de ejemplo
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 415fa0fa-b7b7-4acb-a437-f54c34064004
description: En este tema, se presentan dos ejemplos que muestran el tipo de código que puede escribir en un solución de espacio aislado de InfoPath y cómo publicar la plantilla de formulario.
ms.openlocfilehash: b0874e34d843850df55eee87d689ce0d01112635
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2018
ms.locfileid: "19815968"
---
# <a name="sample-sandboxed-solutions"></a>Soluciones de espacio aislado de ejemplo

Los formularios de InfoPath con código administrado se pueden publicar en la infraestructura solución de espacio aislado de SharePoint desde InfoPath Designer. En este tema, se presentan dos ejemplos que muestran el tipo de código que puede escribir en un solución de espacio aislado de InfoPath y cómo publicar la plantilla de formulario.
  
## <a name="example-1-sorting-data-in-an-order-form"></a>En el ejemplo 1: Ordenar datos en un formulario de pedido

Una tarea útil que puede realizar con código en un formulario de InfoPath es ordenar datos en una tabla de repetición. Para esto, el código reordena los nodos en el documento XML subyacente que se muestra en el formulario de InfoPath. A pesar de que el caso descrito en este tema está destinado a su publicación directamente desde InfoPath como un solución de espacio aislado, también se puede implementar como una plantilla de formulario aprobada por administrador.
  
Antes de comenzar, asegúrese de que se cumplen los siguientes requisitos.
  
- Es administrador de colección de sitios en el sitio de SharePoint Server 2010 o SharePoint Foundation 2010 en donde desea publicar el formulario.
    
- Consulte con el administrador de la granja de servidores para asegurarse de que el Servicio de código de espacio aislado de Microsoft SharePoint Foundation esté en uso en el servidor. Para más información, vea [Publicar formularios con código](publishing-forms-with-code.md).
    
- El lenguaje de programación que seleccionó para la plantilla de formulario es **C#** o **Visual Basic** sin ningún nombre de versión anterior que lo siga. Las versiones compatibles con InfoPath 2007 y InfoPath 2003 de los lenguajes de programación y los modelos de objetos no se admiten para soluciones de espacio aislado. Para obtener más información acerca de cómo especificar el lenguaje de programación, vea [desarrollar con Visual Studio](how-to-develop-with-visual-studio.md).
    
Realice los siguientes pasos para crear una plantilla de formulario que ordene los datos en un control de **Tabla de repetición** en el formulario. 
  
### <a name="to-create-a-form-template-that-programmatically-sorts-data-in-the-form"></a>Para crear una plantilla de formulario que ordena datos mediante programación en el formulario

1. Cree una nueva plantilla de formulario en el diseñador de InfoPath y agregue un control de **Tabla de repetición** al formulario. El código de muestra para este ejemplo ordena las filas basadas en la primera columna de la tabla, pero puede modificar fácilmente el código para trabajar con cualquier columna. 
    
2. Agregue un control **Botón** al formulario. El código para ordenar la tabla se agregará en el controlador de eventos para el evento **Clicked** del botón, pero también puede usar otro evento para este propósito. 
    
3. Seleccione el botón, haga clic en la pestaña **Propiedades** y, a continuación, en **Código personalizado**. Si el formulario no se guardó aún, se le solicitará hacerlo, y el Editor de código se abrirá con el cursor en el controlador de eventos del botón.
    
4. Pegue el siguiente código en el controlador de eventos del botón. El código coloca los elementos de la primera columna en una matriz, ordena la matriz y vuelve a ordenar la tabla basada en la matriz ordenada. Este código asume que los datos que se ordenan son datos de cadena.
    
   ```cs
    // Put the elements from the first column into an array.
    XPathNavigator root = this.CreateNavigator();
        
    // Create a node iterator which contains only the values that you want to sort.
    // For this form, the entire table is in "group1", each row is a "group2"
    // and the rows are "field1", "field2" and "field3" respectively.
    XPathNodeIterator nodeIterator = root.Select(
        "/my:myFields/my:group1/my:group2/my:field1", this.NamespaceManager);
        
    // Create arrays to use for sorting.
    string[] sortArrayWords = new string[nodeIterator.Count + 1];
    int[] sortArrayKeys = new int[nodeIterator.Count + 1];
    int arrayPosition = 1;
        
    // Populate the arrays for sorting.
    while (nodeIterator.MoveNext()) 
    {
        // Loop until there are no more elements
        sortArrayWords[arrayPosition] = nodeIterator.Current.Value;
        sortArrayKeys[arrayPosition] = arrayPosition;
        arrayPosition += 1;
    }
        
    // Sort the array.
    Array.Sort(sortArrayWords, sortArrayKeys);
    arrayPosition = 0;
        
    // Create new XML to update the table.
    string newTableXML = "";
    // Iterate through the sorted array of keys.
    for (int i = 1; i <= sortArrayWords.Length - 1; i++) 
    {
        nodeIterator = root.Select(
            "/my:myFields/my:group1/my:group2", this.NamespaceManager);
            
        // Go to the right position in the table.
        for (int j = 1; j <= sortArrayKeys[i]; j++) 
        {
            nodeIterator.MoveNext();
        }
            
        // Add the row to the XML.
        newTableXML += nodeIterator.Current.OuterXml;
    }
        
    // Set the table to use the new XML.
    root.SelectSingleNode(
        "/my:myFields/my:group1", this.NamespaceManager).InnerXml = newTableXML;
    
   ```

   ```vb
    ' Put the elements from the first column into an array.
    Dim root As XPathNavigator = Me.CreateNavigator
    ' Create a node iterator which contains only the values that you want to sort
    ' For this form, the entire table is in "group1",
    ' each row is a "group2"
    ' and the rows are "field1", "field2" and "field3" respectively.
    Dim nodeIterator As XPathNodeIterator = root.Select( _
        "/my:myFields/my:group1/my:group2/my:field1", Me.NamespaceManager)
    ' Create arrays to use for sorting.
    Dim sortArrayWords(nodeIterator.Count) As String
    Dim sortArrayKeys(nodeIterator.Count) As Integer
    Dim arrayPosition As Integer = 1
    ' Populate the arrays for sorting.
    While nodeIterator.MoveNext() ' Loop until there are no more elements
        sortArrayWords(arrayPosition) = nodeIterator.Current.Value
        sortArrayKeys(arrayPosition) = arrayPosition
        arrayPosition += 1
    End While
    ' Sort the array.
    Array.Sort(sortArrayWords, sortArrayKeys)
    arrayPosition = 0
    ' Create new XML to update the table.
    Dim newTableXML As String = ""
    ' Iterate through the sorted array of keys.
    For i As Integer = 1 To sortArrayWords.Length - 1
        nodeIterator = root.Select( _
            "/my:myFields/my:group1/my:group2", Me.NamespaceManager)
        ' Go to the right position in the table.
        For j As Integer = 1 To sortArrayKeys(i)
        nodeIterator.MoveNext()
        Next
    ' Add the row to the XML.
    newTableXML &amp;= nodeIterator.Current.OuterXml
    Next
    ' Set the table to use the new XML.
    root.SelectSingleNode("/my:myFields/my:group1", _
        Me.NamespaceManager).InnerXml = newTableXML
   ```

5. Publicar el formulario mediante el uso de los siguientes pasos:
    
    1. Haga clic en **SharePoint Server**, en la ficha **Publicar**, en Backstage. 
        
    2. Escriba la dirección URL del sitio de SharePoint en donde desea publicar el formulario y, a continuación, haga clic en **Siguiente**. 
        
       > [!IMPORTANT]
       > [!IMPORTANTE] Debe ser administrador de una colección de sitios en este sitio para publicar esta plantilla de formulario como un solución de espacio aislado. 
    
    3. Seleccione **Biblioteca de formularios** y, a continuación, haga clic en **Siguiente**.
        
    4. Seleccione **Crear una nueva biblioteca de formularios** y, a continuación, haga clic en **Siguiente**.
        
    5. Escriba el nombre y las descripciones de la biblioteca de formularios y, a continuación, haga clic en **Siguiente**.
        
    6. Haga clic en **Publicar**.
    
## <a name="example-2-managing-vendors-in-a-sharepoint-list"></a>Ejemplo 2: Administrar proveedores en una lista de SharePoint

Este ejemplo implica la programación con el modelo de objetos de Microsoft SharePoint Foundation 2010. Para esto, debe establecer una referencia al ensamblado de Microsoft.SharePoint.dll, que está instalado con una copia con licencia de SharePoint Server 2010.
  
Microsoft.SharePoint.Server.dll está instalado en C:\Archivos de programa\Archivos comunes\Microsoft Shared\Web Server Extensions\14\ISAPI de manera predeterminada. Este archivo DLL debe incluirse en los proyectos cuando programe en un modelo de objetos de SharePoint. Para establecer una referencia a Microsoft.SharePoint.dll en un proyecto de Visual Studio 2012, abra el **Editor de código** y haga clic en **Agregar referencia** en el menú **Herramientas**. En el cuadro de diálogo **Agregar referencia**, haga clic en la pestaña **Explorar**, especifique la ubicación del archivo Microsoft.SharePoint.dll y haga clic en **Aceptar**. El archivo Microsoft.SharePoint.dll se copiará en el directorio del proyecto para que pueda usar los miembros del modelo de objetos de SharePoint Foundation 2010 en la solución InfoPath.
  
### <a name="designing-the-form-and-developing-the-code"></a>Diseñar el formulario y desarrollar el código

Del código de un formulario de InfoPath, puede usar el modelo de objetos de SharePoint para crear elementos en listas de búsqueda. Esto resulta útil cuando rellena el cuadro desplegable de una lista de SharePoint y desea agregar nuevos valores a ella sin crear un formulario independiente. En este ejemplo, se usa un cuadro combinado para mostrar todos los valores que están actualmente en la lista y crea lógica de programación para agregar el valor a la lista si aún no existe.
  
### <a name="to-create-a-form-template-that-can-add-new-items-to-a-combo-box-based-on-a-sharepoint-list"></a>Para crear una plantilla de formulario que pueda agregar nuevos elementos a un cuadro combinado basado en una lista de SharePoint

1. Cree una lista personalizada simple en un servidor de SharePoint Server 2010 y cambie el nombre a MiLista. El ejemplo siguiente usa un **Cuadro combinado** vinculado al campo **Título** para esta lista. 
    
2. Cree un nuevo **Formulario en blanco** en InfoPath Designer, inserte un control de **Cuadro combinado** en el formulario y cambie el nombre del campo enlazado al cuadro combinado en myCombo.
    
3. Crear la conexión de datos a la lista que se usará para rellenar el cuadro combinado mediante el uso de los siguientes pasos:
    
    1. En la ficha **Datos**, haga clic en el botón **Desde la lista de SharePoint** en el grupo **Obtener datos externos**. 
        
    2. Escriba la dirección URL del sitio que contiene la lista y, a continuación, haga clic en **Siguiente**.
        
    3. Seleccione la lista y, a continuación, haga clic en **Siguiente**.
        
    4. Seleccione los campos que desea incluir, para este ejemplo, seleccione Título e Id.. Título contiene los valores de búsqueda. Haga clic en **Siguiente**.
        
    5. Haga clic en **Siguiente** en la pantalla a continuación. 
        
    6. Denomine la conexión de datos LookupList y haga clic en **Finalizar**.
    
4. Rellenar los valores en el cuadro combinado de la lista mediante el uso de los siguientes pasos:
    
    1. Seleccione el cuadro combinado que creó en el paso 1.
        
    2. Haga clic en **Editar opciones** en la ficha **Propiedades de herramientas de control** de la cinta de opciones. 
        
    3. Seleccione **Obtener opciones desde un origen de datos externo**.
        
    4. Asegúrese de que el **Origen de datos** esté establecido en la conexión de datos que creó en el paso 2. 
        
    5. Establezca el valor y el nombre para mostrar en Título.
        
    6. En la pestaña **Formularios de explorador**, seleccione **Siempre** en **Configuración de devolución** y haga clic en **Aceptar** para cerrar el cuadro de diálogo de propiedades. 
    
5. Asegúrese de que el cuadro combinado esté seleccionado y haga clic en **Evento cambiado** en la pestaña **Programador** de la cinta. 
    
    Si el formulario aún no se ha guardado, se le pedirá que lo haga. A continuación, se abrirá la ventana del editor de código con el cursor en el controlador de eventos  `myCombo_Changed`. 
    
6. Agregue una referencia al ensamblado Microsoft.SharePoint.dll como se describió anteriormente en este tema. Para obtener más información sobre cómo hacer referencia del ensamblado de Microsoft.SharePoint, vea [Miembros del modelo de objetos de SharePoint de uso](how-to-use-sharepoint-object-model-members.md).
    
7. Pegue el código siguiente en el controlador de eventos  `myCombo_Changed`. 
    
   ```cs
    // Use InfoPath OM's ServerInfo.SharePointSiteUrl property to programmatically
    // specify the site where the form is published.
    using (SPSite FormSite = new SPSite(ServerInfo.SharePointSiteUrl.ToString()))
    {
        using (SPWeb FormWeb = FormSite.OpenWeb())
        {
            // Get the SharePoint list.
            SPList LookupList = FormWeb.Lists["MyList"];
            // Query for the item.
            SPQuery MyQuery = new SPQuery();
            // "Title" is the field (column) to search in the SharePoint list.
            // /my:myFields/my:myCombo is the xpath to the field bound to the Combo Box in the form.
            MyQuery.Query = "<Where><Eq><FieldRef Name='Title' /><Value Type='Text'>" + 
                GetDomValue("/my:myFields/my:myCombo") + "</Value></Eq></Where>";
            SPListItemCollection ReturnedItems = LookupList.GetItems(MyQuery);
            // Add the item to the SharePoint list if no items were returned in the query.
            if (ReturnedItems.Count == 0)
            {
                SPListItem NewItem = LookupList.Items.Add();
                // Set the value of the Title field in the list to the value in Combo Box on the form.
                NewItem["Title"] = GetDomValue("/my:myFields/my:myCombo");
                // Set AllowUnsafeUpdates to 'true' to temporarily allow updates to the database.
                FormWeb.AllowUnsafeUpdates = true;
                NewItem.Update();
                // Set AllowUnsafeUpdates back to 'false' to prevent further updates to the database.
                FormWeb.AllowUnsafeUpdates = false;
            }
        }
    }
   ```

   ```vb
    ' Use InfoPath OM's ServerInfo.SharePointSiteUrl property to specify the site where the form is published.
    Using FormSite As New SPSite(ServerInfo.SharePointSiteUrl.ToString())
        Using FormWeb As SPWeb = FormSite.OpenWeb()
            ' Get the SharePoint list.
            Dim LookupList As SPList = FormWeb.Lists("MyList")
            ' Query for the item.
            Dim MyQuery As New SPQuery()
            ' "Title" is the field (column) to search in the SharePoint list.
            ' my:myFields/my:myCombo is the xpath to the field bound to the Combo Box in the form.
            MyQuery.Query = "<Where><Eq><FieldRef Name='Title' /><Value Type='Text'>" &amp; _
                GetDomValue("/my:myFields/my:myCombo") &amp; "</Value></Eq></Where>"
            Dim ReturnedItems As SPListItemCollection = LookupList.GetItems(MyQuery)
            ' Add the item to the lookup list if no items were returned in the query.
            If ReturnedItems.Count = 0 Then
                Dim NewItem As SPListItem = LookupList.Items.Add()
                ' Set the value of the Title field in the list to the value in Combo Box on the form.
                NewItem("Title") = GetDomValue("/my:myFields/my:myCombo")
                ' Set AllowUnsafeUpdates to 'true' to temporarily allow updates to the database.
                FormWeb.AllowUnsafeUpdates = True
                NewItem.Update()
                ' Set AllowUnsafeUpdates back to 'false' to prevent further updates to the database.
                FormWeb.AllowUnsafeUpdates = False
            End If
        End Using
    End Using
   ```

8. El ejemplo de código anterior depende de la función auxiliar  `GetDomValue`. Pegue el código siguiente para la función auxiliar  `GetDomValue` debajo de la función del controlador de eventos  `myCombo_Changed`. 
    
   ```cs
    private string GetDomValue(string XpathToGet)
    {
        return this.CreateNavigator().SelectSingleNode(XpathToGet, this.NamespaceManager).Value;
    }
   ```

   ```vb
    Private Function GetDomValue(XpathToGet As String) As String
        Return Me.CreateNavigator().SelectSingleNode(XpathToGet, Me.NamespaceManager).Value
    End Function
   ```

9. Publicar el formulario mediante el uso de los siguientes pasos:
    
    1. Haga clic en **SharePoint Server**, en la ficha **Publicar**, en Backstage. 
        
    2. Escriba la dirección URL del sitio de SharePoint en donde desea publicar el formulario y, a continuación, haga clic en **Siguiente**. 
        
       > [!IMPORTANT]
       > [!IMPORTANTE] Debe ser administrador de una colección de sitios en este sitio para publicar esta plantilla de formulario como un solución de espacio aislado. 
    
    3. Seleccione **Biblioteca de formularios** y, a continuación, haga clic en **Siguiente**.
        
    4. Seleccione **Crear una nueva biblioteca de formularios** y, a continuación, haga clic en **Siguiente**.
        
    5. Escriba el nombre y las descripciones de la biblioteca de formularios y haga clic en **Siguiente**.
        
    6. Haga clic en **Publicar**.
        
    7. Una vez publicado el formulario, abra el formulario desde la biblioteca y agregue un nuevo valor en el cuadro combinado para probar el código. Cuando salga del campo myCombo, el nuevo valor se escribirá en la lista de SharePoint. 
    

