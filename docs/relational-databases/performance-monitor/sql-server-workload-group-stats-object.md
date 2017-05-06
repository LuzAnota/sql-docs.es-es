---
title: "Objeto SQL Server: Estadísticas de grupo de cargas de trabajo | Microsoft Docs"
ms.custom:
- SQL2016_New_Updated
ms.date: 12/04/2015
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Workload Group Stats object
- 'SQLServer: Workload Group Stats'
ms.assetid: ca20e4f6-50ec-4456-900d-87d280fde2b3
caps.latest.revision: 14
author: BYHAM
ms.author: rickbyh
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 668f0f7cf7b38fb18144e58cccbc7e4902a39f75
ms.lasthandoff: 04/11/2017

---
# <a name="sql-server-workload-group-stats-object"></a>Objeto SQL Server: Estadísticas de grupo de cargas de trabajo
  El objeto SQLServer:Estadísticas de grupo de cargas de trabajo contiene contadores de rendimiento que notifican información sobre las estadísticas de grupo de cargas de trabajo del regulador de recursos.  
  
 Cada grupo de cargas de trabajo activo crea una instancia del objeto de rendimiento SQLServer:Estadísticas de grupo de cargas de trabajo que tiene el mismo nombre de instancia que el grupo de cargas de trabajo del regulador de recursos. En la tabla siguiente se describen los contadores admitidos en esta instancia.  
  
|Nombre de contador|Descripción|  
|------------------|-----------------|  
|**Subprocesos paralelos activos**|Recuento actual de uso de subprocesos paralelos.|  
|**Solicitudes activas**|El número de solicitudes que están ejecutándose actualmente en este grupo de cargas de trabajo. Este número debería ser equivalente al recuento de filas procedentes de sys.dm_exec_requests filtrado por identificador de grupo.|  
|**Solicitudes bloqueadas**|Número actual de solicitudes bloqueadas en el grupo de cargas de trabajo. Este número se puede utilizar para determinar las características de la carga de trabajo.|  
|**% de CPU retrasada**|CPU del sistema retrasada para todas las solicitudes de la instancia especificada del objeto de rendimiento como porcentaje del tiempo total activo.| 
|**Base de % de CPU retrasada**|Exclusivamente para uso interno.| 
|**% efectivo de la CPU**|Uso de CPU del sistema por todas las solicitudes de la instancia especificada del objeto de rendimiento como porcentaje del tiempo total activo.| 
|**Base de % efectivo de la CPU**|Exclusivamente para uso interno.| 
|**% de uso de CPU**|Uso del ancho banda de CPU por parte de todas las solicitudes en este grupo de cargas de trabajo medidas en relación al equipo y normalizadas con respecto a todas las CPU del sistema. Este valor cambiará a medida que la cantidad de CPU disponible para el proceso de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] varíe. No se normaliza respecto a lo que el proceso de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] recibe.| 
|**Base de % de uso de la CPU**|Exclusivamente para uso interno.| 
|**% de CPU infringida**|Diferencia entre la reserva de CPU y el porcentaje de programación efectiva.|  
|**Tiempo máximo de CPU por solicitud (ms)**|Tiempo de CPU máximo, en milisegundos, utilizado por una solicitud actualmente en ejecución en el grupo de cargas de trabajo.|  
|**Concesión máxima de memoria de solicitud (KB)**|Valor máximo de concesión de memoria, en kilobytes (KB), para una consulta.|  
|**Optimizaciones de consultas/s**|Número de optimizaciones de consultas por segundo que han tenido lugar en este grupo de cargas de trabajo. Este número se puede utilizar para determinar las características de la carga de trabajo.|  
|**Solicitudes en cola**|Número actual de solicitudes en cola que esperan ser recogidas. Este número puede ser distinto de cero si se produce una limitación una vez alcanzado el límite GROUP_MAX_REQUESTS.|  
|**Concesiones con memoria reducida/s**|Número de consultas que obtienen una cantidad de concesiones de memoria por debajo de la cantidad ideal por segundo.|  
|**Solicitudes completadas/s**|Número de solicitudes que se han completado en este grupo de cargas de trabajo. Este número es acumulativo.|  
|**Planes poco óptimos/s**|Número de planes poco óptimos que se generan en este grupo de cargas de trabajo por segundo.|  
  
## <a name="see-also"></a>Vea también  
 [Supervisar el uso de recursos &#40;Monitor de sistema&#41;](../../relational-databases/performance-monitor/monitor-resource-usage-system-monitor.md)   
 [Objeto SQL Server: Estadísticas de grupo de recursos de servidor](../../relational-databases/performance-monitor/sql-server-resource-pool-stats-object.md)   
 [Regulador de recursos](../../relational-databases/resource-governor/resource-governor.md)  
  
  
