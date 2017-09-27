---
title: RAND (Transact-SQL) | Documentos de Microsoft
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- RAND
- RAND_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- RAND function
- values [SQL Server], random float
- random float value
ms.assetid: 363c84d6-b9fa-49ba-9a75-e44f27535ff6
caps.latest.revision: 22
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: b1d358122487d3568167021ac3a296e1eb2d1974
ms.contentlocale: es-es
ms.lasthandoff: 09/01/2017

---
# <a name="rand-transact-sql"></a>RAND (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-asdw-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-asdw-xxx-md.md)]

  Devuelve un seudoaleatorios **float** valor comprendido entre 0 y 1, ambos excluidos.  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
RAND ( [ seed ] )  
```  
  
## <a name="arguments"></a>Argumentos  
 *valor de inicialización*  
 Es un número entero [expresión](../../t-sql/language-elements/expressions-transact-sql.md) (**tinyint**, **smallint**, o **int**) que proporciona el valor de inicialización. Si *inicialización* no se especifica, el [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] asigna un valor de inicialización de forma aleatoria. Para un valor de inicialización especificado, el resultado devuelto es siempre el mismo.  
  
## <a name="return-types"></a>Tipos devueltos  
 **float**  
  
## <a name="remarks"></a>Comentarios  
 Las llamadas repetitivas de RAND() con el mismo valor de inicialización devuelven los mismos resultados.  
  
 Para una conexión, si se llama a RAND() con el valor de inicialización especificado, todas las llamadas posteriores de RAND() generan resultados basados en la llamada a RAND() inicializada. Por ejemplo, la siguiente consulta siempre devuelve la misma secuencia de números.  
  
```  
SELECT RAND(100), RAND(), RAND()   
```  
  
## <a name="examples"></a>Ejemplos  
 En el siguiente ejemplo se producen cuatro números aleatorios diferentes, generados con la función RAND.  
  
```  
DECLARE @counter smallint;  
SET @counter = 1;  
WHILE @counter < 5  
   BEGIN  
      SELECT RAND() Random_Number  
      SET @counter = @counter + 1  
   END;  
GO  
```  
  
## <a name="see-also"></a>Vea también  
 [Funciones matemáticas &#40; Transact-SQL &#41;](../../t-sql/functions/mathematical-functions-transact-sql.md)  
  
  