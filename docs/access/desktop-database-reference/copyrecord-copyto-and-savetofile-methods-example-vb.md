---
title: Ejemplo de los métodos CopyRecord, CopyTo y SaveToFile (VB)
TOCTitle: CopyRecord, CopyTo, and SaveToFile Methods Example (VB)
ms:assetid: 97f9bdc5-acde-ef74-f96a-d2daeb252911
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249679(v=office.15)
ms:contentKeyID: 48546479
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 9c9476a2cae5a3df131ec8cc465866ae44189c1a
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2018
ms.locfileid: "25606279"
---
# <a name="copyrecord-copyto-and-savetofile-methods-example-vb"></a>Ejemplo de los métodos CopyRecord, CopyTo y SaveToFile (VB)


**Se aplica a**: Access 2013 | Office 2013

<<<<<<< HEAD en este ejemplo muestra cómo crear copias de un archivo con objetos [Stream](stream-object-ado.md) o [Record](record-object-ado.md) . Se realiza una copia en una carpeta Web para su publicación en Internet. También se muestran otros métodos y propiedades, como [Stream Type](type-property-ado-stream.md), **Open**, [LoadFromFile](loadfromfile-method-ado.md) y [Record Open](open-method-ado-record.md).
=== En este ejemplo se muestra cómo crear copias de un archivo con objetos [Stream](stream-object-ado.md) o [Record](record-object-ado.md) . Se realiza una copia en una carpeta web para la publicación en Internet. También se muestran otros métodos y propiedades, como [Stream Type](type-property-ado-stream.md), **Open**, [LoadFromFile](loadfromfile-method-ado.md) y [Record Open](open-method-ado-record.md).
>>>>>>> master

```vb 
 
'BeginCopyRecordVB 
 
'Note: 
' This sample requires that "C:\checkmrk.wmf" and 
' "https://MyServer/mywmf.wmf" exist. 
 
Option Explicit 
 
Private Sub Form_Load() 
 On Error GoTo ErrorHandler 
 
 ' Declare variables 
 Dim strPicturePath, strStreamPath, strStream2Path, _ 
 strRecordPath, strStreamURL, strRecordURL As String 
 Dim objStream, objStream2 As Stream 
 Dim objRecord As Record 
 Dim objField As Field 
 
 ' Instantiate objects 
 Set objStream = New Stream 
 Set objStream2 = New Stream 
 Set objRecord = New Record 
 
 ' Initialize path and URL strings 
 strPicturePath = "C:\checkmrk.wmf" 
 strStreamPath = "C:\mywmf.wmf" 
 strStreamURL = "URL=https://MyServer/mywmf.wmf" 
 strStream2Path = "C:\checkmrk2.wmf" 
 strRecordPath = "C:\mywmf.wmf" 
 strRecordURL = "https://MyServer/mywmf2.wmf" 
 
 ' Load the file into the stream 
 objStream.Open 
 objStream.Type = adTypeBinary 
 objStream.LoadFromFile (strPicturePath) 
 
 ' Save the stream to a new path and filename 
 objStream.SaveToFile strStreamPath, adSaveCreateOverWrite 
 
 ' Copy the contents of the first stream to a second stream 
 objStream2.Open 
 objStream2.Type = adTypeBinary 
 objStream.CopyTo objStream2 
 
 ' Save the second stream to a different path 
 objStream2.SaveToFile strStream2Path, adSaveCreateOverWrite 
 
<<<<<<< HEAD
 ' Because strStreamPath is a Web Folder, open a Record on the URL 
=======
 ' Because strStreamPath is a web folder, open a Record on the URL 
>>>>>>> master
 objRecord.Open "", strStreamURL 
 
 ' Display the Fields of the record 
 For Each objField In objRecord.Fields 
 Debug.Print objField.Name & ": " & objField.Value 
 Next 
 
 ' Copy the record to a new URL 
 objRecord.CopyRecord "", strRecordURL, , , adCopyOverWrite 
 
 ' Load each copy of the graphic into Image controls for viewing 
 Image1.Picture = LoadPicture(strPicturePath) 
 Image2.Picture = LoadPicture(strStreamPath) 
 Image3.Picture = LoadPicture(strStream2Path) 
 Image4.Picture = LoadPicture(strRecordPath) 
 
 ' clean up 
 objStream.Close 
 objStream2.Close 
 objRecord.Close 
 Set objStream = Nothing 
 Set objStream2 = Nothing 
 Set objRecord = Nothing 
 Exit Sub 
 
ErrorHandler: 
 ' clean up 
 If Not objStream Is Nothing Then 
 If objStream.State = adStateOpen Then objStream.Close 
 End If 
 Set objStream = Nothing 
 
 If Not objStream2 Is Nothing Then 
 If objStream2.State = adStateOpen Then objStream2.Close 
 End If 
 Set objStream2 = Nothing 
 
 If Not objRecord Is Nothing Then 
 If objRecord.State = adStateOpen Then objRecord.Close 
 End If 
 Set objRecord = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
'EndCopyRecordVB 
```

