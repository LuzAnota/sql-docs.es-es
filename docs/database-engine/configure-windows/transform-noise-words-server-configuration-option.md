---
title: "transform noise words (opci&#243;n de configuraci&#243;n del servidor) | Microsoft Docs"
ms.custom: ""
ms.date: "03/02/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "consultas de texto [SQL Server], rendimiento"
  - "transform noise words, opción"
  - "palabras irrelevantes [búsqueda de texto completo]"
  - "búsqueda de texto completo [SQL Server], palabras irrelevantes"
  - "palabras irrelevantes [búsqueda de texto completo]"
ms.assetid: 69bd388e-a86c-4de4-b5d5-d093424d9c57
caps.latest.revision: 43
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 43
---
# transform noise words (opci&#243;n de configuraci&#243;n del servidor)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Use la opción de configuración del servidor **Transformar palabras irrelevantes** para suprimir un mensaje de error si las [palabras irrelevantes](../../relational-databases/search/configure-and-manage-stopwords-and-stoplists-for-full-text-search.md) hacen que una operación booleana en una consulta de texto completo devuelva cero filas. Esta opción es útil para las consultas de texto completo que utilizan el predicado CONTAINS en el que las operaciones booleanas o las operaciones NEAR incluyen palabras irrelevantes. En la siguiente tabla se describen los valores posibles.  
  
|Valor|Descripción|  
|-----------|-----------------|  
|0|Las palabras irrelevantes no se transforman. Cuando una consulta de texto completo contiene palabras irrelevantes, la consulta devuelve cero filas y [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] produce una advertencia. Éste es el comportamiento predeterminado.<br /><br /> Nota: La advertencia es una advertencia en tiempo de ejecución. Por lo tanto, si no se ejecuta la cláusula de texto completo de la consulta, no se generará la advertencia. En una consulta local solo se generará una advertencia, incluso si existen varias cláusulas de consulta de texto completo. En una consulta remota, es posible que el servidor vinculado no retransmita el error; por tanto, puede que tampoco se genere la advertencia.|  
|1|Las palabras irrelevantes se transforman. Se omiten y el resto de la consulta se evalúa.<br /><br /> Si las palabras irrelevantes se especifican en un término de proximidad, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] las quita. Por ejemplo, la palabra irrelevante `is` se quita de `CONTAINS(<column_name>, 'NEAR (hello,is,goodbye)')`, transformando la consulta de búsqueda en `CONTAINS(<column_name>, 'NEAR(hello,goodbye)')`. Observe que `CONTAINS(<column_name>, 'NEAR(hello,is)')` se transformaría simplemente en `CONTAINS(<column_name>, hello)` porque solo hay un término de búsqueda válido.|  
  
## Efectos de la opción Transformar palabras irrelevantes  
 En esta sección se muestra el comportamiento de las consultas que contienen una palabra irrelevante, "`the`", con la configuración alternativa de **Transformar palabras irrelevantes**.  Se supone que las cadenas de consulta de texto completo de ejemplo se ejecutan en una fila de tabla que contiene los datos siguientes: `[1, "The black cat"]`.  
  
> [!NOTE]  
>  Todos esos escenarios pueden generar una advertencia por palabras irrelevantes.  
  
-   Con Transformar palabras irrelevantes establecido en 0:  
  
    |Cadena de consulta|Resultado|  
    |------------------|------------|  
    |"`cat`" AND "`the`"|Sin resultados (el comportamiento es el mismo para "`the`" AND "`cat`").|  
    |"`cat`" NEAR "`the`"|Sin resultados (el comportamiento es el mismo para "`the`" NEAR "`cat`").|  
    |"`the`" AND NOT "`black`"|No hay resultados|  
    |"`black`" AND NOT "`the`"|No hay resultados|  
  
-   Con Transformar palabras irrelevantes establecido en 1:  
  
    |Cadena de consulta|Resultado|  
    |------------------|------------|  
    |"`cat`" AND "`the`"|Acierto para la fila con identificador 1|  
    |"`cat`" NEAR "`the`"|Acierto para la fila con identificador 1|  
    |"`the`" AND NOT "`black`"|No hay resultados|  
    |"`black`" AND NOT "`the`"|Acierto para la fila con identificador 1|  
  
## Ejemplo  
 En el ejemplo siguiente se establece **Transformar palabras irrelevantes** en `1`.  
  
```  
sp_configure 'show advanced options', 1;  
RECONFIGURE;  
GO  
sp_configure 'transform noise words', 1;  
RECONFIGURE;  
GO  
```  
  
## Vea también  
 [Opciones de configuración de servidor &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md)   
 [CONTAINS &#40;Transact-SQL&#41;](../../t-sql/queries/contains-transact-sql.md)  
  
  