---
title: Columnas con el nombre de una prueba de nodo XPath | Microsoft Docs
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- dbe-xml
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- names [SQL Server], columns with
- XPath node test
ms.assetid: b48adccd-3b6b-486a-b326-20f57170186f
caps.latest.revision: 10
author: BYHAM
ms.author: rickbyh
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 41bc7b31ff9f5185dcdfde4a90bbfe631fbef089
ms.lasthandoff: 04/11/2017

---
# <a name="columns-with-the-name-of-an-xpath-node-test"></a>Columnas con el nombre de una prueba de nodo XPath
  Si el nombre de columna es una de las pruebas de nodo XPath, se asignará el contenido tal y como se muestra en la tabla siguiente. Cuando el nombre de la columna es una prueba de nodo XPath, se asigna el contenido al nodo correspondiente. Si el tipo SQL de la columna es **xml**, se devolverá un error.  
  
|Nombre de la columna|Comportamiento|  
|-----------------|--------------|  
|text()|En el caso de las columnas con el nombre text(), el valor de cadena de la misma se agregará como un nodo de texto.|  
|comment()|En el caso de las columnas con el nombre comment(), el valor de cadena de la misma se agregará como un comentario XML.|  
|node()|En el caso de las columnas con el nombre node(), el resultado será el mismo que cuando el nombre de la columna es un carácter comodín (*).|  
|processing-instruction(name)|En el caso de las columnas con el nombre de una instrucción de procesamiento, su valor de cadena se agregará como el valor PI para el nombre de destino de la instrucción de procesamiento.|  
  
 La siguiente consulta muestra el uso de las pruebas de nodo como nombres de columna. Agrega nodos de texto y comentarios en el XML resultante.  
  
```  
USE AdventureWorks2012;  
GO  
SELECT E.BusinessEntityID "@EmpID",   
        'Example of using node tests such as text(), comment(), processing-instruction()'                as "comment()",  
        'Some PI'                   as "processing-instruction(PI)",  
        'Employee name and address data' as "text()",  
        'middle name is optional'        as "EmpName/text()",  
        FirstName                        as "EmpName/First",   
        MiddleName                       as "EmpName/Middle",   
        LastName                         as "EmpName/Last",  
        AddressLine1                     as "Address/AddrLine1",  
        AddressLine2                     as "Address/AddrLIne2",  
        City                             as "Address/City"  
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P   
    ON P.BusinessEntityID = E.BusinessEntityID  
INNER JOIN Person.BusinessEntityAddress AS BAE  
    ON BAE.BusinessEntityID = E.BusinessEntityID  
INNER JOIN Person.Address AS A  
    ON BAE.AddressID = A.AddressID  
WHERE  E.BusinessEntityID=1  
FOR XML PATH;  
```  
  
 El resultado es el siguiente:  
  
 `<row EmpID="1">`  
  
 `<!--Example of using node tests such as text(), comment(), processing-instruction() -->`  
  
 `<?PI Some PI?>`  
  
 `Employee name and address data`  
  
 `<EmpName>middle name is optional`  
  
 `<First>Ken</First>`  
  
 `<Last>Sánchez</Last>`  
  
 `</EmpName>`  
  
 `<Address>`  
  
 `<AddrLine1>4350 Minute Dr.</AddrLine1>`  
  
 `<City>Minneapolis</City>`  
  
 `</Address>`  
  
 `</row>`  
  
## <a name="see-also"></a>Vea también  
 [Usar el modo PATH con FOR XML](../../relational-databases/xml/use-path-mode-with-for-xml.md)  
  
  