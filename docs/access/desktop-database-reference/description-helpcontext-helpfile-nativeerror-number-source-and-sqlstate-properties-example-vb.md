---
<<<<<<< Título HEAD: Description, ContextoDeAyuda (HelpContext), HelpFile propiedades ejemplo (VB) TOCTitle: Description, ContextoDeAyuda (HelpContext), HelpFile, NativeError, número, origen y ejemplo de las propiedades SQLState (VB) === título: descripción, ContextoDeAyuda (HelpContext), ejemplo de las propiedades HelpFile (VB) TOCTitle: ejemplo de las propiedades Description, ContextoDeAyuda (HelpContext), HelpFile, NativeError, número, origen y SQLState (VB)
>>>>>>> Master ms:assetid: 3c129aec-cd69-5822-4dad-ebef226538e1 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249156(v=office.15) ms:contentKeyID: ms.date 48544304: 18/09/2015 mtps_version: Office.15
---

<<<<<<< HEAD
# <a name="description-helpcontext-helpfile-nativeerror-number-source-and-sqlstate-properties-example-vb"></a>Ejemplo de las propiedades Description, HelpContext, HelpFile, NativeError, Number, Source y SQLState (VB)
=======
# <a name="description-helpcontext-helpfile-nativeerror-number-source-and-sqlstate-properties-example-vb"></a>Ejemplo de las propiedades Description, ContextoDeAyuda (HelpContext), HelpFile, NativeError, número, origen y SQLState (VB)
>>>>>>> master


**Se aplica a**: Access 2013 | Office 2013

Este ejemplo desencadena un error, lo captura y muestra las propiedades [Description](description-property-ado.md), [ContextoDeAyuda (HelpContext)](helpcontext-helpfile-properties-ado.md), [HelpFile](helpcontext-helpfile-properties-ado.md), [NativeError](nativeerror-property-ado.md), [Number](number-property-ado.md), [Source](source-property-ado-error.md) y [SQLState](sqlstate-property-ado.md) del objeto [Error](error-object-ado.md) resultante.

```vb
    'BeginDescriptionVB
    Public Sub Main()
    
        Dim Cnxn As ADODB.Connection
        Dim Err As ADODB.Error
        Dim strError As String
        
        On Error GoTo ErrorHandler
        
        ' Intentionally trigger an error
        Set Cnxn = New ADODB.Connection
        Cnxn.Open "nothing"
        
        Set Cnxn = Nothing
        Exit Sub
    
    ErrorHandler:
    
        ' Enumerate Errors collection and display
        ' properties of each Error object
        For Each Err In Cnxn.Errors
            strError = "Error #" & Err.Number & vbCr & _
                "   " & Err.Description & vbCr & _
                "   (Source: " & Err.Source & ")" & vbCr & _
                "   (SQL State: " & Err.SQLState & ")" & vbCr & _
                "   (NativeError: " & Err.NativeError & ")" & vbCr
            If Err.HelpFile = "" Then
                strError = strError & "   No Help file available"
            Else
                strError = strError & _
                   "   (HelpFile: " & Err.HelpFile & ")" & vbCr & _
                   "   (HelpContext: " & Err.HelpContext & ")" & _
                   vbCr & vbCr
            End If
             
            Debug.Print strError
        Next
    
        Resume Next
    End Sub
    'EndDescriptionVB
```
