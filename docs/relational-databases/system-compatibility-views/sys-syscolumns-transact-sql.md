---
title: Sys.syscolumns (Transact-SQL) | Documentos de Microsoft
ms.custom: 
ms.date: 03/15/2017
ms.prod: sql-non-specified
ms.prod_service: database-enginel, sql-data-warehouse, pdw
ms.service: 
ms.component: system-compatibility-views
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sys.syscolumns
- sys.syscolumns_TSQL
- syscolumns_TSQL
- syscolumns
dev_langs: TSQL
helpviewer_keywords:
- syscolumns system table
- sys.syscolumns compatibility view
ms.assetid: 863fd87b-ff33-4ac5-9aa9-df21140681da
caps.latest.revision: "32"
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: On Demand
ms.openlocfilehash: 94f43de0bf804d366b599c053d8dddadf51d809f
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2017
---
# <a name="syssyscolumns-transact-sql"></a>sys.syscolumns (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-ss2008-xxxx-asdw-pdw-md.md)]

  Devuelve una fila por cada columna de cada tabla y vista, y una fila por cada parámetro de un procedimiento almacenado de la base de datos.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssnoteCompView](../../includes/ssnotecompview-md.md)]  
  
|Nombre de columna|Tipo de datos|Description|  
|-----------------|---------------|-----------------|  
|**Nombre**|**sysname**|Nombre de la columna o parámetro de procedimiento.|  
|**id**|**int**|Id. de objeto de la tabla a la que pertenece la columna o Id. del procedimiento almacenado al que está asociado el parámetro.|  
|**alguno**|**tinyint**|Tipo de almacenamiento físico de **sys.types**.|  
|**typestat**|**tinyint**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**xusertype**|**smallint**|Id. del tipo de datos extendido definido por el usuario. Produce un desbordamiento o devuelve NULL si el número de tipos de datos es superior a 32.767.|  
|**longitud**|**smallint**|Longitud máxima de almacenamiento físico de **sys**. **tipos de**.|  
|**xprec**|**tinyint**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**XScale**|**tinyint**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**colid**|**smallint**|Id. de columna o parámetro.|  
|**XOffset**|**smallint**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**bitpos**|**tinyint**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**reservado**|**tinyint**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**colstat**|**smallint**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**cdefault**|**int**|Id. del valor predeterminado de esta columna.|  
|**dominio**|**int**|Id. de la regla o restricción CHECK de esta columna.|  
|**número**|**smallint**|Número del subprocedimiento cuando el procedimiento está agrupado.<br /><br /> 0 = Entradas que no son de procedimiento|  
|**colorder**|**smallint**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**autoval**|**varbinary (8000)**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**desplazamiento**|**smallint**|Desplazamiento en la fila en la que aparece esta columna.|  
|**collationid**|**int**|Id. de la intercalación de la columna. Es NULL para columnas no basadas en caracteres.|  
|**status**|**tinyint**|Mapa de bits utilizado para describir una propiedad de la columna o parámetro:<br /><br /> 0x08 = La columna admite valores NULL.<br /><br /> 0 x 10 = relleno ANSI activado al **varchar** o **varbinary** se han agregado las columnas. Se conservan los espacios en blanco **varchar** y se conservan los ceros finales **varbinary** columnas.<br /><br /> 0x40 = El parámetro es de tipo OUTPUT.<br /><br /> 0x80 = La columna es de identidad.|  
|**tipo**|**tinyint**|Tipo de almacenamiento físico de **sys**. **tipos de**.|  
|**usertype**|**smallint**|Id. del tipo de datos definido por el usuario de **sys.types**. Produce un desbordamiento o devuelve NULL si el número de tipos de datos es superior a 32.767.|  
|**printfmt**|**varchar (255)**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**Prec**|**smallint**|Nivel de precisión de la columna.<br /><br /> -1 = **xml** o tipo de valor grande.|  
|**escala**|**int**|Escala de esta columna.<br /><br /> NULL = El tipo de datos no es numérico.|  
|**es calculado**|**int**|Marca que señala si es una columna calculada:<br /><br /> 0 = No calculada<br /><br /> 1 = Calculada|  
|**isoutparam**|**int**|Indica si el parámetro de procedimiento es un parámetro de salida:<br /><br /> 1 = True<br /><br /> 0 = False|  
|**IsNullable**|**int**|Indica si la columna admite valores NULL:<br /><br /> 1 = True<br /><br /> 0 = False|  
|**intercalación**|**sysname**|Nombre de la intercalación de la columna. Es NULL si la columna no está basada en caracteres.|  
  
## <a name="see-also"></a>Vea también  
 [Asignar tablas del sistema a vistas del sistema &#40; Transact-SQL &#41;](../../relational-databases/system-tables/mapping-system-tables-to-system-views-transact-sql.md)   
 [Vistas de compatibilidad &#40;Transact-SQL&#41;](~/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql.md)  
  
  