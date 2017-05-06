---
title: "Grupo de disponibilidad no preparado para conmutaci&#243;n autom&#225;tica por error | Microsoft Docs"
ms.custom: ""
ms.date: "05/17/2016"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dbe-high-availability"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.swb.agdashboard.agp3autofailover.issues.f1"
helpviewer_keywords: 
  - "Grupos de disponibilidad [SQL Server], directivas"
ms.assetid: 28261014-342c-442a-bd89-6d04b8d4e8b7
caps.latest.revision: 12
author: "MikeRayMSFT"
ms.author: "mikeray"
manager: "jhubbard"
caps.handback.revision: 12
---
# Grupo de disponibilidad no preparado para conmutaci&#243;n autom&#225;tica por error
    
## Introducción  
  
|||  
|-|-|  
|**Nombre de directiva**|Preparación para la conmutación automática por error del grupo de disponibilidad|  
|**Problema**|Grupo de disponibilidad no preparado para conmutación automática por error.|  
|**Categoría**|**Crítico**|  
|**Faceta**|Grupo de disponibilidad|  
  
## Descripción  
 Esta directiva realiza comprobaciones para asegurarse de que el grupo de disponibilidad tenga al menos una réplica secundaria que esté preparada para la conmutación por error. La directiva está en mal estado y se genera una alerta cuando el modo de conmutación por error de la réplica principal es automático, pero ninguna de las réplicas secundarias del grupo de disponibilidad están listas para la conmutación por error.  
  
 La directiva está en un estado correcto cuando al menos una réplica secundaria está lista para la conmutación automática por error.  
  
> [!NOTE]  
>  En esta versión de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], la información sobre las posibles causas y soluciones se encuentra en el artículo [El grupo de disponibilidad no está listo para la conmutación automática por error](http://go.microsoft.com/fwlink/p/?LinkId=220851) en TechNet Wiki.  
  
## Posibles causas  
 Grupo de disponibilidad no preparado para la conmutación automática por error. La réplica principal está configurada para la conmutación automática por error; sin embargo, la réplica secundaria no está lista para la conmutación automática por error. La réplica secundaria configurada para la conmutación automática por error podría no estar disponible o su estado de sincronización de datos no es actualmente SYNCHRONIZED.  
  
## Soluciones posibles  
 Las siguientes son posibles soluciones para este problema:  
  
-   Compruebe que al menos una réplica secundaria está configurada como conmutación automática por error. Si no hay una réplica secundaria configurada como conmutación automática por error, actualice la configuración de una réplica secundaria para que sea el destino de la conmutación automática por error con confirmación sincrónica.  
  
-   Use la directiva para comprobar que los datos están en un estado de sincronización y el destino de la conmutación automática por error es SYNCHRONIZED y, a continuación, resuelva el problema en la réplica de disponibilidad.  
  
## Vea también  
 [Información general de los grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](../../../database-engine/availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md)   
 [Usar el Panel de AlwaysOn &#40;SQL Server Management Studio&#41;](../../../database-engine/availability-groups/windows/use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  