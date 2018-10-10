---
title: AbrirInforme (acción de macro)
TOCTitle: OpenReport Macro Action
ms:assetid: cd35faf2-190d-ac48-cf59-81c1599eb764
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834462(v=office.15)
ms:contentKeyID: 48547758
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm188079
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 06828474aee961dd6df02f29c7d046805a1c764c
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25484467"
---
# <a name="openreport-macro-action"></a><span data-ttu-id="4ff6c-102">AbrirInforme (acción de macro)</span><span class="sxs-lookup"><span data-stu-id="4ff6c-102">OpenReport Macro Action</span></span>

<span data-ttu-id="4ff6c-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="4ff6c-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="4ff6c-p101">Puede usar la acción **AbrirInforme** para abrir un informe en la vista Diseño o Vista preliminar, o bien, para enviar el informe directamente a la impresora. También puede restringir los registros que se imprimen en el informe.</span><span class="sxs-lookup"><span data-stu-id="4ff6c-p101">You can use the **OpenReport** action to open a report in Design view or Print Preview, or to send the report directly to the printer. You can also restrict the records that are printed in the report.</span></span>

## <a name="setting"></a><span data-ttu-id="4ff6c-106">Configuración</span><span class="sxs-lookup"><span data-stu-id="4ff6c-106">Setting</span></span>

<span data-ttu-id="4ff6c-107">La acción **AbrirInforme** tiene los siguientes argumentos.</span><span class="sxs-lookup"><span data-stu-id="4ff6c-107">The **OpenReport** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="4ff6c-108">Argumento de la acción</span><span class="sxs-lookup"><span data-stu-id="4ff6c-108">Action argument</span></span></p></th>
<th><p><span data-ttu-id="4ff6c-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="4ff6c-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4ff6c-110">Nombre de informe</span><span class="sxs-lookup"><span data-stu-id="4ff6c-110">Report Name</span></span></p></td>
<td><p><span data-ttu-id="4ff6c-p102">Nombre del informe que se va a abrir. El cuadro <strong>Nombre del informe</strong> en la sección <strong>Argumentos de acción</strong> del panel <strong>Generador de macros</strong> muestra todos los informes de la base de datos activa. Este es un argumento obligatorio. Si ejecuta una macro que contenga la acción OpenReport en una base de datos de biblioteca, Microsoft Access primero buscará el informe con este nombre en la base de datos de biblioteca y después en la base de datos actual.  </span><span class="sxs-lookup"><span data-stu-id="4ff6c-p102">The name of the report to open. The <strong>Report Name</strong> box in the <strong>Action Arguments</strong> section of the <strong>Macro Builder</strong> pane shows all reports in the current database. This is a required argument. If you run a macro containing the OpenReport action in a library database, Microsoft Access first looks for the report with this name in the library database, and then in the current database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ff6c-115">Vista</span><span class="sxs-lookup"><span data-stu-id="4ff6c-115">View</span></span></p></td>
<td><p><span data-ttu-id="4ff6c-p103">Vista en la que se va a abrir el informe. Haga clic en <strong>Imprimir</strong> (para imprimir el informe de inmediato), <strong>Diseño</strong> o <strong>Vista preliminar</strong> en el cuadro <strong>Vista</strong>. El valor predeterminado es <strong>Imprimir</strong>.  </span><span class="sxs-lookup"><span data-stu-id="4ff6c-p103">The view in which the report will open. Click <strong>Print</strong> (print the report immediately), <strong>Design</strong>, or <strong>Print Preview</strong> in the <strong>View</strong> box. The default is <strong>Print</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ff6c-119">Filter Name</span><span class="sxs-lookup"><span data-stu-id="4ff6c-119">Filter Name</span></span></p></td>
<td><p><span data-ttu-id="4ff6c-p104">Filtro que restringe los registros del informe. Puede escribir el nombre de una consulta existente o de un filtro que se guardó como consulta. No obstante, la consulta debe incluir todos los campos del informe que está abriendo o tener su propiedad <strong>SalidaTodosLosCampos</strong> establecida en <strong>Sí</strong>.  </span><span class="sxs-lookup"><span data-stu-id="4ff6c-p104">A filter that restricts the report's records. You can enter the name of either an existing query or a filter that was saved as a query. However, the query must include all the fields in the report you are opening or have its <strong>OutputAllFields</strong> property set to <strong>Yes</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ff6c-123">Where Condition</span><span class="sxs-lookup"><span data-stu-id="4ff6c-123">Where Condition</span></span></p></td>
<td><p><span data-ttu-id="4ff6c-124">Una cláusula SQL WHERE válida (sin la palabra WHERE) o una expresión que usa Access para seleccionar registros de la tabla o consulta subyacente al informe.</span><span class="sxs-lookup"><span data-stu-id="4ff6c-124">A valid SQL WHERE clause (without the word WHERE) or expression that Access uses to select records from the report's underlying table or query.</span></span> <span data-ttu-id="4ff6c-125">Si selecciona un filtro con el argumento nombre del filtro, Access aplica esta cláusula WHERE a los resultados del filtro.</span><span class="sxs-lookup"><span data-stu-id="4ff6c-125">If you select a filter with the Filter Name argument, Access applies this WHERE clause to the results of the filter.</span></span> <span data-ttu-id="4ff6c-126">Para abrir un informe y restringir sus registros a los especificados por el valor de un control de un formulario, use la expresión siguiente:</span><span class="sxs-lookup"><span data-stu-id="4ff6c-126">To open a report and restrict its records to those specified by the value of a control on a form, use the following expression:</span></span><br /><span data-ttu-id="4ff6c-127">
<strong>[</strong><em>nombreDelCampo</em><strong>] = Formularios![</strong><em>nombreDelFormulario</em><strong>]![</strong><em>nombre del control en el formulario</em><strong>]</strong></span><span class="sxs-lookup"><span data-stu-id="4ff6c-127">
<strong>[</strong><em>fieldname</em><strong>] = Forms![</strong><em>formname</em><strong>]![</strong><em>controlname on form</em><strong>]</strong></span></span><br />
<span data-ttu-id="4ff6c-128">Sustituya <em>fieldname</em> por el nombre de un campo en la tabla o consulta subyacente del informe que desea abrir.</span><span class="sxs-lookup"><span data-stu-id="4ff6c-128">Replace <em>fieldname</em> with the name of a field in the underlying table or query of the report you want to open.</span></span> <span data-ttu-id="4ff6c-129">Reemplace <em>nombreDeFormulario</em> y <em>nombrecontrol en el formulario</em> con el nombre del formulario y el control del formulario que contiene el valor que desea en el informe para que coincida con los registros.</span><span class="sxs-lookup"><span data-stu-id="4ff6c-129">Replace <em>formname</em> and <em>controlname on form</em> with the name of the form and the control on the form that contains the value you want records in the report to match.</span></span></p>
<p><span data-ttu-id="4ff6c-130"><b>Nota</b>: la longitud máxima del argumento Condición Where es de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="4ff6c-130"><b>NOTE</b>: The maximum length of the Where Condition argument is 255 characters.</span></span> <span data-ttu-id="4ff6c-131">Si necesita escribir una cláusula WHERE de SQL más compleja y más larga, utilice el método <b>OpenReport</b> del objeto <b>DoCmd</b> en un de Visual Basic para aplicaciones (VBA) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="4ff6c-131">If you need to enter a more complex SQL WHERE clause longer than this, use the <b>OpenReport</b> method of the <b>DoCmd</b> object in a Visual Basic for Applications (VBA) module instead.</span></span> <span data-ttu-id="4ff6c-132">Puede especificar instrucciones de cláusula WHERE de SQL de hasta 32.768 caracteres en VBA.</span><span class="sxs-lookup"><span data-stu-id="4ff6c-132">You can enter SQL WHERE clause statements of up to 32,768 characters in VBA.</span></span></p>
</td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ff6c-133">Window Mode</span><span class="sxs-lookup"><span data-stu-id="4ff6c-133">Window Mode</span></span></p></td>
<td><p><span data-ttu-id="4ff6c-p108">Modo en el que se va a abrir el informe. Haga clic en <strong>Normal</strong>, <strong>Oculto</strong>, <strong>Icono</strong> o <strong>Cuadro de diálogo</strong> en el cuadro <strong>Modo de la ventana</strong>. El valor predeterminado es <strong>Normal</strong>.  </span><span class="sxs-lookup"><span data-stu-id="4ff6c-p108">The mode in which the report will open. Click <strong>Normal</strong>, <strong>Hidden</strong>, <strong>Icon</strong>, or <strong>Dialog</strong> in the <strong>Window Mode</strong> box. The default is <strong>Normal</strong>.</span></span></p>
<p><span data-ttu-id="4ff6c-137"><b>Nota</b>: valores del argumento modo parte de la ventana no se aplican al uso de documentos con fichas.</span><span class="sxs-lookup"><span data-stu-id="4ff6c-137"><b>NOTE</b>: Some Window Mode argument settings do not apply when using tabbed documents.</span></span> <span data-ttu-id="4ff6c-138">Para cambiar a ventanas superpuestas:</span><span class="sxs-lookup"><span data-stu-id="4ff6c-138">To switch to overlapping windows:</span></span>
<ol>
<li><p><span data-ttu-id="4ff6c-139">Haga clic en <strong>Opciones</strong>.</span><span class="sxs-lookup"><span data-stu-id="4ff6c-139">Click <strong>Options</strong>.</span></span></p></li>
<li><p><span data-ttu-id="4ff6c-140">En el cuadro de diálogo <strong>Opciones de Access</strong>, haga clic en <strong>Base de datos actual</strong>.</span><span class="sxs-lookup"><span data-stu-id="4ff6c-140">In the <strong>Access Options</strong> dialog box, click <strong>Current Database</strong>.</span></span></p></li>
<li><p><span data-ttu-id="4ff6c-141">En la sección <strong>Opciones de aplicación</strong>, bajo <strong>Opciones de la ventana de documentos</strong>, haga clic en <strong>Ventanas superpuestas</strong>.</span><span class="sxs-lookup"><span data-stu-id="4ff6c-141">In the <strong>Application Options</strong> section, under <strong>Document Window Options</strong>, click <strong>Overlapping Windows</strong>.</span></span></p></li>
<li><p><span data-ttu-id="4ff6c-142">Haga clic en <strong>Aceptar</strong>y, a continuación, cierre y vuelva a abrir la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4ff6c-142">Click <strong>OK</strong>, and then close and reopen the database.</span></span></p></li>
</ol>
</td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="4ff6c-143">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4ff6c-143">Remarks</span></span>

<span data-ttu-id="4ff6c-p110">El valor **Imprimir** del argumento **Vista** imprime el informe de inmediato usando los valores de impresora actuales, sin que se muestre el cuadro de diálogo **Imprimir**. También puede usar la acción **AbrirInforme** para abrir y configurar un informe y usar, a continuación, la acción PrintOut para imprimirlo. Por ejemplo, cuando desea modificar el informe o usarla acción **Imprimir** para cambiar los valores de la impresora antes de imprimir.</span><span class="sxs-lookup"><span data-stu-id="4ff6c-p110">The **Print** setting for the **View** argument prints the report immediately by using the current printer settings, without bringing up the **Print** dialog box. You can also use the **OpenReport** action to open and set up a report and then use the PrintOut action to print it. For example, you may want to modify the report or use the **PrintOut** action to change the printer settings before you print.</span></span>

<span data-ttu-id="4ff6c-147">El filtro y la condición WHERE aplicados se convertirán en el valor de la propiedad **Filtro** del informe.</span><span class="sxs-lookup"><span data-stu-id="4ff6c-147">The filter and WHERE condition you apply become the setting of the report's **Filter** property.</span></span>

<span data-ttu-id="4ff6c-148">La acción **AbrirInforme** es similar a hacer doble clic en el informe en el panel de navegación o hacer clic con el botón secundario en el informe en el panel de navegación y seleccionar una vista o el comando **Imprimir**.</span><span class="sxs-lookup"><span data-stu-id="4ff6c-148">The **OpenReport** action is similar to double-clicking the report in the Navigation Pane, or right-clicking the report in the Navigation Pane and selecting a view or the **Print** command.</span></span>

> [!TIP] 
> - <span data-ttu-id="4ff6c-149">Si desea imprimir informes similares para diferentes conjuntos de datos, use un filtro o una cláusula WHERE para restringir los registros que se van a imprimir en el informe.</span><span class="sxs-lookup"><span data-stu-id="4ff6c-149">To print similar reports for different sets of data, use a filter or a WHERE clause to restrict the records printed in the report.</span></span> <span data-ttu-id="4ff6c-150">A continuación, modifique la macro para aplicar un filtro distinto o cambiar el argumento Condición Where.</span><span class="sxs-lookup"><span data-stu-id="4ff6c-150">Then edit the macro to apply a different filter or change the Where Condition argument.</span></span>
> 
> - <span data-ttu-id="4ff6c-p112">Puede arrastrar un informe desde el panel de navegación hasta una fila de acción de una macro. De este modo, se crea automáticamente una acción **AbrirInforme** que abre el informe en la vista Informe.</span><span class="sxs-lookup"><span data-stu-id="4ff6c-p112">You can drag a report from the Navigation Pane to a macro action row. This automatically creates an **OpenReport** action that opens the report in Report view.</span></span>

## <a name="example"></a><span data-ttu-id="4ff6c-153">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4ff6c-153">Example</span></span>

<span data-ttu-id="4ff6c-154">El siguiente ejemplo nuestra cómo usar la acción OpenReport para pasar un parámetro que filtra un informe cuando se abre.</span><span class="sxs-lookup"><span data-stu-id="4ff6c-154">The following example shows how to use the OpenReport action to pass a parameter that filters a report as it is opened.</span></span> <span data-ttu-id="4ff6c-155">El informe de **rptChapters** muestra los registros para el autor del especificado, se pasa el elemento seleccionado en el cuadro combinado de **cboAuthors** para el parámetro SelectedAuthor.</span><span class="sxs-lookup"><span data-stu-id="4ff6c-155">The **rptChapters** report displays the records for the specified author by passing the item selected in the **cboAuthors** combo box to the SelectedAuthor parameter.</span></span>

<span data-ttu-id="4ff6c-156">**Código de ejemplo proporcionado por** la [referencia del programador de Microsoft Access 2010](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span><span class="sxs-lookup"><span data-stu-id="4ff6c-156">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

```vb
    OpenReport
        Report Name rptChapters
        View Report
        Filter Name
        Where Condition
        Window Mode Normal
    
    Parameters
        SelectedAuthor =[cboAuthor]
```