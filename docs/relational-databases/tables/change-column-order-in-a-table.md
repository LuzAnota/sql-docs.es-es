---
title: Cambio del orden de las columnas en una tabla | Microsoft Docs
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- dbe-tables
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- columns [SQL Server], change order in a table
- column order, change
ms.assetid: cd99ef56-9085-431a-a0fc-58e7add5399f
caps.latest.revision: 15
author: BYHAM
ms.author: rickbyh
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: f9ab22cf6c60bd7d89ff70eba15ca65c731a1fb1
ms.lasthandoff: 04/11/2017

---
# <a name="change-column-order-in-a-table"></a>Cambiar el orden de las columnas de una tabla
[!INCLUDE[tsql-appliesto-ss2016-all_md](../../includes/tsql-appliesto-ss2016-all-md.md)]

  Puede cambiar el orden de las columnas en el Diseñador de tablas en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].  
  
> [!CAUTION]  
>  Si cambia el orden de las columnas de una tabla, el código y las aplicaciones que dependen de un orden de columnas determinado pueden verse afectados. Los elementos afectados pueden ser consultas, vistas, procedimientos almacenados, funciones definidas por el usuario y aplicaciones cliente. Tenga en cuenta las consecuencias antes de realizar cualquier cambio en el orden de las columnas. El procedimiento recomendado es especificar el orden en que las columnas se devuelven en el nivel de aplicación y de consulta. No debe confiar en el uso de SELECT * para devolver todas las columnas en un orden esperado según el orden en que están definidos en la tabla. Especifique siempre las columnas por nombre en las consultas y aplicaciones en el orden en que desea que aparezcan.  
  
 **En este tema**  
  
-   **Para cambiar el orden de las columnas con:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="SSMSProcedure"></a> Usar SQL Server Management Studio  
  
#### <a name="to-change-the-column-order"></a>Para cambiar el orden de las columnas  
  
1.  En el **Explorador de objetos**, haga clic con el botón derecho en la tabla cuyas columnas quiera reordenar y seleccione **Diseñar**.  
  
2.  Seleccione la casilla que hay a la izquierda del nombre de la columna cuyo orden desea cambiar.  
  
3.  Arrastre la columna a otra ubicación en la tabla.  
  
##  <a name="TsqlProcedure"></a> Usar Transact-SQL  
 **Para cambiar el orden de las columnas**  
  
 Esta tarea no se puede realizar mediante instrucciones Transact-SQL.  
  
###  <a name="TsqlExample"></a>  