---
title: remote admin connections (opción de configuración del servidor) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- administrator connections [SQL Server]
- DAC
- connections [SQL Server], dedicated administrator
- remote admin connections option
- dedicated administrator connections [SQL Server]
ms.assetid: bf32b60a-7a48-401f-b6be-b5e2e46c413f
caps.latest.revision: 15
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: 35113a648a66b1122e7bf92785fab7bd7aaa1317
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36203482"
---
# <a name="remote-admin-connections-server-configuration-option"></a>remote admin connections (opción de configuración del servidor)
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proporciona una conexión de administrador dedicada (DAC). La conexión DAC permite a los administradores tener acceso al servidor en ejecución a fin de realizar funciones de diagnóstico o ejecutar instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] , o para solucionar problemas del servidor incluso cuando está bloqueado o se ejecuta en un estado anormal, y no responde a ninguna conexión de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] . De forma predeterminada, la conexión DAC solo está disponible en un cliente del servidor. Para habilitar las aplicaciones cliente en equipos remotos de modo que usen la DAC, utilice la opción remote admin connections de sp_configure.  
  
 De forma predeterminada, la DAC solo escucha en la dirección IP de bucle invertido (127.0.0.1) a través del puerto 1434. Si el puerto TCP 1434 no está disponible, se asigna dinámicamente un puerto TCP al iniciarse [!INCLUDE[ssDE](../../includes/ssde-md.md)] . Cuando haya más de una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instalada en un equipo, compruebe en el registro de errores el número de puerto TCP.  
  
 En la siguiente tabla se muestran los posibles valores para la opción remote admin connections.  
  
|Valor|Descripción|  
|-----------|-----------------|  
|0|Indica que solo se permiten conexiones locales mediante la DAC.|  
|1|Indica que la DAC permite las conexiones remotas.|  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo permite utilizar una DAC desde un equipo remoto.  
  
```  
sp_configure 'remote admin connections', 1;  
GO  
RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a>Vea también  
 [Conexión de diagnóstico para administradores de bases de datos](diagnostic-connection-for-database-administrators.md)  
  
  