---
title: EliminarObjeto (acción de macro)
TOCTitle: DeleteObject Macro Action
ms:assetid: a8deb2a7-4e73-8696-b8c1-3a3939d813f7
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821415(v=office.15)
ms:contentKeyID: 48546912
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm152112
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 85e9fc888e06a69be6f458ed03ad92b8253b30a2
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25484831"
---
# <a name="deleteobject-macro-action"></a><span data-ttu-id="7aa66-102">EliminarObjeto (acción de macro)</span><span class="sxs-lookup"><span data-stu-id="7aa66-102">DeleteObject Macro Action</span></span>


<span data-ttu-id="7aa66-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="7aa66-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="7aa66-104">La acción **EliminarObjeto** permite eliminar un objeto de base de datos especificado.</span><span class="sxs-lookup"><span data-stu-id="7aa66-104">You can use the **DeleteObject** action to delete a specified database object.</span></span>


> [!NOTE]
> <P><span data-ttu-id="7aa66-p101">[!NOTA] Esta acción no estará permitida si la base de datos no es de confianza. Si desea más información sobre la activación de macros, consulte los vínculos de la sección See Also de este artículo.</span><span class="sxs-lookup"><span data-stu-id="7aa66-p101">This action will not be allowed if the database is not trusted. For more information about enabling macros, see the links in the See Also section of this article.</span></span></P>



## <a name="setting"></a><span data-ttu-id="7aa66-107">Configuración</span><span class="sxs-lookup"><span data-stu-id="7aa66-107">Setting</span></span>

<span data-ttu-id="7aa66-108">La acción **EliminarObjeto** tiene los argumentos siguientes.</span><span class="sxs-lookup"><span data-stu-id="7aa66-108">The **DeleteObject** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="7aa66-109">Argumento de la acción</span><span class="sxs-lookup"><span data-stu-id="7aa66-109">Action argument</span></span></p></th>
<th><p><span data-ttu-id="7aa66-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="7aa66-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7aa66-111"><strong>Tipo de objeto</strong></span><span class="sxs-lookup"><span data-stu-id="7aa66-111"><strong>Object Type</strong></span></span></p></td>
<td><p><span data-ttu-id="7aa66-p102">Tipo de objeto que se va a eliminar. Haga clic en <strong>Tabla</strong>, <strong>Consulta</strong>, <strong>Formulario</strong>, <strong>Informe</strong>, <strong>Macro</strong>, <strong>Módulo</strong>, <strong>Página de acceso a datos</strong>, <strong>Vista de servidor</strong>, <strong>Diagrama</strong>, <strong>Procedimiento almacenado</strong> o <strong>Función</strong> en el cuadro <strong>Tipo de objeto</strong>, en la sección <strong>Argumentos de acción</strong> del panel Generador de macros. Para eliminar el objeto seleccionado en el panel de navegación, deje este argumento en blanco.</span><span class="sxs-lookup"><span data-stu-id="7aa66-p102">The type of object to delete. Click <strong>Table</strong>, <strong>Query</strong>, <strong>Form</strong>, <strong>Report</strong>, <strong>Macro</strong>, <strong>Module</strong>, <strong>Data Access Page</strong>, <strong>Server View</strong>, <strong>Diagram</strong>, <strong>Stored Procedure</strong>, or <strong>Function</strong> in the <strong>Object Type</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane. To delete the object selected in the Navigation Pane, leave this argument blank.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aa66-115"><strong>Nombre del objeto</strong></span><span class="sxs-lookup"><span data-stu-id="7aa66-115"><strong>Object Name</strong></span></span></p></td>
<td><p><span data-ttu-id="7aa66-116">El nombre del objeto que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="7aa66-116">The name of the object to delete.</span></span> <span data-ttu-id="7aa66-117">El cuadro <strong>Nombre de objeto</strong> muestra todos los objetos de la base de datos del tipo seleccionado por el argumento <strong>Tipo de objeto</strong>.</span><span class="sxs-lookup"><span data-stu-id="7aa66-117">The <strong>Object Name</strong> box shows all objects in the database of the type selected by the <strong>Object Type</strong> argument.</span></span> <span data-ttu-id="7aa66-118">Si deja en blanco el cuadro <strong>Tipo de objeto</strong> , deje también en blanco este cuadro.</span><span class="sxs-lookup"><span data-stu-id="7aa66-118">If you leave the <strong>Object Type</strong> box blank, leave this box blank also.</span></span> <span data-ttu-id="7aa66-119">Si ejecuta una macro que contenga la acción <strong>EliminarObjeto</strong> en una base de datos de biblioteca, Microsoft Office Access 2007 busca primero el objeto con este nombre en la base de datos de biblioteca y, después, en la base de datos activa.</span><span class="sxs-lookup"><span data-stu-id="7aa66-119">If you run a macro containing the <strong>DeleteObject</strong> action in a library database, Microsoft Office Access 2007 first looks for the object with this name in the library database, and then in the current database.</span></span></p></td>
</tr>
</tbody>
</table>



> [!WARNING]
> <P><span data-ttu-id="7aa66-120">[!PRECAUCIóN] Si deja en blanco los cuadros <STRONG>Tipo de objeto</STRONG> y <STRONG>Nombre del objeto</STRONG>, Access elimina el objeto seleccionado en el panel de navegación sin mostrar ningún mensaje de advertencia cuando encuentra la acción <STRONG>EliminarObjeto</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="7aa66-120">If you leave the <STRONG>Object Type</STRONG> and <STRONG>Object Name</STRONG> boxes blank, Access deletes the object selected in the Navigation Pane without displaying a warning message when it encounters the <STRONG>DeleteObject</STRONG> action.</span></span></P>



## <a name="remarks"></a><span data-ttu-id="7aa66-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7aa66-121">Remarks</span></span>

<span data-ttu-id="7aa66-p104">Puede usar la acción **EliminarObjeto** para eliminar objetos temporales creados mientras se ejecutaba la macro. Por ejemplo, podría utilizar la acción **AbrirConsulta** para ejecutar una consulta de creación de tabla que cree una tabla temporal. Cuando termine de usar la tabla temporal, puede ejecutar la acción **EliminarObjeto** para eliminarla.</span><span class="sxs-lookup"><span data-stu-id="7aa66-p104">You can use the **DeleteObject** action to delete temporary objects you have created while running the macro. For example, you could use the **OpenQuery** action to run a make-table query that creates a temporary table. When you are finished using the temporary table, you can use the **DeleteObject** action to delete it.</span></span>

<span data-ttu-id="7aa66-125">Esta acción tiene el mismo efecto que seleccionar un objeto en el panel de navegación y presionar la tecla SUPR o hacer clic con el botón secundario en el objeto del panel de navegación y seleccionar **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="7aa66-125">This action has the same effect as selecting an object in the Navigation Pane and then pressing the DEL key, or right-clicking the object in the Navigation Pane and clicking **Delete**.</span></span>

<span data-ttu-id="7aa66-126">Para ejecutar la acción **EliminarObjeto** en un módulo de Visual Basic para Aplicaciones, puede usar el método **DeleteObject** del objeto **DoCmd**.</span><span class="sxs-lookup"><span data-stu-id="7aa66-126">To run the **DeleteObject** action in a Visual Basic for Applications module, you can use the **DeleteObject** method of the **DoCmd** object.</span></span>
