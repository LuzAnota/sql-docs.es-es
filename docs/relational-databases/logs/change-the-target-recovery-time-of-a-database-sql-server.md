---
title: "Cambio del tiempo de recuperación de destino de una base de datos (SQL Server) | Microsoft Docs"
ms.custom:
- SQL2016_New_Updated
ms.date: 08/24/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e466419a-d8a4-48f7-8d97-13a903ad6b15
caps.latest.revision: 16
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 6daed0f65622cd6a0533db68441021cb8c8f0a1c
ms.lasthandoff: 04/11/2017

---
# <a name="change-the-target-recovery-time-of-a-database-sql-server"></a>Cambiar el tiempo de recuperación de destino de una base de datos (SQL Server)
  En este tema se describe cómo establecer el cambio el tiempo de recuperación de destino de una base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)]. De forma predeterminada, el tiempo de recuperación de destino es de 60 segundos y la base de datos usa *puntos de comprobación indirectos*. El tiempo de recuperación de destino establece un límite superior en el tiempo de recuperación para esta base de datos.  
  
> [!NOTE]  
>  El límite superior especificado para una base de datos determinada por el valor de tiempo de recuperación de destino se puede superar si una transacción de larga duración provoca tiempos de UNDO excesivos.  
  
-   **Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)  
  
-   **To change the target recovery time, using:**  [SQL Server Management Studio](#SSMSProcedure) or [Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> Antes de empezar  
  
###  <a name="Restrictions"></a> Limitaciones y restricciones 
  
> [!CAUTION]  
>  Una carga de trabajo transaccional en línea en una base de datos que esté configurada para puntos de comprobación indirectos podría experimentar un deterioro del rendimiento. Los puntos de comprobación indirectos garantizan que el número de páginas desfasadas se encuentra por debajo de un umbral determinado para que la recuperación de la base de datos finalice en el tiempo de recuperación de destino. La opción de configuración de intervalo de recuperación usa el número de transacciones para determinar el tiempo de recuperación a diferencia de los puntos de comprobación indirectos, que usan el número de páginas desfasadas. Cuando se habilitan los puntos de comprobación indirectos en una base de datos que recibe un gran número de operaciones de DML, el escritor en segundo plano puede iniciar agresivamente el vaciado de búferes desfasados en el disco para asegurarse de que el tiempo necesario para realizar la recuperación se encuentra dentro del tiempo de recuperación de destino establecido de la base de datos. Esto puede provocar actividad de E/S adicional en determinados sistemas que pueden contribuir a un cuello de botella de rendimiento si el subsistema del disco está funcionando por encima del umbral de E/S o cerca de él.  
  
###  <a name="Security"></a> Seguridad  
  
####  <a name="Permissions"></a> Permisos  
 Requiere el permiso ALTER en la base de datos.  
  
##  <a name="SSMSProcedure"></a> Usar SQL Server Management Studio  
 **Para cambiar el tiempo de recuperación de destino**  
  
1.  En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]y expándala.  
  
2.  Haga clic con el botón derecho en la base de datos que quiera cambiar y haga clic en el comando **Propiedades** .  
  
3.  En el cuadro de diálogo **Propiedades de la base de datos** , haga clic en la página **Opciones** .  
  
4.  En el panel **Recuperación** , en el campo de **Tiempo de recuperación de destino (segundos)** , especifique el número de segundos que quiera como límite superior para el tiempo de recuperación de esta base de datos.  
  
##  <a name="TsqlProcedure"></a> Usar Transact-SQL  
 **Para cambiar el tiempo de recuperación de destino**  
  
1.  Conéctese a la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] donde reside la base de datos.  
  
2.  Use la siguiente instrucción [ALTER DATABASE](../../t-sql/statements/alter-database-transact-sql-set-options.md)del siguiente modo:  
  
     TARGET_RECOVERY_TIME **=***target_recovery_time* { SECONDS | MINUTES }  
  
     *target_recovery_time*  
     Empezando por [!INCLUDE[ssSQL15_md](../../includes/sssql15-md.md)], el valor predeterminado es 1 minuto. Cuando el valor es mayor que 0 (valor predeterminado para versiones más antiguas), especifica el límite superior para el tiempo de recuperación de la base de datos especificada en caso de bloqueo.  
  
     SECONDS  
     Indica que *target_recovery_time* se expresa como el número de segundos.  
  
     MINUTES  
     Indica que *target_recovery_time* se expresa como el número de minutos.  
  
     El ejemplo siguiente se establece el tiempo de recuperación de destino de la base de datos de [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] en `60` segundos.  
  
    ```  
    ALTER DATABASE AdventureWorks2012 SET TARGET_RECOVERY_TIME = 60 SECONDS;  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Puntos de comprobación de base de datos &#40;SQL Server&#41;](../../relational-databases/logs/database-checkpoints-sql-server.md)   
 [Opciones de ALTER DATABASE SET &#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-transact-sql-set-options.md)  
  
  
