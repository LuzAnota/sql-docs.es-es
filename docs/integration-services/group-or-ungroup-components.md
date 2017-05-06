---
title: "Agrupar o desagrupar componentes | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "integration-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "agrupar contenedores"
  - "tareas [Integration Services], agrupación"
  - "contenedores [Integration Services], agrupación"
  - "agrupar tareas"
ms.assetid: 34320838-c271-4f8c-90b3-1254690890bb
caps.latest.revision: 46
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 46
---
# Agrupar o desagrupar componentes
  Las pestañas **Flujo de control**, **Flujo de datos**y **Controladores de eventos** del Diseñador de [!INCLUDE[ssIS](../includes/ssis-md.md)] admiten la agrupación contraíble. Si un paquete tiene muchos componentes, las pestañas pueden estar abarrotadas, lo que dificulta la visión de todos los componentes a la vez y la búsqueda del elemento con el que desea trabajar. La característica de agrupación contraíble puede ahorrar espacio en la superficie de trabajo y facilitar el trabajo con paquetes grandes.  
  
 Se seleccionan los componentes que desea agrupar, los agrupa y luego expande o contrae los grupos para facilitar su trabajo. Al expandir un grupo se proporciona acceso a las propiedades de los componentes del grupo. Las restricciones de precedencia que conectan las tareas y contenedores se incluyen automáticamente en el grupo.  
  
 A continuación se presentan las consideraciones para la agrupación de componentes.  
  
-   Para agrupar componentes, el flujo de control, el flujo de datos o el controlador de eventos deben contener más de un componente.  
  
-   Los grupos también pueden anidarse, permitiendo la creación de grupos dentro de grupos. La superficie de diseño puede implementar varios grupos no anidados, pero un componente solamente puede pertenecer a un grupo, a menos que los grupos estén anidados.  
  
-   Cuando se guarda un paquete, el Diseñador de [!INCLUDE[ssIS](../includes/ssis-md.md)] guarda la agrupación, pero la agrupación no tiene ningún efecto sobre la ejecución de paquetes. La capacidad para agrupar componentes es una característica de tiempo de diseño que no afecta al comportamiento de tiempo de ejecución del paquete.  
  
### Para agrupar componentes  
  
1.  En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que desea.  
  
2.  En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.  
  
3.  Haga clic en la pestaña **Flujo de control**, **Flujo de datos**o **Controladores de eventos** .  
  
4.  En la superficie de diseño de la pestaña, seleccione los componentes que quiera agrupar, haga clic con el botón derecho en un componente que haya seleccionado y, después, haga clic en **Agrupar**.  
  
5.  Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados** , en el menú **Archivo** .  
  
### Para desagrupar componentes  
  
1.  En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que desea.  
  
2.  En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.  
  
3.  Haga clic en la pestaña **Flujo de control**, **Flujo de datos**o **Controladores de eventos** .  
  
4.  En la superficie de diseño de la pestaña, seleccione el grupo que contenga el componente que quiera desagrupar, haga clic con el botón derecho y, después, haga clic en **Desagrupar**.  
  
5.  Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados** , en el menú **Archivo** .  
  
## Vea también  
 [Agregar o eliminar tareas o contenedores en un flujo de control](../integration-services/control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)   
 [Conectar tareas y contenedores mediante una restricción de precedencia predeterminada](../Topic/Connect%20Tasks%20and%20Containers%20by%20Using%20a%20Default%20Precedence%20Constraint.md)  
  
  