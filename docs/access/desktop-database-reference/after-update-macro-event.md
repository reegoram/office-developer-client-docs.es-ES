---
title: Después de actualizar (evento de macro)
TOCTitle: After Update Macro Event
ms:assetid: 5213793b-8301-0f18-3a12-4e3764c879ac
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193905(v=office.15)
ms:contentKeyID: 48544838
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm85126
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 2927a3ede26487cabf9986b301cfc0617ba155c6
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25486674"
---
# <a name="after-update-macro-event"></a>Después de actualizar (evento de macro)


**Se aplica a**: Access 2013 | Office 2013

El evento **Después de actualizar** se produce después de actualizar un registro.


> [!NOTE]
> <P>[!NOTA] El evento <STRONG>Después de actualizar</STRONG> solo está disponible en macros de datos.</P>



## <a name="remarks"></a>Comentarios

Utilice el evento **Después de actualizar** para realizar cualquier acción que desee que se produzca cuando se cambia un registro. **Después de actualizar** se suele utilizar para exigir reglas de negocio, flujos de trabajo, actualizar un total agregado y enviar notificaciones.

Puede utilizar la función **Updated("*Nombre del campo*")** para determinar si un campo ha cambiado. En el ejemplo de código siguiente se muestra cómo utilizar una instrucción **If** para determinar si se ha cambiado el campo PaidInFull.

```vb 
 
If  Updated("PaidInFull")   Then 
 
    /* Perform actions based on changes to the field.   */ 
 
End If 
 
```

Puede obtener acceso al valor anterior de un campo mediante la sintaxis siguiente.

`[Old].[Field Name]`

Por ejemplo, para tener acceso al valor anterior del campo QuantityInStock, utilice la sintaxis siguiente.

`[Old].[QuantityInStock]`

Los valores anteriores se eliminan permanentemente cuando finaliza el evento **Después de actualizar**.

La siguiente tabla enumera los comandos de macro que pueden utilizarse en el evento **Después de actualizar**.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Tipo de comando</p></th>
<th><p>Comando</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Flujo de programas</p></td>
<td><p><a href="comment-macro-statement.md">Comentario (instrucción de macro)</a></p></td>
</tr>
<tr class="even">
<td><p>Flujo de programas</p></td>
<td><p><a href="group-macro-statement.md">Grupo (instrucción de macro)</a></p></td>
</tr>
<tr class="odd">
<td><p>Flujo de programas</p></td>
<td><p><a href="if-then-else-macro-block.md">Si...Entonces...Sino (bloque de macro)</a></p></td>
</tr>
<tr class="even">
<td><p>Bloque de datos</p></td>
<td><p><a href="createrecord-data-block.md">CrearRegistro (acción de macro)</a></p></td>
</tr>
<tr class="odd">
<td><p>Bloque de datos</p></td>
<td><p><a href="editrecord-data-block.md">EditarRegistro (acción de macro)</a></p></td>
</tr>
<tr class="even">
<td><p>Bloque de datos</p></td>
<td><p><a href="foreachrecord-data-block.md">ParaCadaRegistro (acción de macro)</a></p></td>
</tr>
<tr class="odd">
<td><p>Bloque de datos</p></td>
<td><p><a href="lookuprecord-data-block.md">BuscarRegistro (bloque de datos)</a></p></td>
</tr>
<tr class="even">
<td><p>Acción de datos</p></td>
<td><p><a href="cancelrecordchange-macro-action.md">CancelarCambioDeRegistro (acción de macro)</a></p></td>
</tr>
<tr class="odd">
<td><p>Acción de datos</p></td>
<td><p><a href="clearmacroerror-macro-action.md">BorrarErrorDeMacro (acción de macro)</a></p></td>
</tr>
<tr class="even">
<td><p>Acción de datos</p></td>
<td><p><a href="deleterecord-macro-action.md">EliminarRegistro (acción de macro)</a></p></td>
</tr>
<tr class="odd">
<td><p>Acción de datos</p></td>
<td><p><a href="exitforeachrecord-macro-action.md">SalirDeCadaRegistro (acción de macro)</a></p></td>
</tr>
<tr class="even">
<td><p>Acción de datos</p></td>
<td><p><a href="logevent-macro-action.md">RegistrarEvento (acción de macro)</a></p></td>
</tr>
<tr class="odd">
<td><p>Acción de datos</p></td>
<td><p><a href="onerror-macro-action.md">AlOcurrirError (acción de macro)</a></p></td>
</tr>
<tr class="even">
<td><p>Acción de datos</p></td>
<td><p><a href="raiseerror-macro-action.md">ProvocarError (acción de macro)</a></p></td>
</tr>
<tr class="odd">
<td><p>Acción de datos</p></td>
<td><p><a href="rundatamacro-macro-action.md">EjecutarMacroDeDatos (acción de macro)</a></p></td>
</tr>
<tr class="even">
<td><p>Acción de datos</p></td>
<td><p><a href="sendemail-macro-action.md">EnviarCorreoElectrónico (acción de macro)</a></p></td>
</tr>
<tr class="odd">
<td><p>Acción de datos</p></td>
<td><p><a href="setfield-macro-action.md">EstablecerCampo (acción de macro)</a></p></td>
</tr>
<tr class="even">
<td><p>Acción de datos</p></td>
<td><p><a href="setlocalvar-macro-action.md">EstablecerVariableLocal (acción de macro)</a></p></td>
</tr>
<tr class="odd">
<td><p>Acción de datos</p></td>
<td><p><a href="stopallmacros-macro-action.md">DetenerTodasMacros (acción de macro)</a></p></td>
</tr>
<tr class="even">
<td><p>Acción de datos</p></td>
<td><p><a href="stopmacro-macro-action.md">DetenerMacro (acción de macro)</a></p></td>
</tr>
</tbody>
</table>


Para crear una macro de datos que capture el evento **Después de actualizar**, utilice los pasos siguientes.

1.  Abra la tabla en la que desee capturar el evento **Después de actualizar**.

2.  En la ficha **Tabla**, en el grupo **Eventos posteriores**, haga clic en **Después de actualizar**.

Una macro de datos vacía se muestra en el Diseñador de macros.

## <a name="example"></a>Ejemplo

En el ejemplo de código siguiente se utiliza el evento **Después de actualizar** para ejecutar una macro de datos con nombre que agrega un registro a la tabla Comentario cada vez que se actualiza el estado de un problema.

**Haga clic aquí para ver una copia de la macro que puede pegar en el Diseñador de macros.**

Para ver este ejemplo en el Diseñador de macros, utilice los pasos siguientes.

1.  Abra la tabla en la que desee capturar el evento **Después de actualizar**.

2.  En la ficha **Tabla**, en el grupo **Eventos posteriores**, haga clic en **Después de actualizar**.

3.  Seleccione el código en el siguiente ejemplo de código y, a continuación, presione CTRL+C para copiarlo al Portapapeles.

4.  Active la ventana del Diseñador de macros y, a continuación, presione CTRL+V.

<!-- end list -->

```xml
    <DataMacros xmlns="https://schemas.microsoft.com/office/accessservices/2009/04/application"> 
      <DataMacro Event="AfterUpdate"> 
        <Statements> 
          <ConditionalBlock> 
            <If> 
              <Condition>Updated("Status")</Condition> 
              <Statements> 
                <Action Name="RunDataMacro"> 
                  <Argument Name="MacroName">Comments.AddComment</Argument> 
                  <Parameters> 
                    <Parameter Name="prmRelatedID" Value="[ID]" /> 
                    <Parameter Name="prmComment" Value="&quot;-- Status changed to &quot; &amp; [Status]" /> 
                    <Parameter Name="prmUserID" Value="[UserID]" /> 
                  </Parameters> 
                </Action> 
              </Statements> 
            </If> 
          </ConditionalBlock> 
          <ConditionalBlock> 
            <If> 
              <Condition>Updated("Resolution")</Condition> 
              <Statements> 
                <Action Name="RunDataMacro"> 
                  <Argument Name="MacroName">Comments.AddComment</Argument> 
                  <Parameters> 
                    <Parameter Name="prmRelatedID" Value="[ID]" /> 
                    <Parameter Name="prmUserID" Value="[UserID]" /> 
                    <Parameter Name="prmComment" Value="&quot;-- Issue resolved as &quot; &amp; [Resolution]" /> 
                  </Parameters> 
                </Action> 
              </Statements> 
            </If> 
          </ConditionalBlock> 
        </Statements> 
      </DataMacro> 
    </DataMacros>
``` 

<br/>

```vb
If  Updated("Status")   Then 
     RunDataMacro 
        Macro Name   Comments.AddComment 
     Parameters 
       prmRelatedID   = [ID] 
         prmComment   ="--Status Changes to "&[Status] 
          prmUserID   =[ChangedByUserID] 
End If 
 
If   Updated("Resolution")   Then 
     RunDataMacro 
        Macro Name   Comments.AddComment 
     Parameters 
       prmRelatedID   = [ID] 
          prmUserID   =[ChangedByUserID] 
         prmComment   ="--Issue Resolved as "&[Status] 
End If 
```

