---
title: Archivos de registro de seguimiento predeterminados deshabilitados | Microsoft Docs
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
- Best Practices [Database Engine]
ms.assetid: c27761e6-75ed-4ee4-a236-0cbc42e500a1
caps.latest.revision: 10
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 65b052c3282ca8609092c46850ee20d822ae51cb
ms.lasthandoff: 04/11/2017

---
# <a name="default-trace-log-files-disabled"></a>Archivos de registro de seguimiento predeterminados deshabilitados
  Esta regla comprueba el valor de la opción de procedimiento almacenado sp_configure default trace enabled para determinar si el seguimiento predeterminado está establecido en ON (1) o en OFF (0). Cuando esta opción está habilitada, el seguimiento predeterminado proporciona información sobre la configuración y los cambios de DDL de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]. En algunos casos, esta información puede ser útil para los clientes y el Servicio de atención al cliente y soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] al solucionar problemas con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].  
  
## <a name="best-practices-recommendations"></a>Prácticas recomendadas  
 Utilice el procedimiento almacenado sp_configure para habilitar el seguimiento estableciendo el valor de default trace enabled en 1.  
  
## <a name="for-more-information"></a>Para obtener más información  
 [Opciones de configuración de servidor &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md)  
  
## <a name="see-also"></a>Vea también  
 [Supervisar y aplicar las prácticas recomendadas usando la administración basada en directivas](../../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  