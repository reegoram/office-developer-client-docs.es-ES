---
title: BuscarRegistro (acción de macro)
TOCTitle: FindRecord Macro Action
ms:assetid: 379e3dda-cb7d-a294-29b1-c6ce9a62ba8a
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192494(v=office.15)
ms:contentKeyID: 48544199
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm7496
f1_categories:
- Office.Version=v15
ms.openlocfilehash: d62c80c18ffd091d71c88fc64c9bd5c60c580101
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25486781"
---
# <a name="findrecord-macro-action"></a><span data-ttu-id="02a6c-102">BuscarRegistro (acción de macro)</span><span class="sxs-lookup"><span data-stu-id="02a6c-102">FindRecord Macro Action</span></span>


<span data-ttu-id="02a6c-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="02a6c-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="02a6c-p101">Puede usar la acción **BuscarRegistro** para buscar la primera instancia de los datos que cumplan los criterios especificados por los argumentos de **BuscarRegistro**. Estos datos se pueden encontrar en el registro activo, en un registro anterior o posterior, o bien, en el primer registro. Puede buscar registros en la hoja de datos de la tabla, la hoja de datos de la consulta, la hoja de datos del formulario o el formulario que esté activo.</span><span class="sxs-lookup"><span data-stu-id="02a6c-p101">You can use the **FindRecord** action to find the first instance of data that meets the criteria specified by the **FindRecord** arguments. This data can be in the current record, in a succeeding or prior record, or in the first record. You can find records in the active table datasheet, query datasheet, form datasheet, or form.</span></span>

## <a name="setting"></a><span data-ttu-id="02a6c-107">Configuración</span><span class="sxs-lookup"><span data-stu-id="02a6c-107">Setting</span></span>

<span data-ttu-id="02a6c-108">La acción **BuscarRegistro** tiene los siguientes argumentos.</span><span class="sxs-lookup"><span data-stu-id="02a6c-108">The **FindRecord** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="02a6c-109">Argumento de la acción</span><span class="sxs-lookup"><span data-stu-id="02a6c-109">Action argument</span></span></p></th>
<th><p><span data-ttu-id="02a6c-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="02a6c-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02a6c-111"><strong>Buscar</strong></span><span class="sxs-lookup"><span data-stu-id="02a6c-111"><strong>Find What</strong></span></span></p></td>
<td><p><span data-ttu-id="02a6c-112">Especifica los datos que se desean buscar en el registro.</span><span class="sxs-lookup"><span data-stu-id="02a6c-112">Specifies the data you want to find in the record.</span></span> <span data-ttu-id="02a6c-113">Escriba el texto, número o fecha que desea buscar o escriba una expresión, está precedida por un signo igual (<strong>=</strong>), en el cuadro <strong>Buscar</strong> en la sección <strong>Argumentos de acción</strong> del panel Generador de macros.</span><span class="sxs-lookup"><span data-stu-id="02a6c-113">Enter the text, number, or date you want to find or type an expression, which is preceded by an equal sign (<strong>=</strong>), in the <strong>Find What</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane.</span></span> <span data-ttu-id="02a6c-114">Puede usar caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="02a6c-114">You can use wildcard characters.</span></span> <span data-ttu-id="02a6c-115">Este argumento es necesario.</span><span class="sxs-lookup"><span data-stu-id="02a6c-115">This is a required argument.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02a6c-116"><strong>Coincidir</strong></span><span class="sxs-lookup"><span data-stu-id="02a6c-116"><strong>Match</strong></span></span></p></td>
<td><p><span data-ttu-id="02a6c-p103">Especifica dónde están ubicados los datos en el campo. Puede especificar una búsqueda de datos en cualquier parte del campo (<strong>Cualquier parte del campo</strong>), datos que llenen todo el campo (<strong>Hacer coincidir todo el campo</strong>) o datos ubicados al principio del campo (<strong>Comienzo del campo</strong>). El valor predeterminado es <strong>Hacer coincidir todo el campo</strong>.</span><span class="sxs-lookup"><span data-stu-id="02a6c-p103">Specifies where the data is located in the field. You can specify a search for data in any part of the field (<strong>Any Part of Field</strong>), for data that fills the entire field (<strong>Whole Field</strong>), or for data located at the beginning of the field (<strong>Start of Field</strong>). The default is <strong>Whole Field</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02a6c-120"><strong>Coincidir mayúsculas y minúsculas</strong></span><span class="sxs-lookup"><span data-stu-id="02a6c-120"><strong>Match Case</strong></span></span></p></td>
<td><p><span data-ttu-id="02a6c-p104">Especifica si en la búsqueda se hace distinción de mayúsculas y minúsculas. Haga clic en <strong>Sí</strong> (para llevar a cabo una búsqueda en la que coincidan las mayúsculas y minúsculas) o <strong>No</strong> (para buscar sin que coincidan exactamente las letras mayúsculas y minúsculas). El valor predeterminado es <strong>No</strong>.  </span><span class="sxs-lookup"><span data-stu-id="02a6c-p104">Specifies whether the search is case-sensitive. Click <strong>Yes</strong> (conduct a case-sensitive search) or <strong>No</strong> (search without matching uppercase and lowercase letters exactly). The default is <strong>No</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02a6c-124"><strong>Buscar</strong></span><span class="sxs-lookup"><span data-stu-id="02a6c-124"><strong>Search</strong></span></span></p></td>
<td><p><span data-ttu-id="02a6c-p105">Especifica si la búsqueda se produce desde el registro activo hacia el principio de los registros (<strong>Arriba</strong>), hacia abajo hasta el final de los registros (<strong>Abajo</strong>), o bien, desde el registro activo hacia el final de los registros y luego desde el principio de los registros hasta el registro activo, de forma que se busque en todos los registros (<strong>Todos</strong>). El valor predeterminado es <strong>Todos</strong>.</span><span class="sxs-lookup"><span data-stu-id="02a6c-p105">Specifies whether the search proceeds from the current record up to the beginning of the records (<strong>Up</strong>); down to the end of the records (<strong>Down</strong>); or down to the end of the records and then from the beginning of the records to the current record, so all records are searched (<strong>All</strong>). The default is <strong>All</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02a6c-127"><strong>Buscar con formato</strong></span><span class="sxs-lookup"><span data-stu-id="02a6c-127"><strong>Search As Formatted</strong></span></span></p></td>
<td><p><span data-ttu-id="02a6c-p106">Especifica si la búsqueda incluye datos con formato. Haga clic en <strong>Sí</strong> (Microsoft Office Access 2007 busca los datos con el formato y tal y como se muestran en el campo) o <strong>No</strong> (Access busca los datos tal y cómo se almacenan en la base de datos, que no siempre son los mismos que se muestran). El valor predeterminado es <strong>No</strong>. Puede usar esta característica para restringir la búsqueda a los datos con un formato concreto. Por ejemplo, haga clic en <strong>Sí</strong> y escriba <strong>1,234</strong> en el argumento <strong>Buscar</strong> para buscar un valor de 1,234 en el campo con formato para incluir comas. Haga clic en <strong>No</strong> si quiere escribir <strong>1234</strong> para buscar los datos de este campo. Para buscar fechas, haga clic en <strong>Sí</strong> para buscar una fecha exacta con el formato exacto, como 08-Julio-2003. Si hace clic en <strong>No</strong>, escriba la fecha para el argumento <strong>Buscar</strong> con el formato configurado en la configuración regional del Panel de control de Windows. Este formato se muestra en el cuadro <strong>Formato de fecha corta</strong> de la pestaña <strong>Fecha</strong> de la configuración regional. Por ejemplo, si el cuadro <strong>Formato de fecha corta</strong> está configurado en <strong>M/d/aa</strong>, puede escribir 7/8/03 y Access buscará todas las entradas de un campo Fecha que se correspondan al 8 de julio de 2003, independientemente del formato que tenga el campo.  </span><span class="sxs-lookup"><span data-stu-id="02a6c-p106">Specifies whether the search includes formatted data. Click <strong>Yes</strong> (Microsoft Office Access 2007 searches for the data as it is formatted and displayed in the field) or <strong>No</strong> (Access searches for the data as it is stored in the database, which isn't always the same as it's displayed). The default is <strong>No</strong>. You can use this feature to restrict the search to data in a particular format. For example, click <strong>Yes</strong> and type <strong>1,234</strong> in the <strong>Find What</strong> argument to find a value of 1,234 in a field formatted to include commas. Click <strong>No</strong> if you want to type <strong>1234</strong> to search for the data in this field. To search for dates, click <strong>Yes</strong> to find a date exactly as it is formatted, such as 08-July-2003. If you click <strong>No</strong>, enter the date for the <strong>Find What</strong> argument in the format that is set in the regional settings in Windows Control Panel. This format is shown in the <strong>Short date format</strong> box found on the <strong>Date</strong> tab in the regional settings. For example, if the <strong>Short date format</strong> box is set to <strong>M/d/yy</strong>, you can enter 7/8/03, and Access will find all entries in a Date field that correspond to July 8, 2003, regardless of how this field is formatted.</span></span></p>

> [!NOTE]
> <P><span data-ttu-id="02a6c-138">El argumento <STRONG>Buscar con formato</STRONG> sólo tiene efecto si el campo activo es un control dependiente, el argumento <STRONG>Coincidir</STRONG> está establecido en <STRONG>Hacer coincidir todo el campo</STRONG>, el argumento <STRONG>Sólo el campo activo</STRONG> está establecido en <STRONG>Sí</STRONG> y el argumento <STRONG>Coincidir mayúsculas y minúsculas</STRONG> está establecido en <STRONG>No</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="02a6c-138">The <STRONG>Search As Formatted</STRONG> argument takes effect only if the current field is a bound control, the <STRONG>Match</STRONG> argument is set to <STRONG>Whole Field</STRONG>, the <STRONG>Only Current Field</STRONG> argument is set to <STRONG>Yes</STRONG>, and the <STRONG>Match Case</STRONG> argument is set to <STRONG>No</STRONG>.</span></span></P>


<p><span data-ttu-id="02a6c-139">

					Si establece <strong>Coincidir mayúsculas y minúsculas</strong> en <strong>Sí</strong> o <strong>Sólo el campo activo</strong> en <strong>No</strong>, también debe establecer <strong>Buscar con formato</strong> en <strong>Sí</strong>.

</span><span class="sxs-lookup"><span data-stu-id="02a6c-139">If you set <strong>Match Case</strong> to <strong>Yes</strong> or <strong>Only Current Field</strong> to <strong>No</strong>, you must also set <strong>Search As Formatted</strong> to <strong>Yes</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02a6c-140"><strong>Sólo campo activo</strong></span><span class="sxs-lookup"><span data-stu-id="02a6c-140"><strong>Only Current Field</strong></span></span></p></td>
<td><p><span data-ttu-id="02a6c-p107">Especifica si la búsqueda está restringida al campo activo en cada registro o si incluye todos los campos. La búsqueda en el campo activo es más rápida. Haga clic en <strong>Sí</strong> (restringir búsqueda a campo activo) o <strong>No</strong> (búsqueda en todos los campos en cada registro). El valor predeterminado es <strong>Sí</strong>.  </span><span class="sxs-lookup"><span data-stu-id="02a6c-p107">Specifies whether the search is confined to the current field in each record or includes all fields in each record. Searching in the current field is faster. Click <strong>Yes</strong> (confine the search to the current field) or <strong>No</strong> (search in all fields in each record). The default is <strong>Yes</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02a6c-145"><strong>Buscar primero</strong></span><span class="sxs-lookup"><span data-stu-id="02a6c-145"><strong>Find First</strong></span></span></p></td>
<td><p><span data-ttu-id="02a6c-p108">Especifica si la búsqueda comienza en el primer registro o en el registro activo. Haga clic en <strong>Sí</strong> (para empezar en el primer registro) o <strong>No</strong> (para empezar en el registro activo). El valor predeterminado es <strong>Sí</strong>.  </span><span class="sxs-lookup"><span data-stu-id="02a6c-p108">Specifies whether the search starts at the first record or at the current record. Click <strong>Yes</strong> (start at the first record) or <strong>No</strong> (start at the current record). The default is <strong>Yes</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="02a6c-149">Comentarios</span><span class="sxs-lookup"><span data-stu-id="02a6c-149">Remarks</span></span>

<span data-ttu-id="02a6c-p109">Cuando una macro ejecuta la acción **BuscarRegistro**, Access busca los datos especificados en los registros (el orden de la búsqueda viene determinado por el valor del argumento **Buscar** ). Cuando Access encuentra los datos especificados, se seleccionan los datos en el registro.</span><span class="sxs-lookup"><span data-stu-id="02a6c-p109">When a macro runs the **FindRecord** action, Access searches for the specified data in the records (the order of the search is determined by the setting of the **Search** argument). When Access finds the specified data, the data is selected in the record.</span></span>

<span data-ttu-id="02a6c-p110">La acción **BuscarRegistro** es equivalente a hacer clic en **Buscar** en la ficha **Inicio**, y sus argumentos son los mismos que las opciones del cuadro de diálogo **Buscar y reemplazar**. Si establece los argumentos de **BuscarRegistro** en el panel Generador de macros y, a continuación, ejecuta la macro, verá las correspondientes opciones seleccionadas en el cuadro de diálogo **Buscar y reemplazar** cuando haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="02a6c-p110">The **FindRecord** action is equivalent to clicking **Find** on the **Home** tab, and its arguments are the same as the options in the **Find and Replace** dialog box. If you set the **FindRecord** arguments in the Macro Builder pane and then run the macro, you will see the corresponding options selected in the **Find and Replace** dialog box when you click **Find**.</span></span>

<span data-ttu-id="02a6c-p111">Access conserva los argumentos más recientes de **BuscarRegistro** durante una sesión de la base de datos, por lo que no es necesario escribir repetidas veces los mismos criterios cuando se realizan operaciones posteriores con la acción **BuscarRegistro**. Si deja un argumento en blanco, Access utiliza el valor más reciente del argumento, establecido por una acción **BuscarRegistro** anterior o en el cuadro de diálogo **Buscar y reemplazar**.</span><span class="sxs-lookup"><span data-stu-id="02a6c-p111">Access retains the most recent **FindRecord** arguments during a database session so that you don't need to enter the same criteria repeatedly as you perform subsequent operations with the **FindRecord** action. If you leave an argument blank, Access uses the most recent setting for the argument, as set either by a previous **FindRecord** action or in the **Find and Replace** dialog box.</span></span>

<span data-ttu-id="02a6c-156">Cuando desee buscar un registro mediante una macro, utilice la acción **BuscarRegistro** en lugar de la acción **EjecutarComandoDeMenú** con su argumento establecido para que se ejecute el comando **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="02a6c-156">When you want to find a record by using a macro, use the **FindRecord** action, not the **RunMenuCommand** action with its argument set to run the **Find** command.</span></span>


> [!NOTE]
> <P><span data-ttu-id="02a6c-p112">[!NOTA] Si bien la acción <STRONG>BuscarRegistro</STRONG> corresponde al comando <STRONG>Buscar</STRONG> en la ficha <STRONG>Inicio</STRONG> de tablas, consultas y formularios, no corresponde al comando <STRONG>Buscar</STRONG> del menú <STRONG>Edición</STRONG> en la ventana Código. No se puede utilizar la acción <STRONG>BuscarRegistro</STRONG> para buscar texto en módulos.</span><span class="sxs-lookup"><span data-stu-id="02a6c-p112">While the <STRONG>FindRecord</STRONG> action corresponds to the <STRONG>Find</STRONG> command on the <STRONG>Home</STRONG> tab for tables, queries, and forms, it doesn't correspond to the <STRONG>Find</STRONG> command on the <STRONG>Edit</STRONG> menu in the Code window. You can't use the <STRONG>FindRecord</STRONG> action to search for text in modules.</span></span></P>



<span data-ttu-id="02a6c-p113">Si el texto actualmente seleccionado es el mismo que el texto seleccionado en el momento en el que se ejecuta la acción **BuscarRegistro**, la búsqueda se inicia inmediatamente después de la selección en el mismo campo que la selección y en el mismo registro. En caso contrario, la búsqueda se inicia al principio del registro actual. Esto permite buscar múltiples instancias de los mismos criterios de búsqueda que pudieran aparecer en un único registro.</span><span class="sxs-lookup"><span data-stu-id="02a6c-p113">If the currently selected text is the same as the search text at the time the **FindRecord** action is carried out, the search begins immediately following the selection in the same field as the selection, and in the same record. Otherwise, the search begins at the start of the current record. This enables you to find multiple instances of the same search criteria that might appear in a single record.</span></span>

<span data-ttu-id="02a6c-p114">Sin embargo, observe que si usa un botón de comando para ejecutar una macro que contenga la acción **BuscarRegistro**, se buscará de forma repetida la primera instancia de los criterios de búsqueda. Este comportamiento se debe a que, al hacer clic en el botón de comando, se quita el enfoque del campo que contiene el valor coincidente. La acción **BuscarRegistro** empezará la búsqueda desde el principio del registro. Para evitar este problema, ejecute la macro usando una técnica que no cambie el enfoque, como un botón de una barra de herramientas personalizada o una combinación de teclas definida en una macro AutoKeys. O bien, establezca el enfoque de la macro en el campo que contiene los criterios de búsqueda antes de llevar a cabo la acción **BuscarRegistro**.</span><span class="sxs-lookup"><span data-stu-id="02a6c-p114">However, note that if you use a command button to run a macro containing the **FindRecord** action, the first instance of the search criteria will be found repeatedly. This behavior occurs because clicking the command button removes the focus from the field containing the matching value. The **FindRecord** action will then begin searching from the start of the record. To avoid this problem, run the macro by using a technique that doesn't change the focus, such as a custom toolbar button or a key combination defined in an AutoKeys macro, or set the focus in the macro to the field containing the search criteria before you carry out the **FindRecord** action.</span></span>

<table>
<thead>
<tr class="header">
<th><img src="media/access-alert-security.gif" title="Nota de seguridad" alt="Security note" /><span data-ttu-id="02a6c-167">de seguridad\*\*</span><span class="sxs-lookup"><span data-stu-id="02a6c-167"><strong>Security Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="02a6c-p115">
      No use la declaración <strong>SendKeys</strong> ni una macro AutoKeys con información sensible o confidencial porque un usuario malintencionado podría interceptar las pulsaciones de teclas y vulnerar la seguridad de su equipo y de sus datos.
</span><span class="sxs-lookup"><span data-stu-id="02a6c-p115">Avoid using the <strong>SendKeys</strong> statement or an AutoKeys macro with sensitive or confidential information. A malicious user could intercept the keystrokes and compromise the security of your computer and data.</span></span></td>
</tr>
</tbody>
</table>


<span data-ttu-id="02a6c-170">El mismo comportamiento se produce si usa un botón de comando para ejecutar una macro que contenga la acción **BuscarSiguiente**.</span><span class="sxs-lookup"><span data-stu-id="02a6c-170">The same behavior also occurs if you use a command button to run a macro containing the **FindNext** action.</span></span>

<span data-ttu-id="02a6c-171">Para ejecutar la acción **BuscarRegistro** en un módulo de Visual Basic para Aplicaciones (VBA), use el método **FindRecord** del objeto **DoCmd**.</span><span class="sxs-lookup"><span data-stu-id="02a6c-171">To run the **FindRecord** action in a Visual Basic for Applications (VBA) module, use the **FindRecord** method of the **DoCmd** object.</span></span>

<span data-ttu-id="02a6c-172">Para realizar búsquedas más complejas, conviene usar la macro de acción **EncontrarRegistro**.</span><span class="sxs-lookup"><span data-stu-id="02a6c-172">For more complex searches, you may want to use the **SearchForRecord** macro action.</span></span>
