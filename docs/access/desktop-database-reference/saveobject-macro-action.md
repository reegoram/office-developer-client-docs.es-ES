---
title: GuardarObjeto (acción de macro)
TOCTitle: SaveObject Macro Action
ms:assetid: 85716dfc-f76f-ca47-cc40-f8f88162f85a
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196789(v=office.15)
ms:contentKeyID: 48546060
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm116962
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 107b9b97b22f01b1caaf09ae10936abd8484684f
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485280"
---
# <a name="saveobject-macro-action"></a><span data-ttu-id="01190-102">GuardarObjeto (acción de macro)</span><span class="sxs-lookup"><span data-stu-id="01190-102">SaveObject Macro Action</span></span>


<span data-ttu-id="01190-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="01190-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="01190-p101">Puede usar la acción **GuardarObjeto** para guardar el objeto de Access especificado o el objeto activo si ninguno está especificado. También puede guardar el objeto activo con un nombre nuevo en algunos casos (esto funciona de la misma forma que el comando **Guardar como** en la **Barra de herramientas de acceso rápido**).</span><span class="sxs-lookup"><span data-stu-id="01190-p101">You can use the **SaveObject** action to save either a specified Access object or the active object if none is specified. You can also save the active object with a new name in some cases (this functions the same as the **Save As** command on the **Quick Access Toolbar**).</span></span>


> [!NOTE]
> <P><span data-ttu-id="01190-p102">[!NOTA] Esta acción no estará permitida si la base de datos no es de confianza. Si desea más información sobre la activación de macros, consulte los vínculos de la sección See Also de este artículo.</span><span class="sxs-lookup"><span data-stu-id="01190-p102">This action will not be allowed if the database is not trusted. For more information about enabling macros, see the links in the See Also section of this article.</span></span></P>



## <a name="setting"></a><span data-ttu-id="01190-108">Configuración</span><span class="sxs-lookup"><span data-stu-id="01190-108">Setting</span></span>

<span data-ttu-id="01190-109">La acción **GuardarObjeto** tiene los siguientes argumentos.</span><span class="sxs-lookup"><span data-stu-id="01190-109">The **SaveObject** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="01190-110">Argumento de la acción</span><span class="sxs-lookup"><span data-stu-id="01190-110">Action argument</span></span></p></th>
<th><p><span data-ttu-id="01190-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="01190-111">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01190-112"><strong>Tipo de objeto</strong></span><span class="sxs-lookup"><span data-stu-id="01190-112"><strong>Object Type</strong></span></span></p></td>
<td><p><span data-ttu-id="01190-p103">El tipo de objeto que desea guardar. Haga clic en <strong>Tabla</strong>, <strong>Consulta</strong>, <strong>Formulario</strong>, <strong>Informe</strong>, <strong>Macro</strong>, <strong>Módulo</strong>, <strong>Página de acceso a datos</strong>, <strong>Vista de servidor</strong>, <strong>Diagrama</strong>, <strong>Procedimiento almacenado</strong> o <strong>Función</strong> en el cuadro <strong>Tipo de objeto</strong> en la sección <strong>Argumentos de acción</strong> del panel del Generador de macros. Para seleccionar el objeto activo, deje este argumento en blanco. Si selecciona un tipo de objeto en este argumento, debe seleccionar el nombre de un objeto existente en el argumento <strong>Nombre de objeto</strong>.</span><span class="sxs-lookup"><span data-stu-id="01190-p103">The type of object you want to save. Click <strong>Table</strong>, <strong>Query</strong>, <strong>Form</strong>, <strong>Report</strong>, <strong>Macro</strong>, <strong>Module</strong>, <strong>Data Access Page</strong>, <strong>Server View</strong>, <strong>Diagram</strong>, <strong>Stored Procedure</strong>, or <strong>Function</strong> in the <strong>Object Type</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane. To select the active object, leave this argument blank. If you select an object type in this argument, you must select an existing object's name in the <strong>Object Name</strong> argument.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01190-117"><strong>Nombre del objeto</strong></span><span class="sxs-lookup"><span data-stu-id="01190-117"><strong>Object Name</strong></span></span></p></td>
<td><p><span data-ttu-id="01190-118">El nombre del objeto que se va a guardar.</span><span class="sxs-lookup"><span data-stu-id="01190-118">The name of the object to be saved.</span></span> <span data-ttu-id="01190-119">El cuadro <strong>Nombre de objeto</strong> muestra todos los objetos de la base de datos del tipo seleccionado por el argumento <strong>Tipo de objeto</strong>.</span><span class="sxs-lookup"><span data-stu-id="01190-119">The <strong>Object Name</strong> box shows all objects in the database of the type selected by the <strong>Object Type</strong> argument.</span></span> <span data-ttu-id="01190-120">Si deja en blanco el argumento <strong>Tipo de objeto</strong> , puede dejar este argumento en blanco para guardar el objeto activo, o, en algunos casos, especifique un nuevo nombre en este argumento para guardar el objeto activo con este nombre.</span><span class="sxs-lookup"><span data-stu-id="01190-120">If you leave the <strong>Object Type</strong> argument blank, you can leave this argument blank to save the active object, or, in some cases, enter a new name in this argument to save the active object with this name.</span></span> <span data-ttu-id="01190-121">Si escribe un nombre nuevo, el nombre debe cumplir con las convenciones de denominación estándar para objetos de Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="01190-121">If you enter a new name, the name must follow the standard naming conventions for Microsoft Access objects.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="01190-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="01190-122">Remarks</span></span>

<span data-ttu-id="01190-p105">La acción **GuardarObjeto** funciona en todos los objetos de base de datos que el usuario puede abrir explícitamente y guardar. El objeto especificado se debe abrir para la acción **GuardarObjeto** para que tenga efecto en el objeto. Esta acción tiene el mismo efecto que seleccionar un objeto y guardarlo al hacer clic en **Guardar** en la **Barra de herramientas de acceso rápido**. Dejar el argumento **Tipo de objeto** en blanco y escribir un nombre nuevo en el argumento **Nombre de objeto** tiene el mismo efecto que hacer clic en **Guardar como** en la **Barra de herramientas de acceso rápido**, y escribir un nombre nuevo para el objeto activo. Con la acción **GuardarObjeto** puede especificar un objeto para guardar y ejecutar un comando **Guardar como** desde una macro.</span><span class="sxs-lookup"><span data-stu-id="01190-p105">The **SaveObject** action works on all database objects that the user can explicitly open and save. The specified object must be open for the **SaveObject** action to have any effect on the object. This action has the same effect as selecting an object and then saving it by clicking **Save** on the **Quick Access Toolbar**. Leaving the **Object Type** argument blank and entering a new name in the **Object Name** argument has the same effect as clicking **Save As** on the **Quick Access Toolbar**, and entering a new name for the active object. Using the **SaveObject** action enables you to specify an object to save and to perform a **Save As** command from a macro.</span></span>


> [!NOTE]
> <P><span data-ttu-id="01190-128">[!NOTA] No puede utilizar la acción <STRONG>GuardarObjeto</STRONG> para guardar cualquiera de los siguientes con un nombre nuevo:</span><span class="sxs-lookup"><span data-stu-id="01190-128">You can't use the <STRONG>SaveObject</STRONG> action to save any of the following with a new name:</span></span></P>



  - <span data-ttu-id="01190-129">Un formulario en vista Formulario o vista Hoja de datos.</span><span class="sxs-lookup"><span data-stu-id="01190-129">A form in Form view or Datasheet view.</span></span>

  - <span data-ttu-id="01190-130">Un informe en Vista previa de impresión.</span><span class="sxs-lookup"><span data-stu-id="01190-130">A report in Print Preview.</span></span>

  - <span data-ttu-id="01190-131">Un módulo.</span><span class="sxs-lookup"><span data-stu-id="01190-131">A module.</span></span>

  - <span data-ttu-id="01190-132">Una vista de servidor en vista Hoja de datos o Vista previa de impresión.</span><span class="sxs-lookup"><span data-stu-id="01190-132">A server view in Datasheet view or Print Preview.</span></span>

  - <span data-ttu-id="01190-133">Una página de acceso a datos en vista Página.</span><span class="sxs-lookup"><span data-stu-id="01190-133">A data access page in Page view.</span></span>

  - <span data-ttu-id="01190-134">Una tabla en vista Hoja de datos o Vista previa de impresión.</span><span class="sxs-lookup"><span data-stu-id="01190-134">A table in Datasheet view or Print Preview.</span></span>

  - <span data-ttu-id="01190-135">Una consulta en vista Hoja de datos o Vista previa de impresión.</span><span class="sxs-lookup"><span data-stu-id="01190-135">A query in Datasheet view or Print Preview.</span></span>

  - <span data-ttu-id="01190-136">Un procedimiento almacenado en vista Hoja de datos o Vista previa de impresión.</span><span class="sxs-lookup"><span data-stu-id="01190-136">A stored procedure in Datasheet view or Print Preview.</span></span>

<span data-ttu-id="01190-137">La acción **GuardarObjeto**, si se lleva a cabo en una macro que se ejecuta en la base de datos activa o en una base de datos de biblioteca, siempre guarda el objeto especificado en la base de datos en la que se creó el objeto.</span><span class="sxs-lookup"><span data-stu-id="01190-137">The **SaveObject** action, whether it's carried out in a macro run in the current database or in a library database, always saves the specified object or the active object in the database in which the object was created.</span></span>

<span data-ttu-id="01190-p106">Si guarda el objeto activo con un nombre nuevo, pero el nombre es el mismo que el de un objeto existente de este tipo, un cuadro de diálogo solicita si desea sobrescribir el objeto existente. Si estableció el argumento **Activar advertencias** de la acción **EstablecerAdvertencias** como **No**, el cuadro de diálogo no se muestra y el objeto antiguo se sobrescribe automáticamente.</span><span class="sxs-lookup"><span data-stu-id="01190-p106">If you save the active object with a new name, but the name is the same as the name of an existing object of this type, a dialog box asks if you want to overwrite the existing object. If you've set the **Warnings On** argument of the **SetWarnings** action to **No**, the dialog box isn't displayed and the old object is automatically overwritten.</span></span>

<span data-ttu-id="01190-140">Para ejecutar la acción **GuardarObjeto** en un módulo de Visual Basic para Aplicaciones (VBA), utilice el método **Save** del objeto **DoCmd**.</span><span class="sxs-lookup"><span data-stu-id="01190-140">To run the **SaveObject** action in a Visual Basic for Applications (VBA) module, use the **Save** method of the **DoCmd** object.</span></span>
