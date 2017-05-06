---
title: "Consultar los par&#225;metros usados para crear un modelo de miner&#237;a de datos | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "analysis-services"
  - "analysis-services/data-mining"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "consultas de contenido [DMX]"
ms.assetid: ce7719e0-6127-4d9c-a753-0e0a3db065e1
caps.latest.revision: 13
author: "Minewiskan"
ms.author: "owend"
manager: "jhubbard"
caps.handback.revision: 13
---
# Consultar los par&#225;metros usados para crear un modelo de miner&#237;a de datos
  La composición de un modelo de minería de datos no solo se ve afectada por los casos de entrenamiento, sino también por los parámetros que se establecieron al crear el modelo. Por lo tanto, es posible que la recuperación de la configuración de parámetros de un modelo existente resulte de utilidad para comprender mejor el comportamiento del modelo. La recuperación de parámetros también resulta útil al documentar una versión determinada del modelo.  
  
 Para buscar los parámetros que se utilizaron al crear el modelo, cree una consulta en uno de los conjuntos de filas de esquema del modelo de minería de datos. En [!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)], estos conjuntos de filas de esquema se exponen como un conjunto de vistas del sistema que se pueden consultar fácilmente mediante la sintaxis de Transact-SQL. Este procedimiento describe cómo crear una consulta que devuelva los parámetros que se utilizaron para crear el modelo de minería de datos especificado.  
  
### Para abrir una ventana Consulta para una consulta de conjunto de filas de esquema  
  
1.  En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], abra la instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que contiene el modelo que desea consultar.  
  
2.  Haga clic con el botón derecho en el nombre de la instancia, seleccione **Nueva consulta** y, después, seleccione **DMX**.  
  
    > [!NOTE]  
    >  También puede crear una consulta en un modelo de minería de datos usando la plantilla **MDX**.  
  
3.  Si la instancia contiene varias bases de datos, seleccione la base de datos que contiene el modelo que desea consultar en la lista **Bases de datos disponibles** de la barra de herramientas.  
  
### Para devolver los parámetros de un modelo de minería de datos existente  
  
1.  En el panel de consulta DMX, escriba o pegue el texto siguiente:  
  
    ```  
    SELECT MINING_PARAMETERS  
    FROM $system.DMSCHEMA_MINING_MODELS  
    WHERE MODEL_NAME = ''  
    ```  
  
2.  En el Explorador de objetos, seleccione el modelo de minería de datos que desee y, a continuación, arrástrelo hasta el panel Consulta DMX y sitúelo entre las comillas simples.  
  
3.  Presione F5 o haga clic en **Ejecutar**.  
  
## Ejemplo  
 El código siguiente devuelve una lista de los parámetros que se utilizaron para crear el modelo de minería de datos generado en el [Basic Data Mining Tutorial](../Topic/Basic%20Data%20Mining%20Tutorial.md). Estos parámetros incluyen los valores explícitos para cualquier parámetro predeterminado utilizado por los servicios de minería de datos ofrecidos por los proveedores en el servidor.  
  
```  
SELECT MINING_PARAMETERS   
FROM $system.DMSCHEMA_MINING_MODELS  
WHERE MODEL_NAME = 'TM Clustering'  
```  
  
 En el ejemplo de código se devuelven los parámetros siguientes para el modelo de agrupación en clústeres:  
  
 Resultados del ejemplo:  
  
 MINING_PARAMETERS  
  
 CLUSTER_COUNT=10,CLUSTER_SEED=0,CLUSTERING_METHOD=1,MAXIMUM_INPUT_ATTRIBUTES=255,MAXIMUM_STATES=100,MINIMUM_SUPPORT=1,MODELLING_CARDINALITY=10,SAMPLE_SIZE=50000,STOPPING_TOLERANCE=10  
  
## Vea también  
 [Tareas y procedimientos de Consulta de minería de datos](../../analysis-services/data-mining/data-mining-query-tasks-and-how-tos.md)   
 [Consultas de minería de datos](../../analysis-services/data-mining/data-mining-queries.md)  
  
  