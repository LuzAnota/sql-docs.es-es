---
title: Restaurar una clave maestra de base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-security
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- database master key [SQL Server], importing
ms.assetid: 16897cc5-db8f-43bb-a38e-6855c82647cf
caps.latest.revision: 14
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: 2d2608be4f4691e8b0279def055f838fe94006b8
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36197354"
---
# <a name="restore-a-database-master-key"></a>Restaurar una clave maestra de base de datos
  En este tema se describe cómo restaurar la clave maestra de una base de datos en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mediante [!INCLUDE[tsql](../../../includes/tsql-md.md)].  
  
 **En este tema**  
  
-   **Antes de empezar:**  
  
     [Limitaciones y restricciones](#Restrictions)  
  
     [Seguridad](#Security)  
  
-   [Para restaurar la clave maestra de una base de datos utilizando Transact-SQL](#SSMSProcedure)  
  
##  <a name="BeforeYouBegin"></a> Antes de empezar  
  
###  <a name="Restrictions"></a> Limitaciones y restricciones  
  
-   Al restaurar la clave maestra, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] descifra todas las claves cifradas con la clave maestra actualmente activa y cifra estas claves con la clave maestra restaurada. Esta operación requiere un uso intensivo de recursos, por lo que debe programarse durante un período de baja demanda. Si la clave maestra de base de datos no se encuentra abierta, no puede abrirse o alguna de las claves cifradas con ella no pueden descifrarse, la operación de restauración no se puede realizar.  
  
-   Si se producen errores durante cualquier descifrado, se producirán errores en la restauración. Puede utilizar la opción FORCE para omitir los errores, pero esta opción provocará la pérdida de los datos que no sea posible descifrar.  
  
-   Si se cifró la clave maestra con la clave maestra de servicio, la clave maestra restaurada también se cifrará con la clave maestra de servicio.  
  
-   Si no hay una clave maestra en la base de datos actual, RESTORE MASTER KEY creará una clave maestra. La nueva clave maestra no se cifrará automáticamente con la clave maestra de servicio.  
  
###  <a name="Security"></a> Seguridad  
  
####  <a name="Permissions"></a> Permissions  
 Necesita el permiso CONTROL en la base de datos.  
  
##  <a name="SSMSProcedure"></a> Usar SQL Server Management Studio con Transact-SQL  
  
#### <a name="to-restore-the-database-master-key"></a>Para restaurar la clave maestra de una base de datos  
  
1.  Recupere una copia de seguridad de la clave maestra de la base de datos, ya sea desde un medio físico de copia de seguridad o desde un directorio del sistema de archivos local.  
  
2.  En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].  
  
3.  En la barra de Estándar, haga clic en **Nueva consulta**.  
  
4.  Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.  
  
    ```  
    -- Restores the database master key of the AdventureWorks2012 database.  
    USE AdventureWorks2012;  
    GO  
    RESTORE MASTER KEY   
        FROM FILE = 'c:\backups\keys\AdventureWorks2012_master_key'   
        DECRYPTION BY PASSWORD = '3dH85Hhk003#GHkf02597gheij04'   
        ENCRYPTION BY PASSWORD = '259087M#MyjkFkjhywiyedfgGDFD';  
    GO  
    ```  
  
    > [!NOTE]  
    >  La ruta de acceso de archivo a la clave y la contraseña de la clave (si existe) serán distintas de las que se indica más arriba. Asegúrese de que ambas son específicas para la instalación del servidor y de la clave.  
  
 Para obtener más información, vea [RESTORE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-master-key-transact-sql)  
  
  