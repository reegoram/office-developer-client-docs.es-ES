---
<<<<<<< Título HEAD: AbsolutePage, PageCount y ejemplo de las propiedades PageSize (JScript) TOCTitle: AbsolutePage, PageCount y ejemplo de las propiedades PageSize (JScript) ms:assetid: 6df29022-16f2-c7d8-d45b-b9998e929030 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249434(v=office.15) ms:contentKeyID: ms.date 48545506: 18/09/2015 mtps_version: Office.15
---

# <a name="absolutepage-pagecount-and-pagesize-properties-example-jscript"></a>Ejemplo de las propiedades AbsolutePage, PageCount y PageSize (JScript)

**Se aplica a**: Access 2013 | Office 2013

<a name="this-example-demonstrates-the-absolutepage-pagecount-and-pagesize-properties-cut-and-paste-the-following-code-to-notepad-or-another-text-editor-and-save-it-as-absolutepagejsasp"></a>En este ejemplo se muestra cómo las propiedades AbsolutePage, PageCount y PageSize. Corte y pegue el código siguiente en Bloc de notas u otro editor de texto y guárdelo como **AbsolutePageJS.asp**.
=======
título: ejemplo de las propiedades AbsolutePage, PageCount y PageSize (JScript) TOCTitle: ms:assetid de ejemplo (JScript) de las propiedades AbsolutePage, PageCount y PageSize: 6df29022-16f2-c7d8-d45b-b9998e929030 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249434(v=office.15) ms:contentKeyID: ms.date 48545506: 17/10/2018 mtps_version: Office.15
---

# <a name="absolutepage-pagecount-and-pagesize-properties-example-jscript"></a>Ejemplo de las propiedades AbsolutePage, PageCount y PageSize (JScript)

**Se aplica a**: Access 2013 | Office 2013

En este ejemplo se utilizan las propiedades [AbsolutePage](absolutepage-property-ado.md), [PageCount](pagecount-property-ado.md) y [PageSize](pagesize-property-ado.md) para mostrar los nombres y las fechas de contratación de la tabla ***Employees*** de cinco registros a la vez. Corte y pegue el código siguiente en Bloc de notas u otro editor de texto y guárdelo como **AbsolutePageJS.asp**.
>>>>>>> master

```javascript
<!-- BeginAbsolutePageJS --> 
<%@LANGUAGE="JScript" %> 
<%// use this meta tag instead of adojavas.inc%> 
<!--METADATA TYPE="typelib" uuid="00000205-0000-0010-8000-00AA006D2EA4" --> 
 
<html> 
 
<head> 
<title>AbsolutePage, PageSize, and PageSize Properties (JScript)</title> 
<style> 
<!-- 
BODY { 
 font-family: 'Verdana','Arial','Helvetica',sans-serif; 
 BACKGROUND-COLOR:white; 
 COLOR:black; 
 } 
.thead2 { 
 background-color: #800000; 
 font-family: 'Verdana','Arial','Helvetica',sans-serif; 
 font-size: x-small; 
 color: white; 
 } 
.tbody { 
 text-align: center; 
 background-color: #f7efde; 
 font-family: 'Verdana','Arial','Helvetica',sans-serif; 
 font-size: x-small; 
 } 
--> 
</style> 
</head> 
 
<body bgcolor="White"> 
<h1>AbsolutePage, PageSize, and PageSize Properties (JScript)</h1> 
<% 
 // connection and recordset variables 
 var Cnxn = Server.CreateObject("ADODB.Connection") 
 var strCnxn = "Provider='sqloledb';Data Source=" + Request.ServerVariables("SERVER_NAME") + ";" + 
 "Initial Catalog='Northwind';Integrated Security='SSPI';"; 
 var rsEmployee = Server.CreateObject("ADODB.Recordset"); 
 // display variables 
 var strMessage, iRecord, iPageCount; 
 
 try 
 { 
 // open connection 
 Cnxn.Open(strCnxn); 
 
 // Open a recordset on the Employee table using 
 // a client-side cursor to enable AbsolutePage property. 
 rsEmployee.CursorLocation = adUseClient; 
 rsEmployee.Open("employees", strCnxn, adOpenStatic, adLockOptimistic, adCmdTable); 
 
 // Set PageSize to five to display names and hire dates of five employees at a time 
 rsEmployee.PageSize = 5; 
 iPageCount = rsEmployee.PageCount; 
 
 // Write header information to the document 
 Response.Write('<p align="center">There are ' + iPageCount); 
 Response.Write(" pages, each containing "); 
 Response.Write(rsEmployee.PageSize + " or fewer records.</p>"); 
 Response.Write('<table border="0" align="center">'); 
 Response.Write('<tr class="thead2">'); 
 Response.Write("<th>Page</th><th>Name</th><th>Hire Date</th></tr>"); 
 
 for (var i=1; i<=iPageCount; i++) 
 { 
 rsEmployee.AbsolutePage = i; 
 
 for (iRecord = 1; iRecord <= rsEmployee.PageSize; iRecord++) 
 { 
 strMessage = ""; 
 
 // Start a new table row. 
 strMessage = '<tr class="tbody">'; 
 
 // First column in row contains page number on 
 // first record of each page. Otherwise, the column 
 // contains a non-breaking space. 
 if (iRecord == 1) 
 strMessage += "<td>Page " + i + " of " + rsEmployee.PageCount + "</td>" 
 else 
 strMessage += "<td>&nbsp;</td>"; 
 
 // First and last name are in first column. 
 strMessage += "<TD>" + rsEmployee.Fields("FirstName") + " "; 
 strMessage += rsEmployee.Fields("LastName") + " " + "</td>"; 
 
 // Hire date in second column. 
 strMessage += "<td>" + rsEmployee.Fields("HireDate") + "</td>"; 
 
 // End the row. 
 strMessage += "</tr>"; 
 
 // Write line to document. 
 Response.Write(strMessage); 
 
 // Get next record. 
 rsEmployee.MoveNext; 
 
 if (rsEmployee.EOF) 
 break; 
 } 
 } 
 
 // Finish writing table. 
 Response.Write("</table>"); 
 } 
 catch (e) 
 { 
 Response.Write(e.message); 
 } 
 finally 
 { 
 // 'clean up 
 if (rsEmployee.State == adStateOpen) 
 rsEmployee.Close; 
 if (Cnxn.State == adStateOpen) 
 Cnxn.Close; 
 rsEmployee = null; 
 Cnxn = null; 
 } 
%> 
 
</body> 
 
</html> 
<!-- EndAbsolutePageJS --> 
```

