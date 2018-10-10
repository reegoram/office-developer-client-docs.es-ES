---
title: Configurar el formato de cálculo de secuencias de DCOM
TOCTitle: Setting DCOM Stream Marshaling Format
ms:assetid: 5f75fc59-a9f8-6686-07f9-de292e4da787
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249346(v=office.15)
ms:contentKeyID: 48545162
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c0c05a378624f118f1bf6f070273b686a2e50a6e
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485121"
---
# <a name="setting-dcom-stream-marshaling-format"></a><span data-ttu-id="d1135-102">Configurar el formato de cálculo de secuencias de DCOM</span><span class="sxs-lookup"><span data-stu-id="d1135-102">Setting DCOM Stream Marshaling Format</span></span>


<span data-ttu-id="d1135-103">**Se aplica a**: Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="d1135-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="d1135-p101">Un equipo cliente que usa componentes de RDS 1.5 (o de una versión anterior) no es compatible con un servidor que usa componentes de RDS 2.0 (o de versiones posteriores). Cuando se usa DCOM como protocolo subyacente, RDS 2.0 (o versión posterior) resulta más eficiente para transportar objetos [Recordset](recordset-object-ado.md). Si el cliente ejecuta componentes de RDS 1.5 (o versiones anteriores), es posible configurar el servidor de modo que funcione con la compatibilidad RDS anterior (denominada RDS 1.0) o con la nueva compatibilidad RDS (denominada RDS 2.0 o posterior). Configure cualquiera de las siguientes entradas del Registro:</span><span class="sxs-lookup"><span data-stu-id="d1135-p101">A client computer using components from RDS 1.5 or earlier is not compatible with a server using components from RDS 2.0 or later. When using DCOM as the underlying protocol, the support for RDS 2.0 or later is more efficient in transporting [Recordset](recordset-object-ado.md) objects. If your client is running components from RDS 1.5 or earlier, you can set your server to work with the previous RDS support (called RDS 1.0) or the newer RDS support (called RDS 2.0 or later). Set either of the following registry entries:</span></span>

```vb 
 
[HKEY_CLASSES_ROOT] 
\CLSID 
 \[58ECEE30-E715-11CF-B0E3-00AA003F000F} 
 \ADTGOptions]"MarshalFormat"="RDS10" 
```

<span data-ttu-id="d1135-108">\-o -</span><span class="sxs-lookup"><span data-stu-id="d1135-108">\-or-</span></span>

```vb 
 
[HKEY_CLASSES_ROOT] 
\CLSID 
 \[58ECEE30-E715-11CF-B0E3-00AA003F000F} 
 \ADTGOptions]"MarshalFormat"="RDS20" 
```
