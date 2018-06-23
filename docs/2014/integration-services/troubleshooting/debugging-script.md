---
title: Depurar script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Script task [Integration Services], debugging
- debugging [Integration Services], scripts
- scripts [Integration Services], debugging
ms.assetid: fddf57d8-8607-4f88-85a0-1b683087b491
caps.latest.revision: 56
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: 55e6df8e55d0805f6ac33accc427ed7734d4eb97
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36105886"
---
# <a name="debugging-script"></a>Depurar script
  Escribe los scripts que la tarea Script y el componente Script usan, en [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools para aplicaciones (VSTA).  
  
 EN VSTA se establecen y programan los puntos de interrupción. Puede administrar los puntos de interrupción en VSTA, pero también puede administrar los puntos de interrupción mediante el cuadro de diálogo **Establecer puntos de interrupción** que proporciona el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] . Para más información, consulte [Debugging Control Flow](debugging-control-flow.md).  
  
 El cuadro de diálogo **Establecer puntos de interrupción** incluye los puntos de interrupción del script. Estos puntos de interrupción aparecen en la parte inferior de la lista de puntos de interrupción, y muestran el número de línea y el nombre de la función en que aparece el punto de interrupción. Es posible eliminar un punto de interrupción de script en el cuadro de diálogo **Establecer puntos de interrupción** .  
  
 En tiempo de ejecución, los puntos de interrupción establecidos en líneas de código del script se integran con los puntos de interrupción establecidos en el paquete o las tareas y contenedores del paquete. El depurador puede ejecutarse desde un punto de interrupción en el script hasta un conjunto de puntos de interrupción en el paquete, tarea o contenedor, y viceversa. Por ejemplo, un paquete puede tener puntos de interrupción establecidos en las condiciones de interrupción que se producen cuando el paquete recibe los eventos **OnPreExecute** y **OnPostExecute** y también puede tener una tarea Script que tiene puntos de interrupción en líneas de su script. En este escenario, el paquete puede suspender la ejecución en la condición de interrupción asociada al evento **OnPreExecute** , ejecutar los puntos de interrupción en el script y finalmente ejecutarse en la condición de interrupción asociada con el evento **OnPostExecute** .  
  
 Para obtener más información acerca de cómo depurar la tarea Script y el componente Script, vea [Coding and Debugging the Script Task](../extending-packages-scripting/task/coding-and-debugging-the-script-task.md) y [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).  
  
### <a name="to-set-a-breakpoint-in-visual-studio-for-applications"></a>Para establecer un punto de interrupción en Visual Studio para Aplicaciones  
  
-   [Depurar un script mediante el establecimiento de puntos de interrupción en una tarea Script y un componente de script](../extending-packages-scripting/debug-a-script-by-setting-breakpoints-in-a-script-task-and-script-component.md)  
  
## <a name="see-also"></a>Vea también  
 [Herramientas para solucionar problemas del desarrollo de paquetes](troubleshooting-tools-for-package-development.md)  
  
  