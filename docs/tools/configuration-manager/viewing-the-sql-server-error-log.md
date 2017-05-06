---
title: "Ver el registro de errores de SQL Server | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ciclos del registro de errores de SQL Server"
  - "ver el registro de errores de SQL Server"
  - "errores [SQL Server], registros"
  - "registro de errores de SQL Server"
  - "mostrar el registro de errores de SQL Server"
  - "registros [SQL Server], registros de errores de SQL Server"
ms.assetid: 6908c21a-65e3-458f-a272-fee256d86448
caps.latest.revision: 24
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 24
---
# Ver el registro de errores de SQL Server
  Eche un vistazo al registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para asegurarse de que los procesos se han completado correctamente (por ejemplo, operaciones de copias de seguridad y restauración, comandos de un proceso por lotes u otros scripts o procesos). Esto puede resultar útil para detectar áreas con problemas actuales o posibles, incluidos mensajes de recuperación automática (especialmente si se ha detenido y reiniciado una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]), mensajes del kernel u otros mensajes de error de nivel de servidor.  
  
 Para ver el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , utilice [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o cualquier procesador de texto. Para obtener más información sobre cómo ver el registro de errores, vea [Open Log File Viewer](../../relational-databases/logs/open-log-file-viewer.md). De forma predeterminada, el registro de error se encuentra en los archivos `Program Files\Microsoft SQL Server\MSSQL.`*n*`\MSSQL\LOG\ERRORLOG` y `ERRORLOG.`*n* .  
  
 Cada vez que se inicia una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], se crea un registro de errores, pero se puede usar el procedimiento almacenado del sistema [sp_cycle_errorlog](../../relational-databases/system-stored-procedures/sp-cycle-errorlog-transact-sql.md) para cambiar los archivos de registro de errores sin tener que reiniciar la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Normalmente, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conserva copias de seguridad de los últimos seis registros y asigna a la copia de seguridad de registros más reciente la extensión .1, a la segunda más reciente la extensión .2 y así sucesivamente. El registro de errores actual no tiene ninguna extensión.  
  
 Tenga en cuenta que también puede ver las instancias del registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que están sin conexión o no se pueden iniciar. Para obtener más información, vea [Ver sin conexión archivos de registro](../../relational-databases/logs/view-offline-log-files.md).  
  
  