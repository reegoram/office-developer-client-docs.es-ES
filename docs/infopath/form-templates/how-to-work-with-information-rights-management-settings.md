---
title: Trabajar con derechos de información de configuración de administración
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
keywords:
- information rights management [infopath 2007],InfoPath 2007, Information Rights Management,IRM [InfoPath 2007]
localization_priority: Normal
ms.assetid: 4ad91898-b23e-4410-8839-a65259e53d37
description: 'Existen dos tipos de configuración de Information Rights Management (IRM) disponibles en Microsoft InfoPath: una para proteger el acceso a las plantillas de formulario de InfoPath y otra para controlar el acceso y las acciones en los datos que contengan los formularios completados.'
ms.openlocfilehash: 4e6fdac6a0b2b5cd6a29de948cc9dbbd01a407d8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2018
ms.locfileid: "19815906"
---
# <a name="work-with-information-rights-management-settings"></a>Trabajar con derechos de información de configuración de administración

Existen dos tipos de configuración de Information Rights Management (IRM) disponibles en Microsoft InfoPath: una para proteger el acceso a las plantillas de formulario de InfoPath y otra para controlar el acceso y las acciones en los datos que contengan los formularios completados.
  
> [!NOTE]
> [!NOTA] La restricción de permisos solo está disponible con plantillas de formulario compatibles con el editor de InfoPath. Las plantillas de formulario compatibles con exploradores no admiten IRM. 
  
## <a name="adding-the-manage-credentials-command-to-the-quick-access-toolbar"></a>Agregar el comando Administrar credenciales a la Barra de herramientas de acceso rápido

El comando **Administrar credenciales** usado para trabajar con configuraciones de IRM al diseñar una plantilla de formulario no está disponible de forma predeterminada. Siga los siguientes pasos para agregarlo a la **Barra de herramientas de acceso rápido**.
  
### <a name="add-the-manage-credentials-command-to-the-quick-access-toolbar"></a>Para agregar el comando Administrar credenciales a la Barra de herramientas de acceso rápido

1.  Haga clic en la flecha del extremo derecho de la **Barra de herramientas de acceso rápido** para desplegar el menú **Personalizar barra de herramientas de acceso rápido** y, a continuación, haga clic en **Más comandos**.
    
2. En la lista **Comandos disponibles en**, seleccione **Todos los comandos**.
    
3. Desplace hacia abajo la lista hasta **Administrar credenciales** y, a continuación, haga clic en **Agregar**.
    
4. Haga clic en **Aceptar**.
    
Para obtener más información acerca de cómo usar el comando **Administrar credenciales** y el cuadro de diálogo **Permisos** de InfoPath, vea el tema sobre "Creación de una plantilla de formulario con permisos restringidos" en la ayuda de InfoPath. 
  
## <a name="the-irm-object-model"></a>El modelo de objetos de IRM

Use la clase [Permission](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Permission.aspx) para tener acceso a [UserPermissionCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.UserPermissionCollection.aspx) y a la configuración de permisos de IRM que se pueden aplicar a un formulario. Para tener acceso al objeto **Permission** asociado a la plantilla de formulario, utilice la propiedad [Permission](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.Permission.aspx) de la clase [XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) . El objeto devuelto **Permission** ofrece acceso a la colección de objetos [UserPermission](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.UserPermission.aspx) asociados a la plantilla de formulario y a cada instancia de creada con esa plantilla. 
  
El objeto **Permission** y sus propiedades y métodos están disponibles tanto si los permisos están restringidos en la plantilla del formulario activo como si no lo están. Use la propiedad [Enabled](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Permission.Enabled.aspx) para determinar si un formulario tiene permisos restringidos. 
  
Los permisos de un formulario se pueden habilitar de una de las formas siguientes usando las propiedades y los métodos de la clase Permission:
  
La propiedad **Enabled** se establece en **true**.
  
Se establece la propiedad [DocumentAuthor](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Permission.DocumentAuthor.aspx) . 
  
Se establece la propiedad [RequestPermissionUrl](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Permission.RequestPermissionUrl.aspx) . 
  
Se establece la propiedad [StoreLicenses](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Permission.StoreLicenses.aspx) en **true** o **false**.
  
Se llama al método [ApplyPolicy](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Permission.ApplyPolicy.aspx) . 
  
> [!NOTE]
> [!NOTA] Si el cliente de Windows Rights Management no está instalado en el equipo de un usuario, al usar la clase **Permission** se produce una excepción. 
  
Para trabajar mediante programación con la configuración de IRM de usuarios individuales en formularios, use las clases **UserPermissionCollection** y **UserPermission**. 
  
Un objeto **UserPermission** asocia un conjunto de permisos del formulario actual a un único usuario y una fecha de caducidad opcional. Use el método [Add](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.UserPermissionCollection.Add.aspx) de la clase **UserPermissionCollection** para añadir y conceder a un usuario un conjunto de permisos para el formulario. Use el método [Remove](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.UserPermissionCollection.Remove.aspx) de la clase **UserPermissionCollection** para quitar a un usuario y sus permisos. Si bien ciertos permisos concedidos mediante la interfaz de usuario se aplican a todos los usuarios, por ejemplo, los de impresión y fecha de caducidad, puede usar las clases **UserPermission** y **UserPermissionCollection** para asignarlos a usuarios individuales con una fecha de caducidad para cada uno de ellos. El modelo de objetos permite a los programadores enumerar la configuración de los permisos en un formulario y proporcionar la funcionalidad que permita a otros usuarios del formulario agregar permisos sin tener que utilizar el panel de tareas **Permiso de formulario** del cuadro de diálogo **Permiso**. 
  
> [!NOTE]
> [!NOTA] Los permisos no se pueden aplicar cuando un formulario está en el modo de vista previa. Por ello, todas las propiedades de la clase **Permission** son de sólo lectura cuando se está en la vista previa de un formulario. En el modo de vista previa, la propiedad **Enabled** devolverá siempre **false**; si el código trata de cambiar este valor, se produce una excepción **System.Runtime.InteropServices.COMException** y se devuelve un mensaje de error que dice "La propiedad o el método no está disponible en el modo de vista previa". De la misma manera, los métodos asociados a las clases **UserPermission** y **UserPermissionCollection** devolverán este mensaje de error si se usan en el modo de vista previa. 
  
### <a name="overview-of-the-permission-class"></a>Información general sobre la clase Permission

La clase **UserPermissionCollection** proporciona las siguientes propiedades y un método: 
  
|**Nombre**|**Descripción**|
|:-----|:-----|
|[ApplyPolicy](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Permission.ApplyPolicy.aspx) (método)  <br/> |Aplica una directiva al formulario utilizando un archivo de plantilla de directiva.  <br/> |
|[DocumentAuthor](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Permission.DocumentAuthor.aspx) (propiedad)  <br/> |Obtiene o establece al autor del formulario actual como una dirección de correo electrónico.  <br/> |
|[Enabled](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Permission.Enabled.aspx) (propiedad)  <br/> |Obtiene o establece si la configuración del permiso representada por el objeto **Permission** está habilitada para el formulario actual.  <br/> |
|[PermissionFromPolicy](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Permission.PermissionFromPolicy.aspx) (propiedad)  <br/> |Obtiene o establece si se ha aplicado una directiva de permisos al formulario actual.  <br/> |
|[PolicyDescription](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Permission.PolicyDescription.aspx) (propiedad)  <br/> |Obtiene una descripción de la directiva que se aplicó al formulario.  <br/> |
|[PolicyName](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Permission.PolicyName.aspx) (propiedad)  <br/> |Obtiene el nombre de la directiva que se aplicó al formulario.  <br/> |
|[RequestPermissionUrl](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Permission.RequestPermissionUrl.aspx) (propiedad)  <br/> |Obtiene o establece el archivo, la dirección URL o dirección de correo electrónico de contacto para los usuarios que necesitan permisos adicionales en el formulario actual.  <br/> |
|[StoreLicenses](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Permission.StoreLicenses.aspx) (propiedad)  <br/> |Obtiene o establece si la licencia del usuario para ver el formulario actual se debe almacenar en caché para permitir su visualización sin conexión cuando el usuario no se pueda conectar a un servidor de administración de derechos.  <br/> |
|[Objetos UserPermissions](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Permission.UserPermissions.aspx) (propiedad)  <br/> |Obtiene un objeto **UserPermissionCollection** para el formulario actual.  <br/> |
   
### <a name="overview-of-the-userpermissioncollection-class"></a>Información general sobre la clase UserPermissionCollection

La clase **UserPermissionCollection** proporciona las siguientes propiedades y métodos: 
  
|**Nombre**|**Descripción**|
|:-----|:-----|
|Método [Add](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.UserPermissionCollection.Add.aspx) (+ 3 sobrecargas)  <br/> |Añada un nuevo usuario al formulario y opcionalmente especifica los permisos y una fecha de caducidad.  <br/> |
|Método [Remove](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.UserPermissionCollection.Remove.aspx)  <br/> |Quita el objeto **UserPermission** con **UserId** especificado de la colección.  <br/> |
|[RemoveAll](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.UserPermissionCollection.RemoveAll.aspx) (método)  <br/> |Quita todos los objetos **UserPermission** de la colección.  <br/> |
|[Count](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.UserPermissionCollection.Count.aspx) (propiedad)  <br/> |Obtiene el número de objetos **UserPermission** de la colección.  <br/> |
|Propiedad [Item](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.UserPermissionCollection.Item.aspx) (+ 1 sobrecarga)  <br/> |Obtiene un objeto **UserPermission** .  <br/> |
   
### <a name="overview-of-the-userpermission-class"></a>Información general sobre la clase UserPermission

La clase **UserPermission** proporciona las siguientes propiedades y un método: 
  
|**Nombre**|**Descripción**|
|:-----|:-----|
|Método [Remove](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.UserPermission.Remove.aspx)  <br/> |Quita el objeto **UserPermission** actual de los permisos del formulario.  <br/> |
|[ExpirationDate](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.UserPermission.ExpirationDate.aspx) (propiedad)  <br/> |Obtiene o establece la fecha de caducidad opcional de los permisos en el formulario actual asignados al usuario asociado con una instancia de la clase **UserPermission** .  <br/> |
|[Permiso](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.UserPermission.Permission.aspx) (propiedad)  <br/> |Obtiene o establece un valor que representa los permisos sobre el formulario actual asignados al usuario asociado con una instancia de la clase **UserPermission** .  <br/> |
|[UserId](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.UserPermission.UserId.aspx) (propiedad)  <br/> |Obtiene la dirección de correo electrónico del usuario cuyos permisos en el formulario actual se determinan mediante el objeto **UserPermission** especificado.  <br/> |
   
### <a name="the-permissiontype-enumeration"></a>Enumeración PermissionType

Los permisos de un usuario se establecen o leen utilizando los valores de enumeración [PermissionType](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.PermissionType.aspx) . 
  
|**Nombre**|**Descripción**|
|:-----|:-----|
|**PermissionType.Change** <br/> |Permite a los usuarios ver, editar, copiar y guardar, pero no imprimir un formulario. Equivalente a la **lectura**, los permisos **Editar**, **Guardar**y **extraer** combinan.  <br/> |
|**PermissionType.Edit** <br/> |Permite al usuario editar el formulario.  <br/> |
|**PermissionType.Extract** <br/> |Permite que a un usuario con el permiso de **lectura** para copiar contenido en el formulario.  <br/> |
|**PermissionType.FullControl** <br/> |Permite al usuario agregar, cambiar y quitar permisos de los demás usuarios de un formulario.  <br/> |
|**PermissionType.ObjectModel** <br/> |Permite que un usuario tener acceso al documento de formulario mediante programación a través de su modelo de objetos. Los usuarios sin el permiso **ObjectModel** no pueden usar el modelo de objetos para determinar sus propios permisos.  <br/> |
|**PermissionType.Print** <br/> |Permite al usuario imprimir el formulario.  <br/> |
|**PermissionType.Read** <br/> |Permite al usuario leer (vista) el formulario. (Los permisos de **lectura** y **la vista** son equivalentes).  <br/> |
|**PermissionType.Save** <br/> |Permite al usuario guardar el formulario.  <br/> |
|**PermissionType.View** <br/> |Permite al usuario ver (lectura) del formulario. (Los permisos de **lectura** y **la vista** son equivalentes).  <br/> |
   
### <a name="example"></a>Ejemplo

En el ejemplo siguiente, si se hace clic en el control **Botón**, se obtiene la colección **UserPermissionsCollection** del formulario, se agrega un usuario al que se asigna el nivel de acceso de cambio y se establece una fecha de caducidad de dos días a partir de la fecha. 
  
```cs
public void CTRL1_Clicked(object sender, ClickedEventArgs e)
{
   string strExpirationDate = DateTime.Today.AddDays(2).ToString();
   DateTime dtExpirationDate = DateTime.Parse(strExpirationDate);
   this.Permission.UserPermissions.Add("someone@example.com", 
      PermissionType.Change, dtExpirationDate);
}
```

```vb
Public Sub CTRL1_Clicked(ByVal sender As Object, _
   ByVal e As ClickedEventArgs)
   Dim strExpirationDate As String = _
      DateTime.Today.AddDays(2).ToString()
   dtExpirationDate As DateTime = DateTime.Parse(strExpirationDate)
   Me.Permission.UserPermissions.Add("someone@example.com", _
      PermissionType.Change, dtExpirationDate)
End Sub
```

