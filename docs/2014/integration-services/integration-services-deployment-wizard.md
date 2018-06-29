---
title: Asistente para la implementación de Integration Services | Documentos de Microsoft
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- sql12.ssis.deploymentwizard.f1
ms.assetid: f3d93e13-2d85-47ff-a913-cda4046491c4
caps.latest.revision: 10
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: 60bc9f05f7a00075efbda2972cf78d9d169c55d0
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36104289"
---
# <a name="integration-services-deployment-wizard"></a>Asistente para implementación de Integration Services
  El Asistente para la implementación de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] implementa proyectos en el catálogo de SSISDB en una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] mediante el modelo de implementación de proyectos.  
  
 Para iniciar el [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Asistente para la implementación de un proyecto abierto en [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], seleccione **implementar** desde el **proyecto** menú. Para iniciar el asistente [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], expanda la **catálogos de Integration Services** > **SSISDB** nodo en el Explorador de objetos, haga clic en el **proyectos** carpeta y, a continuación, haga clic en **implementar proyecto**.  
  
 El asistente continua con los siguientes cuatro pasos. Haga clic en **siguiente** para continuar con el paso siguiente, o **anterior** para volver al paso anterior.  
  
1.  **Seleccionar origen** : seleccione el [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] proyecto que va a implementar.  
  
2.  **Seleccionar destino** : seleccione el destino del proyecto.  
  
3.  **Revisión** – mostrará sus selecciones.  
  
4.  **Implementar/resultados** : implementa el proyecto y muestra los resultados.  
  
## <a name="select-source"></a>Seleccionar origen  
 Para implementar un archivo de implementación del proyecto que creó, seleccione **archivo de proyecto de implementación** y escriba la ruta de acceso del archivo .ispac o haga clic en **examinar** para encontrarlo en la [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] carpeta del proyecto. Para implementar un proyecto que resida en el catálogo de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , seleccione **Catálogo de Integration Services**y especifique el nombre del servidor y la ruta de acceso al proyecto en el catálogo.  
  
 Si inicia el asistente en [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], posteriormente, de forma predeterminada el asistente selecciona el proyecto abierto como origen y omite este paso. Para volver a este paso y seleccionar un origen diferente, haga clic en **anterior** o haga clic en **Seleccionar origen** en el panel izquierdo.  
  
## <a name="select-destination"></a>Seleccionar destino  
 Para seleccionar la carpeta de destino para el proyecto en el catálogo [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , escriba la instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] o haga clic en **Examinar** para seleccionarla en una lista de servidores. Escriba la ruta de acceso del proyecto en SSISDB o haga clic en **Examinar** para seleccionarla.  
  
 Si inicia el asistente en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], de forma predeterminada, el asistente selecciona la instancia de servidor conectado y especifica la ruta de acceso para el proyecto seleccionado. Puede cambiar estos valores para implementar el proyecto en una ubicación diferente.  
  
## <a name="review"></a>Revisar  
 El asistente le permite revisar los valores de configuración que ha seleccionado antes de implementar el proyecto. Puede cambiar las selecciones si hace clic en **Anterior**o si hace clic en cualquiera de los pasos del panel izquierdo.  
  
## <a name="deployresults"></a>Implementar/Resultados  
 Al hacer clic en **implementar** desde el **revisión** , el proyecto se implementa la clase y el **resultados** página muestra el éxito o fracaso de cada acción. Si la acción no se realiza correctamente, haga clic en **Error** en la columna **Resultado** para que aparezca una explicación del error. Haga clic en **Guardar informe...**  para guardar los resultados en un archivo XML.  
  
 Haga clic en **Cerrar** para salir del asistente.  
  
## <a name="see-also"></a>Vea también  
 [Implementar proyectos en el servidor de Integration Services](../../2014/integration-services/deploy-projects-to-integration-services-server.md)   
 [Implementación de proyectos y paquetes](packages/deploy-integration-services-ssis-projects-and-packages.md)  
  
  