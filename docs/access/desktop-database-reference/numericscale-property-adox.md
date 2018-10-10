---
title: NumericScale (propiedad, ADOX)
TOCTitle: NumericScale Property (ADOX)
ms:assetid: ebe73bdc-2570-f54a-3d2f-85a2a4634c9a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250197(v=office.15)
ms:contentKeyID: 48548501
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4229a318c4eb855b86164f02f1075d29a915d718
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485575"
---
# <a name="numericscale-property-adox"></a><span data-ttu-id="c0ed9-102">NumericScale (propiedad, ADOX)</span><span class="sxs-lookup"><span data-stu-id="c0ed9-102">NumericScale Property (ADOX)</span></span>


<span data-ttu-id="c0ed9-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="c0ed9-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="c0ed9-104">Indica la escala de un valor numérico de la columna.</span><span class="sxs-lookup"><span data-stu-id="c0ed9-104">Indicates the scale of a numeric value in the column.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="c0ed9-105">Configuraciones y valores devueltos</span><span class="sxs-lookup"><span data-stu-id="c0ed9-105">Settings and Return Values</span></span>

<span data-ttu-id="c0ed9-p101">Establece y devuelve un valor **Byte** que es la escala de valores de datos de la columna cuando la propiedad [Tipo](https://msdn.microsoft.com/library/jj249169\(v=office.15\)) es **adNumeric** o **adDecimal**. **NumericScale** se omite para todos los demás tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="c0ed9-p101">Sets and returns a **Byte** value that is the scale of data values in the column when the [Type](https://msdn.microsoft.com/library/jj249169\(v=office.15\)) property is **adNumeric** or **adDecimal**. **NumericScale** is ignored for all other data types.</span></span>

## <a name="remarks"></a><span data-ttu-id="c0ed9-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c0ed9-108">Remarks</span></span>

<span data-ttu-id="c0ed9-109">El valor predeterminado es cero (0).</span><span class="sxs-lookup"><span data-stu-id="c0ed9-109">The default value is zero (0).</span></span>

<span data-ttu-id="c0ed9-110">**NumericScale** es de sólo lectura para objetos [Column](column-object-adox.md) ya anexados a una colección.</span><span class="sxs-lookup"><span data-stu-id="c0ed9-110">**NumericScale** is read-only for [Column](column-object-adox.md) objects already appended to a collection.</span></span>
