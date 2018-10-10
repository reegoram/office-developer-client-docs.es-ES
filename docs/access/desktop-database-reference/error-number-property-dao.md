---
title: Error.Number Property (DAO)
TOCTitle: Number Property
ms:assetid: 2fb94dca-f990-04f8-bbd2-9919d28de75a
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192259(v=office.15)
ms:contentKeyID: 48544013
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053363
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 8e7f5f4b6a0d4fa12be35a20f0a17717fdef1062
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25483787"
---
# <a name="errornumber-property-dao"></a><span data-ttu-id="25084-102">Error.Number Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="25084-102">Error.Number Property (DAO)</span></span>


<span data-ttu-id="25084-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="25084-103">**Applies to**: Access 2013 | Office 2013</span></span>
 

<span data-ttu-id="25084-104">Devuelve un valor numérico que especifica un error.</span><span class="sxs-lookup"><span data-stu-id="25084-104">Returns a numeric value specifying an error.</span></span>

## <a name="syntax"></a><span data-ttu-id="25084-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="25084-105">Syntax</span></span>

<span data-ttu-id="25084-106">*expresión* . Número</span><span class="sxs-lookup"><span data-stu-id="25084-106">*expression* .Number</span></span>

<span data-ttu-id="25084-107">*expresión* Variable que representa un objeto **Error** .</span><span class="sxs-lookup"><span data-stu-id="25084-107">*expression* A variable that represents an **Error** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="25084-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="25084-108">Remarks</span></span>

<span data-ttu-id="25084-p101">Utilice la propiedad **Number** para determinar el error producido. El valor de la propiedad se corresponde con un número de captura exclusivo que a su vez se corresponde con una condición de error.</span><span class="sxs-lookup"><span data-stu-id="25084-p101">Use the **Number** property to determine the error that occurred. The value of the property corresponds to a unique trap number that corresponds to an error condition.</span></span>

## <a name="example"></a><span data-ttu-id="25084-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="25084-111">Example</span></span>

<span data-ttu-id="25084-112">En este ejemplo se fuerza un error, se captura y se muestran las propiedades **Description**, **Number**, **Source**, **HelpContext** y **HelpFile** del objeto **Error** resultante.</span><span class="sxs-lookup"><span data-stu-id="25084-112">This example forces an error, traps it, and displays the **Description**, **Number**, **Source**, **HelpContext**, and **HelpFile** properties of the resulting **Error** object.</span></span>

```vb 
Sub DescriptionX() 
 
 Dim dbsTest As Database 
 
 On Error GoTo ErrorHandler 
 
 ' Intentionally trigger an error. 
 Set dbsTest = OpenDatabase("NoDatabase") 
 
 Exit Sub 
 
ErrorHandler: 
 Dim strError As String 
 Dim errLoop As Error 
 
 ' Enumerate Errors collection and display properties of 
 ' each Error object. 
 For Each errLoop In Errors 
 With errLoop 
 strError = _ 
 "Error #" & .Number & vbCr 
 strError = strError & _ 
 " " & .Description & vbCr 
 strError = strError & _ 
 " (Source: " & .Source & ")" & vbCr 
 strError = strError & _ 
 "Press F1 to see topic " & .HelpContext & vbCr 
 strError = strError & _ 
 " in the file " & .HelpFile & "." 
 End With 
 MsgBox strError 
 Next 
 
 Resume Next 
 
End Sub 
 
```
