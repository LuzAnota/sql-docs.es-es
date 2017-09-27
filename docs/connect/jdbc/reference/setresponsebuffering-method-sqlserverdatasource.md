---
title: "Método setResponseBuffering (SQLServerDataSource) | Documentos de Microsoft"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- SQLServerDataSource.setResponseBuffering(String responseBufferingValue)
apilocation:
- SQLServerDataSource.setResponseBuffering(String responseBufferingValue)
apitype: Assembly
ms.assetid: c9e43ff2-8117-4dca-982d-83c863d0c8e1
caps.latest.revision: 27
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 88cfa89a30461ba3013c7b227651d5d0292c77b2
ms.contentlocale: es-es
ms.lasthandoff: 09/09/2017

---
# <a name="setresponsebuffering-method-sqlserverdatasource"></a>Método setResponseBuffering (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Establece la respuesta para las conexiones creadas utilizando el modo de almacenamiento en búfer [SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md) objeto.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
public void setResponseBuffering(java.lang.String value)  
```  
  
#### <a name="parameters"></a>Parámetros  
 *value*  
  
 A **cadena** que contiene el modo de transmisión por secuencias y almacenamiento en búfer. El modo válido puede ser una de las siguientes cadenas entre mayúsculas y minúsculas: **completa** o **adaptable**.  
  
## <a name="remarks"></a>Comentarios  
 El **completa** valor especifica leer el resultado completo desde el servidor en tiempo de ejecución.  
  
 El **adaptable** valor especifica el almacenamiento en búfer los datos mínimos posibles cuando sea necesario. El **adaptable** el valor predeterminado es el modo de almacenamiento en búfer.  
  
 Para obtener más información acerca de cómo utilizar el modo de almacenamiento en búfer de respuesta, consulte [usar almacenamiento en búfer adaptable](../../../connect/jdbc/using-adaptive-buffering.md).  
  
## <a name="see-also"></a>Vea también  
 [Miembros SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [Clase SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  