---
title: Propiedades personalizadas de Excel | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bdcc72b8-8950-47bd-88bf-5db6d48cc6bf
caps.latest.revision: 8
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: e7d5c7df84ed001aa969f3fb164fa9691670fc3e
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36106803"
---
# <a name="excel-custom-properties"></a>Propiedades personalizadas de Excel
  **Propiedades personalizadas de origen**  
  
 El origen de Excel tiene propiedades personalizadas y propiedades comunes a todos los componentes de flujo de datos.  
  
 En la tabla siguiente se describen las propiedades personalizadas del origen de Excel. Todas las propiedades son de lectura y escritura.  
  
|Nombre de propiedad|Tipo de datos|Descripción|  
|-------------------|---------------|-----------------|  
|AccessMode|Integer|Modo que se usa para tener acceso a la base de datos. Los valores posibles son **conjuntos de filas abiertos**, **Open Rowset from Variable**, `SQL Command`, y **comando SQL de Variable**. El valor predeterminado es **Open Rowset**.|  
|CommandTimeout|Integer|Número de segundos que tienen que transcurrir antes de que un comando supere el tiempo de espera.  El valor 0 indica un tiempo infinito.<br /><br /> **Nota** : esta propiedad no está disponible en el **Editor de origen de Excel**, pero se puede establecer con el **Editor avanzado**.|  
|OpenRowset|String|Nombre del objeto de base de datos que se usa para abrir un conjunto de filas.|  
|OpenRowsetVariable|String|Variable que contiene el objeto del objeto de base de datos que se usa para abrir un conjunto de filas.|  
|ParameterMapping|String|Asignación de los parámetros del comando SQL a variables.|  
|SqlCommand|String|Comando SQL que se va a ejecutar.|  
|SqlCommandVariable|String|Variable que contiene el comando SQL que se va a ejecutar.|  
  
 La salida y las columnas de salida del origen de Excel no tienen ninguna propiedad personalizada.  
  
 Para más información, consulte [Excel Source](excel-source.md).  
  
 **Propiedades personalizadas de los destinos**  
  
 El destino de Excel tiene propiedades personalizadas y propiedades comunes a todos los componentes de flujo de datos.  
  
 En la tabla siguiente se describen las propiedades personalizadas del destino Excel. Todas las propiedades son de lectura y escritura.  
  
|Nombre de propiedad|Tipo de datos|Descripción|  
|-------------------|---------------|-----------------|  
|AccessMode|Integer (enumeración)|Valor que especifica cómo tiene acceso el destino a su base de datos de destino.<br /><br /> Esta propiedad admite cualquiera de los siguientes valores:<br /><br /> `OpenRowset` (0), proporcione el nombre de una tabla o vista.<br /><br /> `OpenRowset from Variable` (1), debe proporcionar el nombre de una variable que contiene el nombre de una tabla o vista.<br /><br /> `OpenRowset Using Fastload` (3): se proporciona el nombre de una tabla o vista.<br /><br /> `OpenRowset Using Fastload from Variable` (4), debe proporcionar el nombre de una variable que contiene el nombre de una tabla o vista.<br /><br /> `SQL Command` (2): se proporciona una instrucción SQL.|  
|CommandTimeout|Integer|Número máximo de segundos que el comando SQL se puede ejecutar antes de superar el tiempo de espera. Si el valor es **0** , indica un tiempo infinito. El valor predeterminado de esta propiedad es **0**.<br /><br /> Nota: Esta propiedad no está disponible en el **Editor de destino de Excel**, pero se puede establecer con el **Editor avanzado**.|  
|FastLoadKeepIdentity|Boolean|Valor que especifica si se copian los valores de identidad cuando se cargan los datos. Esta propiedad solo está disponible cuando se usa una de las opciones de carga rápida. El valor predeterminado de esta propiedad es **False**.|  
|FastLoadKeepNulls|Boolean|Valor que especifica si se copian los valores Null cuando se cargan los datos. Esta propiedad solo está disponible con una de las opciones de carga rápida. El valor predeterminado de esta propiedad es **False**.|  
|FastLoadMaxInsertCommitSize|Integer|Valor que especifica el tamaño de lote que el destino de Excel intenta confirmar en operaciones de carga rápida. El valor predeterminado es **2147483647**. Un valor de **0** indica una operación de confirmación única después de que se procesen todas las filas.|  
|FastLoadOptions|String|Colección de opciones de carga rápida. Las opciones de carga rápida incluyen el bloqueo de las tablas y la comprobación de las restricciones. Puede especificar una, ambas o ninguna.<br /><br /> Nota: Algunas opciones de esta propiedad no están disponibles en el **Editor de destino de Excel**, pero pueden establecerse con el **Editor avanzado**.|  
|OpenRowset|String|Cuando AccessMode es `OpenRowset`, el nombre de la tabla o vista que tiene acceso el destino de Excel.|  
|OpenRowsetVariable|String|Cuando AccessMode es `OpenRowset from Variable`, el nombre de la variable que contiene el nombre de la tabla o vista que tiene acceso el destino de Excel.|  
|SqlCommand|String|Cuando AccessMode es `SQL Command`, la instrucción de Transact-SQL que el destino de Excel que se utiliza para especificar las columnas de destino para los datos.|  
  
 La entrada y las columnas de entrada del destino de Excel no tienen ninguna propiedad personalizada.  
  
 Para más información, consulte [Excel Destination](excel-destination.md).  
  
## <a name="see-also"></a>Vea también  
 [Common Properties](../common-properties.md)  
  
  