---
title: ProvocarError (acción de macro)
TOCTitle: RaiseError Macro Action
ms:assetid: c8c57685-b373-67d6-cea6-8f2c334547d3
ms:mtpsurl: https://msdn.microsoft.com/library/Ff823192(v=office.15)
ms:contentKeyID: 48547661
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 134222e825826615feb495adaae6296229edb868
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25483837"
---
# <a name="raiseerror-macro-action"></a>ProvocarError (acción de macro)

**Se aplica a**: Access 2013 | Office 2013 

La acción **ProvocarError** produce una excepción que se puede controlar mediante la acción de macro **[AlOcurrirError](onerror-macro-action.md)**.

> [!NOTE]
> [!NOTA] La acción **ProvocarError** solo está disponible en macros de datos.

## <a name="setting"></a>Valores

La acción **ProvocarError** utiliza los siguientes argumentos.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Argumento</p></th>
<th><p>Obligatorio</p></th>
<th><p>Descripción</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Número de error </p></td>
<td><p>Sí</p></td>
<td><p>Un número o una expresión que da como resultado el tipo de datos Long .</p></td>
</tr>
<tr class="even">
<td><p>Descripción del error</p></td>
<td><p>No</p></td>
<td><p>Una expresión de cadena que describe el error.</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>Comentarios

Si se llama a la acción **ProvocarError** en un evento de macro **[Cambio previo](before-change-macro-event.md)** o **[Eliminación previa](before-delete-macro-event.md)**, se cancela el evento.

Si no hay ninguna instrucción **AlOcurrirError** activa que esté controlando los errores, el error provocado por la acción **ProvocarError** se agrega a la tabla de sistema **USysApplicationLog**. Cuando la acción **ProvocarError** se escribe en la tabla **USysApplicationLog**, la columna **Categoría** se establece automáticamente en **Ejecución**.

Para ver la tabla **USysApplicationLog**, siga estos pasos:

1.  Haga clic en el menú **archivo** y, a continuación, haga clic en **Opciones**.

2.  En el cuadro de diálogo **Opciones de Access**, haga clic en la pestaña **Base de datos actual**.

3.  En la sección **Navegación**, haga clic en **Opciones de navegación**.

4.  En el cuadro de diálogo **Opciones de navegación**, haga clic en **Mostrar objetos del sistema** y, a continuación, haga clic en **Aceptar**.

5.  Haga clic en **Aceptar** para descartar el cuadro de diálogo **Opciones de Access**.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo usar la acción Provocarerror para cancelar el evento de macro de datos antes de cambiar. Cuando se actualiza el campo AssignedTo, un bloque de datos BuscarRegistro se usa para determinar si el técnico asignado actualmente está asignado a una solicitud de servicio abiertas. Si es true, a continuación, se cancela el evento cambio previo y no se actualiza el registro.

**Código de ejemplo proporcionado por** la [referencia del programador de Microsoft Access 2010](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).

```vb
    /* Get the name of the technician  */
    Look Up A Record In tblTechnicians
        Where Condition =[tblTechnicians].[ID]=[tblServiceRequests].[AssignedTo]
    SetLocalVar
        Name TechName
        Expression [tblTechnicians].[FirstName] & " " & [tblTechnicians].[LastName]
    /* End LookUpRecord  */
    
    If Updated("AssignedTo") Then
        Look Up A Record In tblServiceRequests
            Where Condition SR.[AssignedTo]=tblServiceRequests[AssignedTo] And 
                SR.[ID]<>tblServiceRequests.[ID] And IsNull(SR.[ActualCompletionDate])
            Alias SR
            RaiseError
                Error Number 1234
                Error Description ="Cannot assign a request to the specified technician: " & [TechName]
    
    End If
```
