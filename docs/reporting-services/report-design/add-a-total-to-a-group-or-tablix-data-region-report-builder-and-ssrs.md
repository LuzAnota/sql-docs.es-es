---
title: "Agregar un total a un grupo o a una regi&#243;n de datos Tablix (Generador de informes y SSRS) | Microsoft Docs"
ms.custom: ""
ms.date: "03/07/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "reporting-services-sharepoint"
  - "reporting-services-native"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cf1b96c3-7f0f-4c94-ad08-5239c77ccfe4
caps.latest.revision: 8
author: "maggiesMSFT"
ms.author: "maggies"
manager: "erikre"
caps.handback.revision: 8
---
# Agregar un total a un grupo o a una regi&#243;n de datos Tablix (Generador de informes y SSRS)
 En un informe paginado de [!INCLUDE[ssRSnoversion_md](../../includes/ssrsnoversion-md.md)], puede agregar totales en una región de datos Tablix solo para un grupo o para toda la región de datos. De forma predeterminada, un total es la suma de los datos numéricos no NULL de un grupo o de la región de datos, una vez aplicados los filtros. Para agregar totales a un grupo, haga clic en **Agregar total** en el menú contextual del grupo en el panel Agrupación. Para agregar totales a una celda individual en el área del cuerpo Tablix, haga clic en **Agregar total** en el menú contextual de la celda. El comando **Agregar total** es contextual y solo está habilitado para los campos numéricos. En función de la celda de Tablix seleccionada, puede agregar un total para una única celda, seleccionando una celda en el área del cuerpo de Tablix, o para el grupo completo, seleccionando una celda en el área del grupo de filas o del grupo de columnas de Tablix. Para obtener más información sobre las áreas de Tablix, vea [Región de datos Tablix &#40;Generador de informes y SSRS&#41;](../../reporting-services/report-design/tablix-data-region-report-builder-and-ssrs.md).  
  
 Después de agregar un total, puede cambiar la función Sum predeterminada por una función de agregado diferente de la lista de funciones de informe integradas. Para obtener más información, vea [Referencia a las funciones de agregado &#40;Generador de informes y SSRS&#41;](../../reporting-services/report-design/aggregate-functions-reference-report-builder-and-ssrs.md).[!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## Para agregar un total a un valor individual en el área del cuerpo de Tablix  
  
-   En el área del cuerpo de la región de datos Tablix, haga clic con el botón secundario en la celda donde desea agregar el total. La celda debe contener un campo numérico. Seleccione **Agregar total**y, a continuación, haga clic en **Fila** o **Columna**.  
  
     Se agrega a la región de datos una nueva fila o columna fuera del grupo actual, con un total predeterminado para el campo de la celda en la que hizo clic.  
  
     Si la región de datos Tablix es una tabla, automáticamente se agrega una fila.  
  
## Para agregar totales a un grupo de filas  
  
-   En el área de grupo de filas de la región de datos Tablix, haga clic con el botón derecho en una celda del área de grupo de filas cuyos totales quiere calcular, seleccione **Agregar total** y, luego, haga clic en **Antes** o **Después**.  
  
     Se agrega a la región de datos una nueva fila fuera del grupo actual y, a continuación, se agrega un total predeterminado para cada campo numérico de la fila.  
  
## Para agregar totales a un grupo de columnas  
  
-   En el área de grupo de filas de la región de datos Tablix, haga clic con el botón derecho en la celda del área de grupo de columnas cuyos totales quiere calcular, seleccione **Agregar total** y, luego, haga clic en **Antes** o **Después**.  
  
     Se agrega a la región de datos una nueva columna fuera del grupo actual y, a continuación, se agrega un total predeterminado para cada campo numérico de la columna.  
  
## Vea también  
 [Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;](../../reporting-services/report-design/expression scope for totals, aggregates, and built-in collections.md)   
 [Región de datos Tablix &#40;Generador de informes y SSRS&#41;](../../reporting-services/report-design/tablix-data-region-report-builder-and-ssrs.md)   
 [Tablas, matrices y listas &#40;Generador de informes y SSRS&#41;](../../reporting-services/report-design/tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  