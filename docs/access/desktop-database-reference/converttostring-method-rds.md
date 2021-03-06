---
title: ConvertToString (método, RDS)
TOCTitle: ConvertToString Method (RDS)
ms:assetid: dc6381e4-98c8-badc-ad8c-87c70574a8a4
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250113(v=office.15)
ms:contentKeyID: 48548136
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: fa1a4326cf318a9cbcddf8ebcdf584543ac8ebfb
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25486088"
---
# <a name="converttostring-method-rds"></a>ConvertToString (método, RDS)


**Se aplica a**: Access 2013 | Office 2013 

Convierte un objeto [Recordset](recordset-object-ado.md) en una cadena MIME que representa los datos del conjunto de registros.

## <a name="syntax"></a>Sintaxis

*DataFactory*. ConvertToString (objeto de*conjunto de registros*)

## <a name="parameters"></a>Parámetros

  - *DataFactory*

  - Variable de objeto que representa un objeto [RDSServer.DataFactory](datafactory-object-rdsserver.md).

  - *Recordset*

  - Variable de objeto que representa un objeto **Recordset**.

## <a name="remarks"></a>Comentarios

Con archivos .asp, use **ConvertToString** para incrustar el objeto **Recordset** en una página HTML generada en el servidor para su transmisión a un equipo de cliente.

**ConvertToString** carga primero el objeto **Recordset** en las tablas del servicio de cursor y, a continuación, genera una secuencia en formato MIME.

En el cliente, el Servicio de datos remoto puede volver a convertir la cadena MIME en un objeto **Recordset** de plena funcionalidad. Esto funciona bien cuando se manipulan menos de 400 filas de datos y el ancho de cada fila no supera los 1024 bytes. No debe usarse para transmitir datos BLOB ni conjuntos de resultados de gran tamaño a través de HTTP. No se realiza ningún tipo de compresión en la cadena, por lo que los conjuntos de datos de tamaño muy grande tardarán bastante en transmitirse a través de HTTP en comparación con el formato de tablagrama optimizada que el Servicio de datos remoto define e implementa como su formato de protocolo de transporte nativo.


> [!NOTE]
> <P>[!NOTA] Si utiliza páginas Active Server para incrustar la cadena MIME resultante en una página HTML de cliente, tenga en cuenta que las versiones de VBScript anteriores a la versión 2.0 limitan el tamaño de la cadena a 32 K. Si se supera este límite, se devuelve un error. Mantenga el ámbito de consulta bastante reducido al utilizar la incrustación MIME a través de archivos .asp. Para solucionar esto, descargue la última versión de VBScript del <A href="https://www.microsoft.com/downloads/en/default.aspx">Centro de descarga de Microsoft</A>.</P>


