---
title: Detección de metadatos | Documentos de Microsoft
description: Detección de metadatos en el controlador OLE DB para SQL Server
ms.custom: ''
ms.date: 03/26/2018
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: ''
ms.component: oledb|features
ms.reviewer: ''
ms.suite: sql
ms.technology:
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
author: pmasl
ms.author: Pedro.Lopes
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 5990632392ec4656af7f655fcbd1b19b29346066
ms.sourcegitcommit: 9f4330a4b067deea396b8567747a6771f35e6eee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2018
---
# <a name="metadata-discovery"></a>Detección de metadatos
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

  La mejora de la detección de metadatos en [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] permite que el controlador OLE DB para las aplicaciones de SQL Server para asegurarse de esa columna o metadatos del parámetro devuelto de la ejecución de una consulta son idénticos o compatibles con el formato de metadatos especificados antes de ejecuta la consulta. Se producirá un error si los metadatos devueltos tras la ejecución de la consulta no son compatibles con el formato de los metadatos especificados antes de la ejecución de la consulta.  
  
 En bcp y las interfaces IBCPSession e IBCPSession2, ahora puede especificar un retraso lectura (detección de metadatos diferida) para evitar la detección de metadatos de salida operaciones de consulta. De este modo, mejora el rendimiento y se eliminan los errores de detección de metadatos.  
  
 Si desarrolla una aplicación utilizando el controlador OLE DB para SQL Server pero se conecta a una versión de servidor anterior a [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], funcionalidad se corresponderá con la versión del servidor de detección de metadatos.  
  
## <a name="remarks"></a>Comentarios   
 Las funciones miembro de OLE DB siguientes se han perfeccionado en [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] para proporcionar una detección de metadatos mejorada:  
  
-   IColumnsInfo::GetColumnInfo  
  
-   IColumnsRowset::GetColumnsRowset  
  
-   ICommandWithParameters:: GetParameterInfo (vea [ICommandWithParameters](../../oledb/ole-db-interfaces/icommandwithparameters.md) para obtener más información)  
  
 También verá una mejora del rendimiento cuando se especifica el formato de metadatos utilizando IBCPSession::BCPSetBulkMode  
  
 La detección de metadatos mejorada en el controlador OLE DB para SQL Server es posible debido a la adición de dos procedimientos almacenados de [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]:  
  
-   sp_describe_first_result_set  
  
-   sp_describe_undeclared_parameters  
  
## <a name="see-also"></a>Vea también  
 [Controlador OLE DB para características de SQL Server](../../oledb/features/oledb-driver-for-sql-server-features.md)  
  
  