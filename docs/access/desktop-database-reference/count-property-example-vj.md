---
<<<<<<< Título HEAD: ejemplo de la propiedad Count (VJ ++) TOCTitle: ejemplo de la propiedad Count (VJ ++) === título: ejemplo de la propiedad Count (VJ ++) TOCTitle: ejemplo de la propiedad Count (VJ ++)
>>>>>>> Master ms:assetid: 749de00a-7530-ea04-558c-34277c4d2f61 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249478(v=office.15) ms:contentKeyID: ms.date 48545666: 18/09/2015 mtps_version: Office.15
---

<<<<<<< HEAD
# <a name="count-property-example-vj"></a>Ejemplo de la propiedad Count (VJ++)
=======
# <a name="count-property-example-vj"></a>Ejemplo de la propiedad Count (VJ ++)
>>>>>>> master


**Se aplica a**: Access 2013 | Office 2013

En este ejemplo se muestra la propiedad [Count](count-property-ado.md) con dos colecciones en la base de datos de ***los empleados*** . La propiedad obtiene el número de objetos de cada colección y establece el límite superior de los bucles que enumeran estas colecciones. Otra forma de enumerar estas colecciones sin utilizar la propiedad **Count** sería utilizar instrucciones.

```java 
 
// BeginCountJ 
import com.ms.wfc.data.*; 
import java.io.* ; 
 
public class CountX 
{ 
 // The main entry point for the application. 
 
 public static void main (String[] args) 
 { 
 CountX(); 
 System.exit(0); 
 } 
 
 // CountX function 
 
 static void CountX() 
 { 
 
 // Define ADO Objects. 
 Recordset rstEmployees = null; 
 
 // Declarations. 
 BufferedReader in = 
 new BufferedReader (new InputStreamReader(System.in)); 
 String line = null; 
 String strCnn = "Provider='sqloledb';Data Source='MySqlServer';" 
 + "Initial Catalog='Pubs';Integrated Security='SSPI';"; 
 
 int intLoop; 
 int intDisplaySize = 20; 
 int recCount=0; 
 
 try 
 { 
 rstEmployees = new Recordset(); 
 
 // Open recordset with data from Employees table. 
 rstEmployees.open("employee", strCnn, 
 AdoEnums.CursorType.FORWARDONLY, 
 AdoEnums.LockType.READONLY, 
 AdoEnums.CommandType.TABLE); 
 
 // Print information about Fields collection. 
 System.out.println(rstEmployees.getFields().getCount() + 
 " Fields in Employees"); 
 for ( intLoop = 0; intLoop < 
 rstEmployees.getFields().getCount(); intLoop++) 
 { 
 System.out.println("\t" + 
 rstEmployees.getFields().getItem(intLoop).getName()); 
 } 
 System.out.println("\n\nPress <Enter> to continue.."); 
 in.readLine(); 
 
 // Print information about Properties collection. 
 System.out.println(rstEmployees.getProperties().getCount() + 
 " Properties in Employees"); 
 for ( intLoop = 0; intLoop < 
 rstEmployees.getProperties().getCount(); intLoop++) 
 { 
 System.out.println("\t" + 
 rstEmployees.getProperties().getItem(intLoop).getName()); 
 recCount++; 
 if ( recCount >= intDisplaySize) 
 { 
 System.out.println("\n\nPress <Enter> to continue.."); 
 in.readLine(); 
 recCount = 0; 
 } 
 } 
 System.out.println("\n\nPress <Enter> to continue.."); 
 in.readLine(); 
 
 } 
 catch( AdoException ae ) 
 { 
 // Notify user of any errors that result from ADO. 
 
 // Check for null pointer for connection object. 
 if (rstEmployees.getActiveConnection()==null) 
 { 
 System.out.println("Exception: " + ae.getMessage()); 
 } 
 else 
 { 
 // As passing a Recordset, check for null pointer first. 
 if (rstEmployees != null) 
 { 
 PrintProviderError(rstEmployees.getActiveConnection()); 
 } 
 else 
 { 
 System.out.println("Exception: " + ae.getMessage()); 
 } 
 } 
 } 
 
 // System read requires this catch. 
 catch( java.io.IOException je) 
 { 
 PrintIOError(je); 
 } 
 
 finally 
 { 
 // Cleanup objects before exit. 
 if (rstEmployees != null) 
 if (rstEmployees.getState() == 1) 
 rstEmployees.close(); 
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
 
// EndCountJ 
```

