---
title: GoToControl Macro Action
TOCTitle: GoToControl Macro Action
ms:assetid: caff76dc-7ca8-4f87-8144-89445ed4600d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834370(v=office.15)
ms:contentKeyID: 48547705
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 2617544bf04aa0b26ccbb9d7ce8d7329d42ed1e9
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25484847"
---
# <a name="gotocontrol-macro-action"></a><span data-ttu-id="3fe3a-102">GoToControl Macro Action</span><span class="sxs-lookup"><span data-stu-id="3fe3a-102">GoToControl Macro Action</span></span>


<span data-ttu-id="3fe3a-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="3fe3a-103">**Applies to**: Access 2013 | Office 2013</span></span>



<span data-ttu-id="3fe3a-104">Puede utilizar la acción **GoToControl (IrAControl)** para desplazar el enfoque para el campo o control especificado en el registro actual del formulario abierto, hoja de datos de formulario, hoja de datos de tabla o consulta de la hoja de datos.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-104">You can use the **GoToControl** action to move the focus to the specified field or control in the current record of the open form, form datasheet, table datasheet, or query datasheet.</span></span> <span data-ttu-id="3fe3a-105">Puede usar esta acción si desea que un campo o control concreto tenga el foco.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-105">You can use this action when you want a particular field or control to have the focus.</span></span> <span data-ttu-id="3fe3a-106">A continuación, en este campo o control puede utilizarse para realizar comparaciones o acciones **FindRecord** .</span><span class="sxs-lookup"><span data-stu-id="3fe3a-106">This field or control can then be used for comparisons or **FindRecord** actions.</span></span> <span data-ttu-id="3fe3a-107">También puede usar esta acción para desplazarse por un formulario según ciertas condiciones.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-107">You can also use this action to navigate in a form according to certain conditions.</span></span> <span data-ttu-id="3fe3a-108">Por ejemplo, si el usuario escribe No en un control Casado en un formulario de seguros de salud, el foco puede omitir automáticamente el control Nombre de cónyuge y pasar al siguiente control.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-108">For example, if the user enters No in a Married control on a health insurance form, the focus can automatically skip the Spouse/partner Name control and move to the next control.</span></span>

## <a name="setting"></a><span data-ttu-id="3fe3a-109">Configuración</span><span class="sxs-lookup"><span data-stu-id="3fe3a-109">Setting</span></span>


> [!NOTE]
> <P><span data-ttu-id="3fe3a-110">Esta acción no está disponible para su uso con páginas de acceso a datos.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-110">This action is not available for use with data access pages.</span></span></P>



<span data-ttu-id="3fe3a-111">La acción **GoToControl** tiene el siguiente argumento.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-111">The **GoToControl** action has the following argument.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="3fe3a-112">Argumento de la acción</span><span class="sxs-lookup"><span data-stu-id="3fe3a-112">Action argument</span></span></p></th>
<th><p><span data-ttu-id="3fe3a-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="3fe3a-113">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3fe3a-114"><strong>Nombre del control</strong></span><span class="sxs-lookup"><span data-stu-id="3fe3a-114"><strong>Control Name</strong></span></span></p></td>
<td><p><span data-ttu-id="3fe3a-115">El nombre del campo o control donde desea el foco.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-115">The name of the field or control where you want the focus.</span></span> <span data-ttu-id="3fe3a-116">Escriba el nombre del campo o control en el cuadro <strong>Nombre del Control</strong> en la sección <strong>Argumentos de acción</strong> del panel Generador de macros.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-116">Enter the field or control name in the <strong>Control Name</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane.</span></span> <span data-ttu-id="3fe3a-117">Este argumento es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-117">This is a required argument.</span></span></p>

> [!NOTE]
> <P><span data-ttu-id="3fe3a-118">¡Escriba sólo el nombre del campo o control en el argumento <STRONG>Nombre del Control</STRONG> , no el identificador completo, como Forms! ¡Productos! [Product ID].</span><span class="sxs-lookup"><span data-stu-id="3fe3a-118">Enter only the name of the field or control in the <STRONG>Control Name</STRONG> argument, not the fully qualified identifier, such as Forms!Products![Product ID].</span></span></P>


<p></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="3fe3a-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3fe3a-119">Remarks</span></span>

<span data-ttu-id="3fe3a-120">No se puede utilizar la acción **GoToControl (IrAControl)** para desplazar el enfoque a un control de un formulario oculto.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-120">You cannot use the **GoToControl** action to move the focus to a control on a hidden form.</span></span>


> [!TIP]
> <P><span data-ttu-id="3fe3a-121">Puede utilizar la acción <STRONG>GoToControl (IrAControl)</STRONG> para desplazarse a un subformulario, que es un tipo de control.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-121">You can use the <STRONG>GoToControl</STRONG> action to move to a subform, which is a type of control.</span></span> <span data-ttu-id="3fe3a-122">A continuación, puede usar la acción <STRONG>IrARegistro</STRONG> para mover a un registro determinado del subformulario.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-122">You can then use the <STRONG>GoToRecord</STRONG> action to move to a particular record in the subform.</span></span> <span data-ttu-id="3fe3a-123">También puede mover a un control de un subformulario usando la acción <STRONG>IrAControl</STRONG> para moverse primero al subformulario y, a continuación, al control del subformulario.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-123">You can also move to a control on a subform by using the <STRONG>GoToControl</STRONG> action to move first to the subform and then to the control on the subform.</span></span></P>



<span data-ttu-id="3fe3a-124">Para ejecutar la acción **GoToControl (IrAControl)** en un módulo Visual Basic para aplicaciones (VBA), use el método **GoToControl** del objeto **DoCmd** .</span><span class="sxs-lookup"><span data-stu-id="3fe3a-124">To run the **GoToControl** action in a Visual Basic for Applications (VBA) module, use the **GoToControl** method of the **DoCmd** object.</span></span> <span data-ttu-id="3fe3a-125">También puede usar el método **SetFocus** para desplazar el enfoque a un control de un formulario o cualquiera de sus subformularios, o a un campo en una tabla abierta, una consulta o una hoja de datos de formulario.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-125">You can also use the **SetFocus** method to move the focus to a control on a form or any of its subforms, or to a field in an open table, query, or form datasheet.</span></span>

## <a name="examples"></a><span data-ttu-id="3fe3a-126">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3fe3a-126">Examples</span></span>

<span data-ttu-id="3fe3a-127">**Configurar el valor de un control con una macro**</span><span class="sxs-lookup"><span data-stu-id="3fe3a-127">**Set the value of a control by using a macro**</span></span>

<span data-ttu-id="3fe3a-p105">La siguiente macro abre el formulario Agregar productos desde un botón del formulario Proveedores. Muestra el uso de las acciones **Eco**, **CerrarVentana**, **AbrirFormulario**, **ConfigurarValor** e **IrAControl**. La acción **ConfigurarValor** configura el control Id. de proveedor en el formulario Productos para el proveedor actual del formulario Proveedores. La acción **IrAControl** mueve el foco al campo Id. de categoría, donde puede empezar a introducir los datos para el nuevo producto. Esta macro se debe adjuntar al botón Agregar productos del formulario Proveedores.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-p105">The following macro opens the Add Products form from a button on the Suppliers form. It shows the use of the **Echo**, **CloseWindow**, **OpenForm**, **SetValue**, and **GoToControl** actions. The **SetValue** action sets the Supplier ID control on the Products form to the current supplier on the Suppliers form. The **GoToControl** action then moves the focus to the Category ID field, where you can begin to enter data for the new product. This macro should be attached to the Add Products button on the Suppliers form.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="3fe3a-133">Acción</span><span class="sxs-lookup"><span data-stu-id="3fe3a-133">Action</span></span></p></th>
<th><p><span data-ttu-id="3fe3a-134">Argumentos: Configuración</span><span class="sxs-lookup"><span data-stu-id="3fe3a-134">Arguments: Setting</span></span></p></th>
<th><p><span data-ttu-id="3fe3a-135">Comentario</span><span class="sxs-lookup"><span data-stu-id="3fe3a-135">Comment</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3fe3a-136"><strong>Eco</strong></span><span class="sxs-lookup"><span data-stu-id="3fe3a-136"><strong>Echo</strong></span></span></p></td>
<td><p><span data-ttu-id="3fe3a-137"><strong>Eco activo</strong>: <strong>No</strong></span><span class="sxs-lookup"><span data-stu-id="3fe3a-137"><strong>Echo On</strong>: <strong>No</strong></span></span></p></td>
<td><p><span data-ttu-id="3fe3a-138">Detener la actualización de la pantalla mientras se ejecuta la macro.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-138">Stop screen updating while the macro is running.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fe3a-139"><strong>CerrarVentana</strong></span><span class="sxs-lookup"><span data-stu-id="3fe3a-139"><strong>CloseWindow</strong></span></span></p></td>
<td><p><span data-ttu-id="3fe3a-140"><strong>Tipo de objeto</strong>: <strong>Nombre de FormObject</strong>: lista de producto <strong>Guardar</strong>: <strong>No</strong></span><span class="sxs-lookup"><span data-stu-id="3fe3a-140"><strong>Object Type</strong>: <strong>FormObject Name</strong>: Product List <strong>Save</strong>: <strong>No</strong></span></span></p></td>
<td><p><span data-ttu-id="3fe3a-141">Cerrar el formulario lista de productos.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-141">Close Product List form.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fe3a-142"><strong>AbrirFormulario</strong></span><span class="sxs-lookup"><span data-stu-id="3fe3a-142"><strong>OpenForm</strong></span></span></p></td>
<td><p><span data-ttu-id="3fe3a-143"><strong>Nombre del formulario</strong>: productos <strong>vista</strong>: <strong>Modo FormData</strong>: <strong>Modo AddWindow</strong>: <strong>Normal</strong></span><span class="sxs-lookup"><span data-stu-id="3fe3a-143"><strong>Form Name</strong>: Products <strong>View</strong>: <strong>FormData Mode</strong>: <strong>AddWindow Mode</strong>: <strong>Normal</strong></span></span></p></td>
<td><p><span data-ttu-id="3fe3a-144">Abrir el formulario Productos.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-144">Open the Products form.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fe3a-145"><strong>ConfigurarValor</strong></span><span class="sxs-lookup"><span data-stu-id="3fe3a-145"><strong>SetValue</strong></span></span></p></td>
<td><p><span data-ttu-id="3fe3a-146"><strong>Elemento</strong>: [Forms]![Products]![SupplierID] <strong>Expresión</strong>: IdProveedor</span><span class="sxs-lookup"><span data-stu-id="3fe3a-146"><strong>Item</strong>: [Forms]![Products]![SupplierID] <strong>Expression</strong>: SupplierID</span></span></p></td>
<td><p><span data-ttu-id="3fe3a-147">Configurar el control Id. de proveedor para el proveedor actual del formulario Proveedores.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-147">Set the Supplier ID control to the current supplier on the Suppliers form.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fe3a-148"><strong>IrAControl</strong></span><span class="sxs-lookup"><span data-stu-id="3fe3a-148"><strong>GoToControl</strong></span></span></p></td>
<td><p><span data-ttu-id="3fe3a-149"><strong>Nombre del control</strong>: IdCategoría</span><span class="sxs-lookup"><span data-stu-id="3fe3a-149"><strong>Control Name</strong>: CategoryID</span></span></p></td>
<td><p><span data-ttu-id="3fe3a-150">Ir al control Id. de categoría.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-150">Go to the Category ID control.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3fe3a-151">**Validar los datos con una macro**</span><span class="sxs-lookup"><span data-stu-id="3fe3a-151">**Validate data by using a macro**</span></span>

<span data-ttu-id="3fe3a-152">La siguiente macro de validación comprueba los códigos postales introducidos en el formulario Proveedores.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-152">The following validation macro checks the postal codes entered in a Suppliers form.</span></span> <span data-ttu-id="3fe3a-153">Muestra el uso de las acciones **DetenerMacro**, **CuadroDeMensajes**, **CancelarEvento** e **IrAControl**.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-153">It shows the use of the **StopMacro**, **MessageBox**, **CancelEvent**, and **GoToControl** actions.</span></span> <span data-ttu-id="3fe3a-154">Una expresión condicional comprueba el país o la región y el código postal especificados en un registro del formulario.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-154">A conditional expression checks the country/region and postal code entered in a record on the form.</span></span> <span data-ttu-id="3fe3a-155">Si el código postal no tiene el formato correcto para el país o la región, la macro muestra un cuadro de mensaje y cancela el proceso de guardar el registro.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-155">If the postal code is not in the right format for the country/region, the macro displays a message box and cancels saving the record.</span></span> <span data-ttu-id="3fe3a-156">A continuación, la macro devuelve, al control de código Postal, donde puede corregir el error.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-156">The macro then returns you to the Postal Code control, where you can correct the error.</span></span> <span data-ttu-id="3fe3a-157">Esta macro se debe adjuntar a la propiedad **BeforeUpdate** del formulario Proveedores.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-157">This macro should be attached to the **BeforeUpdate** property of the Suppliers form.</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="3fe3a-158">Condición</span><span class="sxs-lookup"><span data-stu-id="3fe3a-158">Condition</span></span></p></th>
<th><p><span data-ttu-id="3fe3a-159">Acción</span><span class="sxs-lookup"><span data-stu-id="3fe3a-159">Action</span></span></p></th>
<th><p><span data-ttu-id="3fe3a-160">Argumentos: Configuración</span><span class="sxs-lookup"><span data-stu-id="3fe3a-160">Arguments: Setting</span></span></p></th>
<th><p><span data-ttu-id="3fe3a-161">Comentario</span><span class="sxs-lookup"><span data-stu-id="3fe3a-161">Comment</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3fe3a-162">IsNull([PaísRegión])</span><span class="sxs-lookup"><span data-stu-id="3fe3a-162">IsNull([CountryRegion])</span></span></p></td>
<td><p><span data-ttu-id="3fe3a-163"><strong>DetenerMacro</strong></span><span class="sxs-lookup"><span data-stu-id="3fe3a-163"><strong>StopMacro</strong></span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="3fe3a-164">Si PaísRegión es <strong>nulo</strong>, no se puede validar el código postal.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-164">If CountryRegion is <strong>Null</strong>, postal code cannot be validated.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fe3a-165">[PaísRegión] En (&quot;Francia&quot;,&quot;Italia&quot;,&quot;España&quot;) y longitud ([CódigoPostal]) &lt; &gt; 5</span><span class="sxs-lookup"><span data-stu-id="3fe3a-165">[CountryRegion] In (&quot;France&quot;,&quot;Italy&quot;,&quot;Spain&quot;) And Len([Postal Code]) &lt;&gt; 5</span></span></p></td>
<td><p><span data-ttu-id="3fe3a-166"><strong>MessageBox</strong></span><span class="sxs-lookup"><span data-stu-id="3fe3a-166"><strong>MessageBox</strong></span></span></p></td>
<td><p><span data-ttu-id="3fe3a-167"><strong>Mensaje</strong>: el código postal debe ser de 5 caracteres.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-167"><strong>Message</strong>: The postal code must be 5 characters.</span></span> <span data-ttu-id="3fe3a-168"><strong>Bip</strong>: <strong>YesType</strong>: <strong>InformationTitle</strong>: Error de código Postal</span><span class="sxs-lookup"><span data-stu-id="3fe3a-168"><strong>Beep</strong>: <strong>YesType</strong>: <strong>InformationTitle</strong>: Postal Code Error</span></span></p></td>
<td><p><span data-ttu-id="3fe3a-169">Si el código postal no es 5 caracteres, se muestra un mensaje.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-169">If the postal code is not 5 characters, display a message.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fe3a-170">...</span><span class="sxs-lookup"><span data-stu-id="3fe3a-170"></span></span></p></td>
<td><p><span data-ttu-id="3fe3a-171"><strong>CancelarEvento</strong></span><span class="sxs-lookup"><span data-stu-id="3fe3a-171"><strong>CancelEvent</strong></span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="3fe3a-172">Cancelar el evento.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-172">Cancel the event.</span></span></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p><span data-ttu-id="3fe3a-173"><strong>IrAControl</strong></span><span class="sxs-lookup"><span data-stu-id="3fe3a-173"><strong>GoToControl</strong></span></span></p></td>
<td><p><span data-ttu-id="3fe3a-174"><strong>Nombre del control</strong>: CódigoPostal</span><span class="sxs-lookup"><span data-stu-id="3fe3a-174"><strong>Control Name</strong>: PostalCode</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fe3a-175">[PaísRegión] En (&quot;Australia&quot;,&quot;Singapur&quot;) y longitud ([CódigoPostal]) &lt; &gt; 4</span><span class="sxs-lookup"><span data-stu-id="3fe3a-175">[CountryRegion] In (&quot;Australia&quot;,&quot;Singapore&quot;) And Len([Postal Code]) &lt;&gt; 4</span></span></p></td>
<td><p><span data-ttu-id="3fe3a-176"><strong>MessageBox</strong></span><span class="sxs-lookup"><span data-stu-id="3fe3a-176"><strong>MessageBox</strong></span></span></p></td>
<td><p><span data-ttu-id="3fe3a-177">Mensaje: el código postal debe ser de 4 caracteres.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-177">Message: The postal code must be 4 characters.</span></span> <span data-ttu-id="3fe3a-178"><strong>Bip</strong>: <strong>YesType</strong>: <strong>InformationTitle</strong>: Error de código Postal</span><span class="sxs-lookup"><span data-stu-id="3fe3a-178"><strong>Beep</strong>: <strong>YesType</strong>: <strong>InformationTitle</strong>: Postal Code Error</span></span></p></td>
<td><p><span data-ttu-id="3fe3a-179">Si el código postal no es de 4 caracteres, se muestra un mensaje.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-179">If the postal code is not 4 characters, display a message.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fe3a-180">...</span><span class="sxs-lookup"><span data-stu-id="3fe3a-180"></span></span></p></td>
<td><p><span data-ttu-id="3fe3a-181"><strong>CancelarEvento</strong></span><span class="sxs-lookup"><span data-stu-id="3fe3a-181"><strong>CancelEvent</strong></span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="3fe3a-182">Cancelar el evento.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-182">Cancel the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="3fe3a-183"><strong>IrAControl</strong></span><span class="sxs-lookup"><span data-stu-id="3fe3a-183"><strong>GoToControl</strong></span></span></p></td>
<td><p><span data-ttu-id="3fe3a-184"><strong>Nombre del control</strong>: CódigoPostal</span><span class="sxs-lookup"><span data-stu-id="3fe3a-184"><strong>Control Name</strong>: PostalCode</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fe3a-185">([PaísRegión] = &quot;Canadá&quot;) Y ([CódigoPostal] no le gusta&quot;[A-z] [0-9] [A-z] [0-9] [A-z] [0-9]&quot;)</span><span class="sxs-lookup"><span data-stu-id="3fe3a-185">([CountryRegion] = &quot;Canada&quot;) And ([Postal Code] Not Like&quot;[A-Z][0-9][A-Z] [0-9][A-Z][0-9]&quot;)</span></span></p></td>
<td><p><span data-ttu-id="3fe3a-186"><strong>MessageBox</strong></span><span class="sxs-lookup"><span data-stu-id="3fe3a-186"><strong>MessageBox</strong></span></span></p></td>
<td><p><span data-ttu-id="3fe3a-187"><strong>Mensaje</strong>: El código postal no es válido.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-187"><strong>Message</strong>: The postal code is not valid.</span></span> <span data-ttu-id="3fe3a-188">Ejemplo de código de Canadá: H1J 1C3 <strong>Bip</strong>: <strong>YesType</strong>: <strong>InformationTitle</strong>: Error de código Postal</span><span class="sxs-lookup"><span data-stu-id="3fe3a-188">Example of Canadian code: H1J 1C3 <strong>Beep</strong>: <strong>YesType</strong>: <strong>InformationTitle</strong>: Postal Code Error</span></span></p></td>
<td><p><span data-ttu-id="3fe3a-189">Si el código postal no es correcto para Canadá, mostrar un mensaje.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-189">If the postal code is not correct for Canada, display a message.</span></span> <span data-ttu-id="3fe3a-190">(Ejemplo de código canadiense: H1J 1C3)</span><span class="sxs-lookup"><span data-stu-id="3fe3a-190">(Example of Canadian code: H1J 1C3)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fe3a-191">...</span><span class="sxs-lookup"><span data-stu-id="3fe3a-191"></span></span></p></td>
<td><p><span data-ttu-id="3fe3a-192"><strong>CancelarEvento</strong></span><span class="sxs-lookup"><span data-stu-id="3fe3a-192"><strong>CancelEvent</strong></span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="3fe3a-193">Cancelar el evento.</span><span class="sxs-lookup"><span data-stu-id="3fe3a-193">Cancel the event.</span></span></p></td>
</tr>
</tbody>
</table>
