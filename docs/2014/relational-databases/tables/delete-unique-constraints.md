---
title: Eliminación de restricciones UNIQUE | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- removing constraints
- UNIQUE constraints [SQL Server], deleting
- constraints [SQL Server], deleting
- deleting constraints
- constraints [SQL Server], unique
ms.assetid: 71e563fc-f5d7-4c2e-a42f-f0695a831f32
caps.latest.revision: 14
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: c2f9ad9a3528fcb7eb15422c4d4e4294811e7142
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36107590"
---
# <a name="delete-unique-constraints"></a>Eliminar restricciones UNIQUE
  Puede eliminar una restricción UNIQUE en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)]. Al eliminar una restricción UNIQUE, se quita el requisito de unicidad para los valores escritos en una columna o una combinación de columnas incluidas en la expresión de la restricción y se elimina el índice único correspondiente.  
  
 **En este tema**  
  
-   **Antes de empezar:**  
  
     [Seguridad](#Security)  
  
-   **Para eliminar una restricción UNIQUE con:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> Antes de empezar  
  
###  <a name="Security"></a> Seguridad  
  
####  <a name="Permissions"></a> Permissions  
 Requiere el permiso ALTER en la tabla.  
  
##  <a name="SSMSProcedure"></a> Usar SQL Server Management Studio  
  
#### <a name="to-delete-a-unique-constraint-using-object-explorer"></a>Para eliminar una restricción UNIQUE mediante el Explorador de objetos  
  
1.  En el Explorador de objetos, expanda la tabla que contiene la restricción UNIQUE y, a continuación, expanda **Restricciones**.  
  
2.  Haga clic con el botón derecho en la clave y seleccione **Eliminar**.  
  
3.  En el cuadro de diálogo **Eliminar objeto** , compruebe que se ha especificado la clave correcta y haga clic en **Aceptar**.  
  
#### <a name="to-delete-a-unique-constraint-using-table-designer"></a>Para eliminar una restricción UNIQUE mediante el Diseñador de tablas  
  
1.  En el **Explorador de objetos**, haga clic con el botón derecho en la tabla con la restricción UNIQUE y haga clic en **Diseño**.  
  
2.  En el menú **Diseñador de tablas** , haga clic en **Índices o claves**.  
  
3.  En el cuadro de diálogo **Índices o claves** , seleccione la clave UNIQUE en la lista **Clave principal o única, o índice seleccionado** .  
  
4.  Haga clic en **Eliminar**.  
  
5.  En el menú **Archivo** , haga clic en **Guardar***nombre de tabla*.  
  
##  <a name="TsqlProcedure"></a> Usar Transact-SQL  
  
#### <a name="to-delete-a-unique-constraint"></a>Para eliminar una restricción UNIQUE  
  
1.  En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].  
  
2.  En la barra de Estándar, haga clic en **Nueva consulta**.  
  
3.  Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.  
  
    ```  
    -- Return the name of unique constraint.  
    SELECT name  
    FROM sys.objects  
    WHERE type = 'UQ' AND OBJECT_NAME(parent_object_id) = N' DocExc';  
    GO  
    -- Delete the unique constraint.  
    ALTER TABLE dbo.DocExc   
    DROP CONSTRAINT UNQ_ColumnB_DocExc;  
    GO  
    ```  
  
 Para obtener más información, vea [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) y [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).  
  
###  <a name="TsqlExample"></a>  