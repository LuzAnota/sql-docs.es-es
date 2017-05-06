---
title: "Modificar una alerta de datos en el Dise&#241;ador de alertas | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "reporting-services-sharepoint"
  - "reporting-services-native"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "editar, alertas de datos"
  - "actualizar, alertas de datos"
  - "editar, alertas"
  - "actualizar, alertas"
ms.assetid: dde3664d-90b5-4b12-969e-39152c86e58a
caps.latest.revision: 11
author: "guyinacube"
ms.author: "asaxton"
manager: "erikre"
caps.handback.revision: 11
---
# Modificar una alerta de datos en el Dise&#241;ador de alertas
  La definición de alerta de datos que desea editar se abre en el Administrador de alertas de datos. Solo el usuario que creó la definición de la alerta puede modificarla. Para más información sobre cómo abrir el Administrador de alertas de datos, vea [Administrar mis alertas de datos en el Administrador de alertas de datos](../reporting-services/manage-my-data-alerts-in-data-alert-manager.md).  
  
 En la imagen siguiente se muestra el menú contextual de una alerta de datos en el Administrador de alertas de datos.  
  
 ![Abrir el Diseñador de alertas de datos haciendo clic en Editar](../reporting-services/media/rs-alertmanageriwopendesigner.gif "Abrir el Diseñador de alertas de datos haciendo clic en Editar")  
  
 El procedimiento siguiente incluye los pasos para abrir la definición de alerta con objeto de modificarla en el Diseñador de alertas de datos desde el Administrador de alertas de datos.  
  
### Para editar una definición de alerta de datos en el Diseñador de alertas de datos  
  
1.  En el Administrador de alertas de datos, haga clic con el botón derecho en la definición de alerta de datos que quiere editar y haga clic en **Editar**.  
  
     La definición de alerta se abre en el Diseñador de alertas de datos.  
  
2.  Actualice las reglas, la configuración de la programación y la de los mensajes de correo electrónico. Para más información, vea [Diseñador de alertas de datos](../reporting-services/data-alert-designer.md) y [Crear una alerta de datos en el Diseñador de alertas de datos](../reporting-services/create-a-data-alert-in-data-alert-designer.md).  
  
    > [!NOTE]  
    >  No puede elegir una fuente de distribución de datos diferente. Para utilizar otra fuente de distribución de datos, debe crear una nueva definición de alerta de datos.  
  
3.  Haga clic en **Guardar**.  
  
    > [!NOTE]  
    >  Si el informe ha cambiado y las fuentes de distribución de datos generadas desde el informe han cambiado, la definición de la alerta podría no ser válida. Esto ocurre cuando una columna a la que la definición de alerta hace referencia en sus reglas se elimina del informe, cuando cambia el tipo de datos o cuando se elimina o mueve el informe. Puede abrir una definición de alerta que no sea válida, pero no puede volver a guardarla hasta que sea válida con arreglo a la versión actual de la fuente de distribución de datos del informe en la que se basa. Para más información sobre cómo se generan las fuentes de datos de informes, vea [Generar fuentes de distribución de datos a partir de informes &#40;Generador de informes y SSRS&#41;](../reporting-services/report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).  
  
## Vea también  
 [Administrador de alertas de datos para administradores de alertas](../reporting-services/data-alert-manager-for-alerting-administrators.md)   
 [Alertas de datos de Reporting Services](../reporting-services/reporting-services-data-alerts.md)  
  
  