---
title: "Cambio de la configuración del grupo de cargas de trabajo | Microsoft Docs"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- workload groups [SQL Server], alter
- Resource Governor, workload group alter
ms.assetid: 73b6109c-2ad0-4915-b11b-d40d5a0fdc25
caps.latest.revision: 15
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 7ee33f07052addb06e1dd2fe56f6153498fdbc9b
ms.lasthandoff: 04/11/2017

---
# <a name="change-workload-group-settings"></a>Cambiar la configuración del grupo de cargas de trabajo
  Puede modificar la configuración de un grupo de cargas de trabajo utilizando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].  
  
-   **Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)  
  
-   **To change the settings for a workload group, using:**  [SQL Server Management Studio](#ChgWGProp), [Transact-SQL](#ChgWGTSQL)  
  
## <a name="before-you-begin"></a>Antes de empezar  
  
###  <a name="LimitationsRestrictions"></a> Limitaciones y restricciones  
 Puede cambiar la configuración del grupo de cargas de trabajo predeterminado y los grupos de cargas de trabajo definidos por el usuario.  
  
 **REQUEST_MAX_MEMORY_GRANT_PERCENT**  
  
 La memoria consumida por la creación de índices en una tabla con particiones no alineada es proporcional al número de particiones involucradas. Si la memoria total necesaria supera el límite por consulta (REQUEST_MAX_MEMORY_GRANT_PERCENT) impuesto por la configuración del grupo de cargas de trabajo, puede que esta creación de índices produzca un error. Dado que el grupo de cargas de trabajo predeterminado permite que una consulta supere el límite por consulta con la memoria mínima necesaria para iniciar la compatibilidad con SQL Server 2005, es posible que el usuario pueda ejecutar la misma creación de índices en el grupo de cargas de trabajo predeterminado si el grupo de recursos de servidor predeterminado tiene configurada una memoria total suficiente para ejecutar una consulta.  
  
 Se permite la creación de índices para usar más memoria del área de trabajo que la concedida inicialmente para mejorar el rendimiento. El regulador de recursos admite este tratamiento especial; sin embargo, la concesión inicial y cualquier concesión de memoria adicional están limitadas por la configuración del grupo de cargas de trabajo y el grupo de recursos de servidor.  
  
###  <a name="Permissions"></a> Permisos  
 Cambiar la configuración del grupo de cargas de trabajo requiere el permiso CONTROL SERVER.  
  
##  <a name="ChgWGProp"></a> Cambiar la configuración del grupo de cargas de trabajo mediante SQL Server Management Studio  
 **Para cambiar la configuración del grupo de cargas de trabajo utilizando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**  
  
1.  En el Explorador de objetos, expanda de forma recursiva el nodo **Management** hasta e incluida la carpeta **Grupos de cargas de trabajo** que contiene el grupo de cargas de trabajo que se va a modificar.  
  
2.  Haga clic con el botón derecho en el grupo de cargas de trabajo que se va a modificar y, después, haga clic en **Propiedades**.  
  
3.  En la página **Propiedades del regulador de recursos** , seleccione la fila del grupo de cargas de trabajo en la cuadrícula **Grupos de cargas de trabajo del grupo de recursos de servidor** si no está seleccionada automáticamente.  
  
4.  Haga clic o doble clic en las celdas de la fila que va a cambiar y especifique los nuevos valores.  
  
5.  Haga clic en **Aceptar**para guardar los cambios.  
  
##  <a name="ChgWGTSQL"></a> Cambiar la configuración del grupo de cargas de trabajo mediante Transact-SQL  
 **Para cambiar la configuración del grupo de cargas de trabajo utilizando Transact-SQL**  
  
1.  Ejecute la instrucción ALTER WORKLOAD GROUP especificando los valores de propiedad que desea cambiar.  
  
2.  Ejecute la instrucción ALTER RESOURCE GOVERNOR RECONFIGURE.  
  
### <a name="example-transact-sql"></a>Ejemplo (Transact-SQL)  
 En el siguiente ejemplo se cambia el porcentaje de concesión de memoria máxima del grupo de cargas de trabajo denominado `groupAdhoc`.  
  
```  
ALTER WORKLOAD GROUP groupAdhoc  
WITH (REQUEST_MAX_MEMORY_GRANT_PERCENT = 30);  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a>Vea también  
 [Regulador de recursos](../../relational-databases/resource-governor/resource-governor.md)   
 [Crear un grupo de cargas de trabajo](../../relational-databases/resource-governor/create-a-workload-group.md)   
 [Crear un grupo de recursos de servidor](../../relational-databases/resource-governor/create-a-resource-pool.md)   
 [Cambiar la configuración del grupo de recursos de servidor](../../relational-databases/resource-governor/change-resource-pool-settings.md)   
 [ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](../../t-sql/statements/alter-workload-group-transact-sql.md)   
 [ALTER RESOURCE POOL &#40;Transact-SQL&#41;](../../t-sql/statements/alter-resource-pool-transact-sql.md)   
 [ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;](../../t-sql/statements/alter-resource-governor-transact-sql.md)  
  
  