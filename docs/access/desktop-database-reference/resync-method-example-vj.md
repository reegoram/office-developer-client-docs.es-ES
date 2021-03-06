---
title: Ejemplo del método Resync (VJ++)
TOCTitle: Resync Method Example (VJ++)
ms:assetid: f8394f26-7a56-a342-ef99-9b32a3f8ebf5
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250261(v=office.15)
ms:contentKeyID: 48548780
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c32e4c914ccab183162a473f708f5e571415c92c
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25485609"
---
# <a name="resync-method-example-vj"></a>Ejemplo del método Resync (VJ++)


**Se aplica a**: Access 2013 | Office 2013

En este ejemplo se muestra cómo utilizar el método [Resync](resync-method-ado.md) para actualizar los datos de un conjunto de registros estático.

```java 
 
// BeginResyncJ 
import java.io.*; 
import com.ms.wfc.data.*; 
 
public class ResyncX 
{ 
 // The main entry point of the application. 
 public static void main (String[] args) 
 { 
 ResyncX(); 
 System.exit(0); 
 } 
 static void ResyncX() 
 { 
 // Define ADO Objects. 
 Recordset rstTitles = null; 
 
 // Declarations. 
 BufferedReader in = 
 new BufferedReader(new InputStreamReader(System.in)); 
 String strCnn = "Provider='sqloledb';Data Source='MySqlServer';" + 
 "Initial Catalog='Pubs';Integrated Security='SSPI';"; 
 
 try 
 { 
 // Open recordset for Titles table. 
 rstTitles = new Recordset(); 
 rstTitles.setCursorLocation(AdoEnums.CursorLocation.CLIENT); 
 rstTitles.setCursorType(AdoEnums.CursorType.STATIC); 
 rstTitles.setLockType(AdoEnums.LockType.BATCHOPTIMISTIC); 
 rstTitles.open("Titles", strCnn, AdoEnums.CursorType.STATIC, 
 AdoEnums.LockType.BATCHOPTIMISTIC, 
 AdoEnums.CommandType.TABLE); 
 
 // Change the type of the first title in the recordset. 
 rstTitles.getField("type").setString("database"); 
 
 // Display the results of the change. 
 System.out.println("\n\n\tBefore resync:\n" + "\tTitle - " + 
 rstTitles.getField("title").getString() + 
 "\n\tType - " + rstTitles.getField("type").getString()); 
 
 // Resync with database and redisplay the results. 
 rstTitles.resync(); 
 System.out.println("\n\n\tAfter resync:\n" + "\tTitle - " + 
 rstTitles.getField("title").getString() + 
 "\n\tType - " + 
 rstTitles.getField("type").getString()+"\n"); 
 rstTitles.cancelBatch(); 
 
 System.out.println("\tPress <Enter> to continue.."); 
 in.readLine(); 
 
 } 
 catch(AdoException ae) 
 { 
 // Notify user of any errors that result from ADO. 
 
 // As passing a recordset, check for null pointer first. 
 if(rstTitles != null) 
 { 
 PrintProviderError(rstTitles.getActiveConnection()); 
 } 
 else 
 { 
 System.out.println("Exception: " + ae.getMessage()); 
 } 
 } 
 // System read requires this catch. 
 catch(java.io.IOException je) 
 { 
 PrintIOError(je); 
 } 
 
 finally 
 { 
 // Cleanup objects before exit. 
 if (rstTitles != null) 
 if (rstTitles.getState() == 1) 
 rstTitles.close(); 
 } 
 } 
 
 // PrintProviderError Function 
 
 static void PrintProviderError( Connection Cnn1 ) 
 { 
 // Print Provider errors from Connection object. 
 // ErrItem is an item object in the Connections Errors collection. 
 com.ms.wfc.data.Error ErrItem = null; 
 long nCount = 0; 
 int i = 0; 
 
 nCount = Cnn1.getErrors().getCount(); 
 
 // If there are any errors in the collection, print them. 
 if( nCount > 0); 
 { 
 // Collection ranges from 0 to nCount - 1 
 for (i = 0; i< nCount; i++) 
 { 
 ErrItem = Cnn1.getErrors().getItem(i); 
 System.out.println("\t Error number: " + ErrItem.getNumber() 
 + "\t" + ErrItem.getDescription() ); 
 } 
 } 
 
 } 
 
 // PrintIOError Function 
 
 static void PrintIOError( java.io.IOException je) 
 { 
 System.out.println("Error \n"); 
 System.out.println("\tSource = " + je.getClass() + "\n"); 
 System.out.println("\tDescription = " + je.getMessage() + "\n"); 
 } 
} 
// EndResyncJ 
```

