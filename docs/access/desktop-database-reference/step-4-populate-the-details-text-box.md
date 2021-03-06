---
title: 'Paso 4: Rellenar el cuadro de texto de detalles'
TOCTitle: 'Step 4: Populate the Details Text Box'
ms:assetid: fa5e4482-8986-0c03-1e46-7b7fefb5fb58
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250278(v=office.15)
ms:contentKeyID: 48548839
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e0f04d52edc55c7ccc5163bc9a858d7bc8845702
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485175"
---
# <a name="step-4-populate-the-details-text-box"></a>Paso 4: Rellenar el cuadro de texto de detalles


**Se aplica a**: Access 2013 | Office 2013

## <a name="step-4-populate-the-details-text-box"></a>Paso 4: Rellenar el cuadro de texto de detalles

**Para rellenar el cuadro de texto de detalles**

Cree una subrutina nueva denominada recFields e inserte el código siguiente:

```vb 
 
Sub recFields(r As Record, l As ListBox, t As TextBox) 
    Dim f As Field 
    Dim s As Stream 
    Set s = New Stream 
    Dim str As String 
     
    For Each f In r.Fields 
        l.AddItem f.Name & ": " & f.Value 
    Next 
    t.Text = "" 
    If r!RESOURCE_CONTENTCLASS = "text/plain" Then 
        s.Open r, adModeRead, adOpenStreamFromRecord 
        str = s.ReadText(1) 
        s.Position = 0 
        If Asc(Mid(str, 1, 1)) = 63 Then '//63 = "?" 
            s.Charset = "ascii" 
            s.Type = adTypeText 
        End If 
        t.Text = s.ReadText(adReadAll) 
    End If 
End Sub 
```

Este código rellena lstDetails con los campos y valores del registro simple pasado a recFields. Si el recurso es un archivo de texto, se abre un ** Stream** de texto a partir del registro. El código determina si el juego de caracteres es ASCII y copia el contenido del **Stream** en txtDetails.

