---
title: "Ver o establecer la opci&#243;n de configuraci&#243;n del servidor de compresi&#243;n de copia de seguridad predeterminada | Microsoft Docs"
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
  - "SQL Server Management Studio [SQL Server], opción predeterminada de compresión de copia de seguridad"
  - "compresión de copia de seguridad [SQL Server], opción predeterminada de compresión de copia de seguridad"
ms.assetid: 23029395-3e93-4c29-b7d6-e5a47a3526ff
caps.latest.revision: 30
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 30
---
# Ver o establecer la opci&#243;n de configuraci&#243;n del servidor de compresi&#243;n de copia de seguridad predeterminada
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  En este tema se describe cómo ver o configurar la opción de configuración del servidor **Compresión de copia de seguridad predeterminada** en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)]. La opción **Compresión de copia de seguridad predeterminada** determina si la instancia de servidor crea copias de seguridad comprimidas de forma predeterminada. Cuando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está instalado, la opción **Compresión de copia de seguridad predeterminada** está desactivada.  
  
 **En este tema**  
  
-   **Antes de empezar:**  
  
     [Limitaciones y restricciones](#Restrictions)  
  
     [Recomendaciones](#Recommendations)  
  
     [Seguridad](#Security)  
  
-   **Para ver o configurar la opción de valor predeterminado de compresión de copia de seguridad, use:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
-   **Seguimiento:**  [Después de configurar la opción de valor predeterminado de compresión de copia de seguridad](#FollowUp)  
  
##  <a name="BeforeYouBegin"></a> Antes de comenzar  
  
###  <a name="Restrictions"></a> Limitaciones y restricciones  
  
-   La compresión no está disponible en todas las ediciones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Para obtener más información, vea [Características compatibles con las ediciones de SQL Server 2016](../Topic/Features%20Supported%20by%20the%20Editions%20of%20SQL%20Server%202016.md).  
  
-   De forma predeterminada, la compresión aumenta significativamente el uso de CPU y la CPU adicional que consume el proceso de compresión puede afectar adversamente a las operaciones simultáneas. Por consiguiente, podría ser conveniente crear copias de seguridad comprimidas de prioridad baja en una sesión en la que el [regulador de recursos](../../relational-databases/resource-governor/resource-governor.md) limite el uso de CPU. Para obtener más información, vea [Usar el regulador de recursos para limitar el uso de CPU mediante compresión de copia de seguridad &#40;Transact-SQL&#41;](../../relational-databases/backup-restore/use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).  
  
###  <a name="Recommendations"></a> Recomendaciones  
  
-   Al crear una copia de seguridad individual, establecer una configuración de trasvase de registros o crear un plan de mantenimiento, puede invalidar el valor predeterminado de nivel de servidor.  
  
-   La compresión de copia de seguridad se admite para dispositivos de copia de seguridad en disco y en cinta.  
  
###  <a name="Security"></a> Seguridad  
  
####  <a name="Permissions"></a> Permisos  
 De forma predeterminada, todos los usuarios tienen permisos de ejecución en **sp_configure** sin ningún parámetro o solo con el primero. Para ejecutar **sp_configure** con ambos parámetros y cambiar una opción de configuración, o para ejecutar la instrucción RECONFIGURE, un usuario debe tener el permiso ALTER SETTINGS en el nivel de servidor. Los roles fijos de servidor **sysadmin** y **serveradmin** tienen el permiso ALTER SETTINGS de forma implícita.  
  
##  <a name="SSMSProcedure"></a> Usar SQL Server Management Studio  
  
#### Para ver o configurar la opción de valor predeterminado de compresión de copia  
  
1.  En el Explorador de objetos, haga clic con el botón derecho en un servidor y seleccione **Propiedades**.  
  
2.  Haga clic en el nodo **Configuración de base de datos** .  
  
3.  En **Copias de seguridad y restauración**, **Comprimir copia de seguridad** muestra el valor actual de la opción **Compresión de copia de seguridad predeterminada** . Esta opción determina el valor predeterminado de nivel de servidor para comprimir copias de seguridad, de la siguiente manera:  
  
    -   Si la casilla **Comprimir copia de seguridad** se deja en blanco, las nuevas copias de seguridad no se comprimirán de forma predeterminada.  
  
    -   Si la casilla **Comprimir copia de seguridad** se activa, las nuevas copias de seguridad se comprimirán de forma predeterminada.  
  
     Si es miembro de los roles fijos de servidor **sysadmin** o **serveradmin** , puede cambiar también el valor predeterminado haciendo clic en la casilla **Comprimir copia de seguridad** .  
  
##  <a name="TsqlProcedure"></a> Usar Transact-SQL  
  
#### Para ver la opción de valor predeterminado de compresión de copia de seguridad  
  
1.  Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].  
  
2.  En la barra Estándar, haga clic en **Nueva consulta**.  
  
3.  Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**. En este ejemplo se consulta la vista de catálogo [sys.configurations](../../relational-databases/system-catalog-views/sys-configurations-transact-sql.md) para determinar el valor de `backup compression default`. El valor 0 significa que la compresión de copia de seguridad está desactivada y el valor 1 significa que la compresión está habilitada.  
  
```tsql  
SELECT value   
FROM sys.configurations   
WHERE name = 'backup compression default' ;  
GO  
```  
  
#### Para configurar la opción de valor predeterminado de compresión de copia de seguridad  
  
1.  Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].  
  
2.  En la barra Estándar, haga clic en **Nueva consulta**.  
  
3.  Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**. En este ejemplo se muestra cómo usar [sp_configure](../../relational-databases/system-stored-procedures/sp-configure-transact-sql.md) para configurar la instancia de servidor con el fin de crear copias de seguridad comprimidas de forma predeterminada.  
  
```tsql  
EXEC sp_configure 'backup compression default', 1 ;  
RECONFIGURE WITH OVERRIDE ;  
GO 
```  
  
 Para obtener más información, vea [Opciones de configuración de servidor &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md).  
  
##  <a name="FollowUp"></a> Seguimiento: Después de configurar la opción de valor predeterminado de compresión de copia de seguridad  
 La configuración surte efecto inmediatamente, sin necesidad de reiniciar el servidor.  
  
## Vea también  
 [BACKUP &#40;Transact-SQL&#41;](../../t-sql/statements/backup-transact-sql.md)   
 [Opciones de configuración de servidor &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md)   
 [RECONFIGURE &#40;Transact-SQL&#41;](../../t-sql/language-elements/reconfigure-transact-sql.md)   
 [sp_configure &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-configure-transact-sql.md)   
 [Información general de copia de seguridad &#40;SQL Server&#41;](../../relational-databases/backup-restore/backup-overview-sql-server.md)  
  
  