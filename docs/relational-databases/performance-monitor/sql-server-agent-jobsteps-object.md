---
title: JobSteps (objeto del Agente SQL Server) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JobSteps object
- SQLAgent:JobSteps
ms.assetid: 44f9983c-1753-4fe0-8475-973aa2460b3a
caps.latest.revision: 23
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 61884b4353e065c60f9489eca33a8979cf7d782f
ms.lasthandoff: 04/11/2017

---
# <a name="sql-server-agent-jobsteps-object"></a>JobSteps (objeto del Agente SQL Server)
  El objeto de rendimiento [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] JobSteps **del Agente** contiene contadores de rendimiento que informan sobre los pasos de trabajo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . En la siguiente tabla se enumeran los contadores incluidos en este objeto.  
  
 La siguiente tabla contiene los contadores de **SQLAgent:JobSteps** .  
  
|Nombre|Descripción|  
|----------|-----------------|  
|**Pasos activos**|Este contador muestra el número de pasos de trabajo que se están ejecutando actualmente.|  
|**Pasos en cola**|Este contador informa acerca del número de pasos de trabajo preparados para que el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] los ejecute, pero cuya ejecución aún no se ha iniciado.|  
|**Total de reintentos de pasos**|Este contador informa acerca del número total de veces que [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ha intentado ejecutar un paso de trabajo desde la última vez que se reinició el servidor.|  
  
 Cada contador del objeto contiene las instancias siguientes:  
  
|Instancia|Descripción|  
|--------------|-----------------|  
|**_Total**|Información de todos los pasos de trabajo.|  
|**ActiveScripting**|Información de los pasos de trabajo que utilizan el subsistema **ActiveScripting** .|  
|**ANALYSISCOMMAND**|Información de los pasos de trabajo que utilizan el subsistema ANALYSISCOMMAND.|  
|**ANALYSISQUERY**|Información de los pasos de trabajo que utilizan el subsistema ANALYSISQUERY.|  
|**CmdExec**|Información de los pasos de trabajo que utilizan el subsistema **CmdExec** .|  
|**Distribución**|Información de los pasos de trabajo que utilizan el subsistema **Distribution** .|  
|**Dts**|Información de los pasos de trabajo que utilizan el subsistema [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .|  
|**LogReader**|Información de los pasos de trabajo que utilizan el subsistema **LogReader** .|  
|**Mezcla**|Información de los pasos de trabajo que utilizan el subsistema **Merge** .|  
|**PowerShell**|Información de los pasos de trabajo que utilizan el subsistema **PowerShell** .|  
|**QueueReader**|Información de los pasos de trabajo que utilizan el subsistema **QueueReader** .|  
|**Snapshot**|Información de los pasos de trabajo que utilizan el subsistema **Snapshot** .|  
|**TSQL**|Información de los pasos de trabajo que ejecutan [!INCLUDE[tsql](../../includes/tsql-md.md)].|  
  
## <a name="see-also"></a>Vea también  
 [Administrar pasos de trabajo](http://msdn.microsoft.com/library/51352afc-a0a4-428b-8985-f9e58bb57c31)   
 [Usar objetos de rendimiento](http://msdn.microsoft.com/library/830b843a-6b2a-4620-a51b-98358e9fc54b)   
 [Supervisar el uso de recursos &#40;Monitor de sistema&#41;](../../relational-databases/performance-monitor/monitor-resource-usage-system-monitor.md)  
  
  