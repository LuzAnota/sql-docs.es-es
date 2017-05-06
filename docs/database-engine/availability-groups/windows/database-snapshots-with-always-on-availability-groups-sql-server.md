---
title: "Instant&#225;neas de bases de datos con grupos de disponibilidad AlwaysOn (SQL Server) | Microsoft Docs"
ms.custom: ""
ms.date: "05/17/2016"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dbe-high-availability"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "instantáneas de bases de datos [SQL Server], grupos de disponibilidad AlwaysOn"
  - "Grupos de disponibilidad [SQL Server], interoperabilidad"
ms.assetid: 7432da1c-ce2f-4cd9-af41-54c97744166b
caps.latest.revision: 7
author: "MikeRayMSFT"
ms.author: "mikeray"
manager: "jhubbard"
caps.handback.revision: 7
---
# Instant&#225;neas de bases de datos con grupos de disponibilidad AlwaysOn (SQL Server)
[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx_md](../../../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

  Puede crear una instantánea de base de datos en una base de datos primaria o secundaria en un grupo de disponibilidad. El rol de réplica debe ser PRIMARY o SECONDARY y no debe encontrarse en el estado RESOLVING.  
  
 Se recomienda que el estado de sincronización de la base de datos sea SYNCHRONIZING o SYNCHRONIZED cuando se crea una instantánea de base de datos. Sin embargo, las instantáneas de base de datos pueden crearse cuando el estado de sincronización de la base de datos sea NOT SYNCHRONIZING.  
  
 Una instantánea de base de datos debe seguir funcionando aunque la réplica se DESCONECTE de la réplica primaria.  
  
 Algunas condiciones de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] pueden hacer que la base de datos de origen y sus instantáneas de base de datos se reinicien y desconecten temporalmente a los usuarios. Estas condiciones son:  
  
-   La réplica principal cambia los roles, ya sea porque la réplica principal actual se queda sin conexión y vuelve a conectarse en la misma instancia del servidor o porque se produce un error en el grupo de disponibilidad.  
  
-   La base de datos entra en el rol secundario.  
  
 Si se produce una conmutación por error de la réplica de disponibilidad que hospeda las instantáneas de base de datos, estas permanecen en la instancia del servidor donde se crearon. Los usuarios pueden seguir usando las instantáneas tras la conmutación por error. Si el rendimiento es importante en el entorno, se recomienda crear instantáneas de base de datos solo en las bases de datos secundarias que estén hospedadas por una réplica secundaria configurada para el modo de conmutación por error manual.  Si alguna vez realiza una conmutación por error manual del grupo de disponibilidad en esta réplica secundaria, puede crear un conjunto de instantáneas de base de datos en otra réplica secundaria, redirigir a los clientes a las nuevas instantáneas de base de datos y quitar todas las instantáneas de las bases de datos principales.  
  
## Vea también  
 [Información general de los grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](../../../database-engine/availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md)   
 [Instantáneas de bases de datos &#40;SQL Server&#41;](../../../relational-databases/databases/database-snapshots-sql-server.md)  
  
  