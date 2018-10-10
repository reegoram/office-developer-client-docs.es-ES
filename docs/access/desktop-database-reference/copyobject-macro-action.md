---
title: CopiarObjeto (acción de macro)
TOCTitle: CopyObject Macro Action
ms:assetid: 746f61df-d5db-284a-0897-75820c2be11f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195876(v=office.15)
ms:contentKeyID: 48545661
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm12836
f1_categories:
- Office.Version=v15
ms.openlocfilehash: d48869d42d44a6440a1cc971ec9497320758ef16
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485008"
---
# <a name="copyobject-macro-action"></a><span data-ttu-id="b472f-102">CopiarObjeto (acción de macro)</span><span class="sxs-lookup"><span data-stu-id="b472f-102">CopyObject Macro Action</span></span>


<span data-ttu-id="b472f-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="b472f-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="b472f-p101">Puede usar la acción **CopiarObjeto** para copiar el objeto de base de datos especificado a una base de datos de Access diferente o a la misma base de datos o proyecto de Access con un nuevo nombre. Por ejemplo, puede copiar o hacer una copia de seguridad de un objeto existente en otra base de datos o crear rápidamente un objeto similar con algunos cambios.</span><span class="sxs-lookup"><span data-stu-id="b472f-p101">You can use the **CopyObject** action to copy the specified database object to a different Access database or to the same database or Access project under a new name. For example, you can copy or back up an existing object in another database or quickly create a similar object with a few changes.</span></span>


> [!NOTE]
> <P><span data-ttu-id="b472f-p102">[!NOTA] Esta acción no estará permitida si la base de datos no es de confianza. Si desea más información sobre la activación de macros, consulte los vínculos de la sección See Also de este artículo.</span><span class="sxs-lookup"><span data-stu-id="b472f-p102">This action will not be allowed if the database is not trusted. For more information about enabling macros, see the links in the See Also section of this article.</span></span></P>



## <a name="setting"></a><span data-ttu-id="b472f-108">Configuración</span><span class="sxs-lookup"><span data-stu-id="b472f-108">Setting</span></span>

<span data-ttu-id="b472f-109">La acción **CopiarObjeto** tiene los siguientes argumentos.</span><span class="sxs-lookup"><span data-stu-id="b472f-109">The **CopyObject** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="b472f-110">Argumento de la acción</span><span class="sxs-lookup"><span data-stu-id="b472f-110">Action argument</span></span></p></th>
<th><p><span data-ttu-id="b472f-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="b472f-111">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b472f-112"><strong>Base de datos de destino</strong></span><span class="sxs-lookup"><span data-stu-id="b472f-112"><strong>Destination Database</strong></span></span></p></td>
<td><p><span data-ttu-id="b472f-p103">Ruta de acceso y nombre de archivo válidos para la base de datos de destino. Escriba la ruta de acceso y el nombre de archivo en el cuadro <strong>Base de datos de destino</strong>, en la sección <strong>Argumentos de acción</strong> del panel Generador de macros. Deje este argumento en blanco si desea seleccionar la base de datos actual. 

</span><span class="sxs-lookup"><span data-stu-id="b472f-p103">A valid path and file name for the destination database. Enter the path and file name in the <strong>Destination Database</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane. Leave this argument blank if you want to select the current database.</span></span></p>

> [!NOTE]
> <P><span data-ttu-id="b472f-p104">Este argumento solo está disponible en el entorno de base de datos de Access. Cuando se usa esta acción en un entorno de proyecto de Access (.adp), el argumento Base de datos de destino debe estar en blanco.</span><span class="sxs-lookup"><span data-stu-id="b472f-p104">This argument is only available in the Access database environment. When using this action in an Access project environment (.adp), the Destination Database argument must be blank.</span></span></P>


<p><span data-ttu-id="b472f-118">Si se ejecuta una macro que contiene la acción <strong>CopiarObjeto</strong> en una base de datos de biblioteca y se deja este argumento en blanco, Microsoft Office Access 2007 copiará el objeto a la base de datos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="b472f-118">If you run a macro containing the <strong>CopyObject</strong> action in a library database and leave this argument blank, Microsoft Office Access 2007 will copy the object into the library database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b472f-119"><strong>Nombre nuevo</strong></span><span class="sxs-lookup"><span data-stu-id="b472f-119"><strong>New Name</strong></span></span></p></td>
<td><p><span data-ttu-id="b472f-p105">Nombre nuevo del objeto. Cuando copie a una base de datos diferente, deje este argumento en blanco si desea mantener el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="b472f-p105">A new name for the object. When copying to a different database, leave this argument blank to keep the same name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b472f-122"><strong>Tipo de objeto de origen</strong></span><span class="sxs-lookup"><span data-stu-id="b472f-122"><strong>Source Object Type</strong></span></span></p></td>
<td><p><span data-ttu-id="b472f-p106">El tipo de objeto que desea copiar. Haga clic en <strong>Tabla</strong>, <strong>Consulta</strong>, <strong>Formulario</strong>, <strong>Informe</strong>, <strong>Macro</strong>, <strong>Módulo</strong>, <strong>Página de acceso a datos</strong>, <strong>Vista de servidor</strong>, <strong>Diagrama</strong>, <strong>Procedimiento almacenado</strong> o <strong>Función</strong>. Para copiar el objeto seleccionado en el Panel de navegación, deje este argumento en blanco.</span><span class="sxs-lookup"><span data-stu-id="b472f-p106">The object type you want to copy. Click <strong>Table</strong>, <strong>Query</strong>, <strong>Form</strong>, <strong>Report</strong>, <strong>Macro</strong>, <strong>Module</strong>, <strong>Data Access Page</strong>, <strong>Server View</strong>, <strong>Diagram</strong>, <strong>Stored Procedure</strong>, or <strong>Function</strong>. To copy the object selected in the Navigation Pane, leave this argument blank.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b472f-126"><strong>Nombre de objeto de origen</strong></span><span class="sxs-lookup"><span data-stu-id="b472f-126"><strong>Source Object Name</strong></span></span></p></td>
<td><p><span data-ttu-id="b472f-127">El nombre del objeto que se va a copiar.</span><span class="sxs-lookup"><span data-stu-id="b472f-127">The name of the object to be copied.</span></span> <span data-ttu-id="b472f-128">El cuadro <strong>Nombre del objeto de origen</strong> muestra todos los objetos en la base de datos del tipo seleccionado por el argumento <strong>Tipo de objeto de origen</strong> .</span><span class="sxs-lookup"><span data-stu-id="b472f-128">The <strong>Source Object Name</strong> box shows all objects in the database of the type selected by the <strong>Source Object Type</strong> argument.</span></span> <span data-ttu-id="b472f-129">En el cuadro <strong>Nombre de objeto de origen</strong> , haga clic en el objeto que se va a copiar.</span><span class="sxs-lookup"><span data-stu-id="b472f-129">In the <strong>Source Object Name</strong> box, click the object to copy.</span></span> <span data-ttu-id="b472f-130">Si deja en blanco el argumento <strong>Tipo de objeto de origen</strong> , deje también en blanco este argumento.</span><span class="sxs-lookup"><span data-stu-id="b472f-130">If you leave the <strong>Source Object Type</strong> argument blank, leave this argument blank also.</span></span> <span data-ttu-id="b472f-131">Si ejecuta una macro que contiene la acción <strong>CopiarObjeto</strong> en una base de datos de biblioteca, Access primero busca el objeto con este nombre en la base de datos de biblioteca y después en la base de datos actual.</span><span class="sxs-lookup"><span data-stu-id="b472f-131">If you run a macro containing the <strong>CopyObject</strong> action in a library database, Access first looks for the object with this name in the library database, and then in the current database.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="b472f-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b472f-132">Remarks</span></span>

<span data-ttu-id="b472f-133">Debe especificar un valor para uno o los dos argumentos **Base de datos de destino** y **Nombre nuevo** de esta acción.</span><span class="sxs-lookup"><span data-stu-id="b472f-133">You must enter a value for either one or both of the **Destination Database** and **New Name** arguments for this action.</span></span>

<span data-ttu-id="b472f-p108">Si deja en blanco los argumentos **Tipo del objeto de origen** y **Nombre del objeto de origen**, Access copia el objeto seleccionado en el panel de navegación. Para seleccionar un objeto en el panel de navegación, puede usar la acción **SeleccionarObjeto** con el argumento En panel de navegación establecido en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="b472f-p108">If you leave the **Source Object Type** and **Source Object Name** arguments blank, Access copies the object selected in the Navigation Pane. To select an object in the Navigation Pane, you can use the **SelectObject** action with the In Navigation Pane argument set to **Yes**.</span></span>

<span data-ttu-id="b472f-136">La acción **CopiarObjeto** es similar a realizar los siguientes pasos manualmente:</span><span class="sxs-lookup"><span data-stu-id="b472f-136">The **CopyObject** action is similar to performing the following steps manually:</span></span>

1.  <span data-ttu-id="b472f-137">Seleccione un objeto en el Panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="b472f-137">Select an object in the Navigation Pane.</span></span>

2.  <span data-ttu-id="b472f-138">En la pestaña Home, en el grupo Clipboard, haga clic en Copy.</span><span class="sxs-lookup"><span data-stu-id="b472f-138">On the Home tab, in the Clipboard group, click Copy.</span></span>

3.  <span data-ttu-id="b472f-p109">En la misma ficha, haga clic en **Pegar**.El cuadro de diálogo **Pegar como** aparece de modo que pueda proporcionarle un nombre nuevo al objeto. La acción **CopiarObjeto** realiza todos estos pasos automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b472f-p109">On the same tab, click **Paste**.The **Paste As** dialog box appears so that you can give the object a new name. The **CopyObject** action performs all of these steps automatically.</span></span>


> [!NOTE]
> <P><span data-ttu-id="b472f-141">[!NOTA] Al copiar páginas de acceso a datos, la acción <STRONG>CopiarObjeto</STRONG> copia solo el vínculo al archivo .htm asociado, no al archivo en sí.</span><span class="sxs-lookup"><span data-stu-id="b472f-141">When copying data access pages, the <STRONG>CopyObject</STRONG> action copies only the link to the associated .htm file, not the file itself.</span></span></P>



<span data-ttu-id="b472f-p110">La ruta y el nombre de archivo de la base de datos de destino deben existir antes de que la macro ejecute la acción **CopiarObjeto**. Si no existen, Access muestra un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="b472f-p110">The path and file name of the destination database must exist before the macro runs the **CopyObject** action. If they don't exist, Access displays an error message.</span></span>

<span data-ttu-id="b472f-144">Para ejecutar la acción **CopiarObjeto** en un módulo de Visual Basic para Aplicaciones (VBA), utilice el método **CopyObject** del objeto **DoCmd**.</span><span class="sxs-lookup"><span data-stu-id="b472f-144">To run the **CopyObject** action in a Visual Basic for Applications (VBA) module, use the **CopyObject** method of the **DoCmd** object.</span></span>

<span data-ttu-id="b472f-p111">También se puede copiar manualmente un objeto seleccionado en el panel de navegación o un objeto que está abierto actualmente, haciendo clic en el **Botón de Microsoft Office** y en **Guardar como**. Este comando realizará una copia del objeto únicamente en la base de datos activa. En el cuadro de diálogo **Guardar como**, escriba el nombre para la copia y elija el tipo de objeto con el que desea guardarla. Si ya se ha guardado el objeto original y guarda la copia en la base de datos activa con un nombre nuevo, la versión original se conservará con su nombre antiguo.</span><span class="sxs-lookup"><span data-stu-id="b472f-p111">You can also manually copy an object selected in the Navigation Pane, or an object that is currently open, by clicking the **File** tab and then clicking **Save As**. This command will make a copy of the object in the current database only. In the **Save As** dialog box, enter the name for the copy, and choose what type of object you want to save it as. If the original object has already been saved and you save it in the current database with a new name, the original version still exists with its old name.</span></span>

<span data-ttu-id="b472f-149">Para copiar manualmente un objeto a una base de datos de Access diferente:</span><span class="sxs-lookup"><span data-stu-id="b472f-149">To manually copy an object to a different Access database:</span></span>

1.  <span data-ttu-id="b472f-150">En la ficha **Datos externos**, en el grupo **Exportar**, haga clic en **Más** y, a continuación, en **Base de datos de Access**.</span><span class="sxs-lookup"><span data-stu-id="b472f-150">On the **External Data** tab, in the **Export** group, click **More** and then click **Access Database**.</span></span>

2.  <span data-ttu-id="b472f-151">En el cuadro de diálogo **Exportar - Base de datos de Access**, escriba el nombre del archivo de la base de datos de destino.-o bien-Haga clic en **Examinar** para mostrar el cuadro de diálogo **Guardar archivo**, ubique la base de datos de destino y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b472f-151">In the **Export - Access Database** dialog box, enter the file name of the destination database.-or-Click **Browse** to display the **File Save** dialog box, locate the destination database, and then click **Save**.</span></span>

3.  <span data-ttu-id="b472f-p112">En el cuadro de diálogo **Exportar - Base de datos de Access**, haga clic en **Aceptar**. Aparece el cuadro de diálogo **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="b472f-p112">In the **Export - Access Database** dialog box, click **OK**. The **Export** dialog box appears.</span></span>

4.  <span data-ttu-id="b472f-p113">En el cuadro de diálogo **Exportar**, escriba un nombre para el objeto de la base de datos de destino. Elija las opciones aplicables, como **Exportar definición y datos** o **Sólo definición** para las tablas. Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b472f-p113">In the **Export** dialog box, enter a name for the object in the destination database. Choose any applicable options, such as **Export Definition and Data** or **Definition Only** for tables. When you are finished, click **OK**.</span></span>
