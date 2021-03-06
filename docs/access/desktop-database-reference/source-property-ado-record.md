---
title: Source (propiedad, Record ADO)
TOCTitle: Source Property (ADO Record)
ms:assetid: f36f0f5f-4493-d8c5-db4b-c72f5031bcb3
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250235(v=office.15)
ms:contentKeyID: 48548670
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4d6e010ce8db93baaf8faddaeff5ab4dabda6a84
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2018
ms.locfileid: "25603388"
---
# <a name="source-property-ado-record"></a>Source (propiedad, Record ADO)


**Se aplica a**: Access 2013 | Office 2013

Indica el origen de datos o el objeto representados por el objeto [Record](record-object-ado.md).

<<<<<<< HEAD
## <a name="settings-and-return-values"></a>Configuración y valores devueltos
=======
## <a name="settings-and-return-values"></a>Configuración y valores devueltos
>>>>>>> master

Establece o devuelve un valor de tipo **Variant** que indica la entidad representada por el objeto **Record**.

## <a name="remarks"></a>Comentarios

La propiedad **Source** devuelve el argumento *Source* del método [Open](open-method-ado-record.md) del objeto de **registro** . Puede incluir una cadena de dirección URL absoluta o relativa. Es posible usar una dirección URL absoluta sin establecer la propiedad [ActiveConnection](activeconnection-property-ado.md) para abrir directamente el objeto **Record**. En este caso se crea un objeto **Connection** implícito.

La propiedad **Source** también puede incluir una referencia a un objeto **Recordset** ya abierto, que abre un objeto **Record** que representa a la fila actual del objeto **Recordset**.

La propiedad **Source** también podría incluir una referencia a un objeto [Command](command-object-ado.md) que devuelve una única fila de datos del proveedor.

Si también se establece la propiedad **ActiveConnection**, la propiedad **Source** debe apuntar a algún objeto que exista en el ámbito de esa conexión. Por ejemplo, en los espacios de nombre con estructura de árbol, si la propiedad **Source** incluye una dirección URL absoluta, debe apuntar a un nodo que exista en el ámbito del nodo identificado por la dirección URL en la cadena de conexión. Si la propiedad **Source** incluye una dirección URL relativa, se valida en el contexto establecido por la propiedad **ActiveConnection**.

La propiedad **Source** es de lectura y escritura mientras el objeto **Record** está cerrado y de sólo lectura mientras el objeto **Record** está abierto.

<<<<<<< HEAD

> [!NOTE]
> <P>[!NOTA] Las direcciones URL que utilicen el esquema http invocarán automáticamente <A href="microsoft-ole-db-provider-for-internet-publishing.md">Microsoft OLE DB Provider for Internet Publishing</A>. Para obtener más información, vea <A href="absolute-and-relative-urls.md">Direcciones URL absolutas y relativas</A>.</P>
=======
> [!NOTE]
> [!NOTA] Las direcciones URL que utilicen el esquema http invocarán automáticamente [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md). Para obtener más información, vea [direcciones URL absolutas y relativas](absolute-and-relative-urls.md).
>>>>>>> master


