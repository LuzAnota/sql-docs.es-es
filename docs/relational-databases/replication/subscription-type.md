---
title: "Tipo de suscripción | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.rep.newsubwizard.subscriptiontype.f1
ms.assetid: 9a50f588-ee45-4a87-826f-372ff0798587
caps.latest.revision: 20
author: BYHAM
ms.author: rickbyh
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 0541842347278d70b5d759737bf0c37b1f91bfab
ms.lasthandoff: 04/11/2017

---
# <a name="subscription-type"></a>Tipo de suscripción
  La replicación de mezcla proporciona dos tipos de suscripción: servidor y cliente (denominadas en versiones anteriores de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] global y local, respectivamente). Los suscriptores con una suscripción de servidor pueden:  
  
-   Volver a publicar datos en otros suscriptores.  
  
-   Servir como asociados de sincronización alternativos.  
  
-   Solucionador de conflictos en función de la prioridad establecida.  
  
 La mayoría de los suscriptores no necesitan esta funcionalidad y pueden usar la suscripción de cliente. Las suscripciones de cliente todavía permiten la detección y resolución de conflictos, pero los suscriptores no tienen asignada una prioridad: el primer suscriptor que envía un cambio al publicador gana cualquier conflicto que pueda surgir de ese cambio.  
  
> [!NOTE]  
>  El tipo de suscripción no se puede cambiar una vez creada la suscripción.  
  
## <a name="options"></a>Opciones  
 **Propiedades de la suscripción**  
 Para cada suscriptor, seleccione **Cliente** o **Servidor** en el cuadro de lista desplegable de la columna **Tipo de suscripción** . Para los suscriptores con suscripciones de servidor, escriba un número entre 0 y 99,99 en la columna **Prioridad para la resolución de conflictos** (cuanto mayor sea el número, más alta será la prioridad del suscriptor).  
  
## <a name="see-also"></a>Vea también  
 [Crear una suscripción de extracción](../../relational-databases/replication/create-a-pull-subscription.md)   
 [Create a Push Subscription](../../relational-databases/replication/create-a-push-subscription.md)   
 [Suscribirse a publicaciones](../../relational-databases/replication/subscribe-to-publications.md)  
  
  