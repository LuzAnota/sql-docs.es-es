---
title: "Opciones de Solicitud de perfil de proporci&#243;n de columnas nulas (tarea de generaci&#243;n de perfiles de datos) | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "integration-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Editor de tareas de generación de perfiles de datos"
ms.assetid: 157ef8e4-fd23-4f81-8194-eebf74e9fd86
caps.latest.revision: 19
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 19
---
# Opciones de Solicitud de perfil de proporci&#243;n de columnas nulas (tarea de generaci&#243;n de perfiles de datos)
  Utilice el panel **Propiedades de la solicitud** de la página **Solicitudes de perfil** para establecer las opciones de **Solicitud de perfil de proporción de columnas nulas** seleccionadas en el panel de solicitudes. Un perfil de proporción de columnas nulas indica el porcentaje de valores nulos de la columna seleccionada. Este perfil puede ayudarle a identificar problemas en los datos, por ejemplo una proporción inesperadamente alta de valores nulos en una columna. Por ejemplo, un perfil de proporción de columnas nulas puede generar un perfil de una columna de códigos postales y detectar que falta un porcentaje inaceptablemente alto de códigos postales.  
  
> [!NOTE]  
>  Las opciones que se describen en este tema aparecen en la página **Solicitudes de perfil** del **Editor de tareas de generación de perfiles de datos**. Para obtener más información sobre esta página del editor, vea [Editor de tareas de generación de perfiles de datos &#40;página Solicitudes de perfil&#41;](../../integration-services/control-flow/data-profiling-task-editor-profile-requests-page.md).  
  
 Para obtener más información sobre cómo usar la tarea de generación de perfiles de datos, vea [Configuración de la Tarea de generación de perfiles de datos](../../integration-services/control-flow/setup-of-the-data-profiling-task.md). Para obtener más información sobre cómo usar el Visor de perfil de datos para analizar la salida de la tarea de generación de perfiles de datos, vea [Visor de perfil de datos](../../integration-services/control-flow/data-profile-viewer.md).  
  
## Opciones de Propiedades de la solicitud  
 Para cada **Solicitud de perfil de proporción de columnas nulas**, el panel **Propiedades de la solicitud** muestra los grupos de opciones siguientes:  
  
-   **Data**, que incluye las opciones **TableOrView** y **Column**  
  
-   **General**  
  
### Opciones de Data  
 **ConnectionManager**  
 Seleccione el administrador de conexiones de [!INCLUDE[vstecado](../../includes/vstecado-md.md)] existente que usa el proveedor de datos .NET para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) con el fin de conectarse a la base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que contiene la tabla o la vista con la que se va a generar el perfil.  
  
 **TableOrView**  
 Seleccione la tabla o vista existente que contenga la columna de la que se va a generar un perfil.  
  
 Para obtener más información, vea la sección "Opciones de TableorView" en este tema.  
  
 **Columna**  
 Seleccione la columna existente de la que se va a generar un perfil. Seleccione **(\*)** para generar un perfil de todas las columnas.  
  
 Para obtener más información, vea la sección "Opciones de Column" en este tema.  
  
#### Opciones de TableOrView  
 **Esquema**  
 Especifica el esquema al que pertenece la tabla seleccionada. Esta opción es de solo lectura.  
  
 **Table**  
 Muestra el nombre de la tabla seleccionada. Esta opción es de solo lectura.  
  
#### Opciones de Column  
 **IsWildCard**  
 Especifica si se ha seleccionado el carácter comodín **(\*)**. Esta opción está establecida en **True** si ha seleccionado **(\*)** para generar un perfil de todas las columnas. Es **False** si ha seleccionado una columna individual para la que generar un perfil. Esta opción es de solo lectura.  
  
 **ColumnName**  
 Muestra el nombre de la columna seleccionada. Esta opción está en blanco si ha seleccionado **(\*)** para generar un perfil de todas las columnas. Esta opción es de solo lectura.  
  
 **StringCompareOptions**  
 Esta opción no se aplica al Perfil de proporción de columnas nulas.  
  
### Opciones de General  
 **IdSolicitud**  
 Escriba un nombre descriptivo para identificar esta solicitud de perfil. Generalmente, no tiene que cambiar el valor generado automáticamente.  
  
## Vea también  
 [Editor de tareas de generación de perfiles de datos &#40;página General&#41;](../../integration-services/control-flow/data-profiling-task-editor-general-page.md)   
 [Formulario de perfil rápido de tabla única &#40;tarea de generación de perfiles de datos&#41;](../../integration-services/control-flow/single-table-quick-profile-form-data-profiling-task.md)  
  
  