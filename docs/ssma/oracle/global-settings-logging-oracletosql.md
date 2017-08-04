---
title: "Configuración global (registro) (OracleToSQL) | Documentos de Microsoft"
ms.prod: sql-non-specified
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- sql-ssma
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 12dbcd77-2b90-4fa1-9cf9-239231ea5773
caps.latest.revision: 4
author: sabotta
ms.author: carlasab
manager: v-thobro
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: df359be112e86522d35e27d8cf49a4515d8745d6
ms.contentlocale: es-es
ms.lasthandoff: 08/02/2017

---
# <a name="global-settings-logging-oracletosql"></a>Configuración global (registro) (OracleToSQL)
Use la **configuración Global** cuadro de diálogo para especificar la configuración del registro para SSMA. Por lo general, debería cambiar esta configuración solo cuando se trabaja con servicios de soporte técnico.  
  
Para tener acceso a este cuadro de diálogo, en la **herramientas** menú, seleccione **configuración Global** y, a continuación, haga clic en el **registro** situado en la parte inferior del panel izquierdo.  
  
## <a name="options"></a>Opciones  
**Nivel de mensajes**  
Las siguientes opciones están disponibles en **nivel de mensajes**:  
  
|Opción|Description|  
|----------|---------------|  
|**[todas las categorías]**|Se usa para establecer el nivel de registro para todas las opciones siguientes.|  
|**Recopilador**|Recopila los metadatos sobre el esquema de origen y lo guarda en el proyecto.|  
|**Convertidor**|Convierte las estructuras de los objetos de base de datos de origen, como tablas y procedimientos almacenados, en correspondiente [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] estructuras.|  
|**Migrador de datos**|Migra los datos de la base de datos de origen en [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)].|  
|**Formateador**|Subcomponente del convertidor que genera scripts para el [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] esquema.|  
|**Interfaz gráfica de usuario**|Mensajes que aparecen cuando se utiliza la herramienta SSMA.|  
|**Vinculador**|Resuelve los identificadores de SQL y se proporciona información a otros componentes.|  
|**Otro**|Todos los mensajes que no están en cualquier otra categoría.|  
|**Analizador**|Analiza el esquema de origen.|  
|**Sincronizador**|Carga del origen de objetos de base de datos en [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)].|  
|**TreeConverter**|Convierte los objetos en los metadatos de origen en [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] metadatos.|  
|**Herramienta de comprobación**|Mensajes que aparecen cuando se usa la herramienta de comprobación de SSMA.|  
  
Para cada opción en **nivel de mensajes**, configure uno de los siguientes niveles de registro para SSMA:  
  
|||  
|-|-|  
|**Error irrecuperable**|Escribir solo mensajes de error grave en el registro.|  
|**Error**|Escribir los errores y mensajes de error grave en el registro.|  
|**Advertencia**|Escribir mensajes de error grave, error y de advertencia en el registro.|  
|**Información de**|Escribir informativos, advertencias, errores y mensajes de error grave en el registro.|  
|**Depuración**|Escribir todos los mensajes, incluidos los mensajes, en el registro de depuración.|  
  
**Ruta de acceso de archivo de registro**  
La ruta de acceso de archivo y el nombre de los archivos de registro SSMA. Para especificar un nombre diferente, haga clic en la ruta de acceso actual y, a continuación, haga clic en el botón Examinar (**...** ) botón.  
  
**Tamaño de archivo de registro**  
El tamaño máximo del archivo de registro en KB. El tamaño mínimo es de 10 KB. El tamaño predeterminado es 10240 KB.  
  
**Número total de archivos de registro**  
Cuando se llena un registro, SSMA se cambie el nombre del archivo de registro e iniciar uno nuevo. Con esta configuración, especifique el número máximo de archivos de registro que se va a mantener. El valor mínimo es 2.  
  
