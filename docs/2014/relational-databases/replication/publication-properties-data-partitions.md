---
title: Propiedades de la publicación, Particiones de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- sql12.rep.newpubwizard.pubproperties.datapartitions.f1
ms.assetid: 5869edb7-d05f-495b-b828-b7fd5e828d20
caps.latest.revision: 19
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: fe5c3417d20656c207bcdddea97b8cb998d5050f
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36108065"
---
# <a name="publication-properties-data-partitions"></a>Propiedades de la publicación, Particiones de datos
  La página **Particiones de datos** del cuadro de diálogo **Propiedades de la publicación** le permite definir particiones de datos para publicaciones de combinación que utilizan el filtro con parámetros. Después de definir particiones, puede generar instantáneas para estas particiones, proporcionando distintos conjuntos de datos iniciales para diferentes suscriptores sobre la base de las propiedades de conexión (inicio de sesión o nombre del equipo) de los suscriptores. También puede optar por permitir que los suscriptores soliciten la entrega y la generación de instantáneas si no tienen una instantánea disponible para su partición la primera vez que realizan la sincronización. Para más información, consulte [Crear una instantánea para una publicación de mezcla con filtros con parámetros](create-a-snapshot-for-a-merge-publication-with-parameterized-filters.md).  
  
## <a name="options"></a>Opciones  
 **Agregar**  
 Haga clic en **Agregar** para definir una partición. En el cuadro de diálogo **Agregar partición de datos** , especifique valores para **HOST_NAME()** o **SUSER_SNAME()** y defina una programación para actualizar las instantáneas.  
  
 **Editar**  
 Seleccione una partición existente en la cuadrícula y haga clic en **Editar** para editarla.  
  
 **Eliminar**  
 Seleccione una partición existente en la cuadrícula y haga clic en **Eliminar** para eliminarla.  
  
 **Generar instantáneas seleccionadas ahora**  
 Seleccione una o varias particiones en la cuadrícula y haga clic en **Generar instantáneas seleccionadas ahora** para generar instantáneas para estas particiones.  
  
 **Limpiar instantáneas existentes**  
 Seleccione una o varias particiones en la cuadrícula y haga clic en **Limpiar instantáneas existentes** para limpiar las instantáneas de estas particiones.  
  
 **Definir automáticamente una partición y generar una instantánea si es necesario cuando un suscriptor nuevo intente sincronizarse**  
 Seleccione esta opción si desea permitir que los suscriptores soliciten la generación y aplicación de instantáneas. Los suscriptores podrían solicitar esta opción si no tienen una instantánea disponible para su partición la primera vez que realizan la sincronización.  
  
## <a name="see-also"></a>Vea también  
 [Create a Publication](publish/create-a-publication.md)   
 [Ver y modificar propiedades de publicación](publish/view-and-modify-publication-properties.md)   
 [Parameterized Row Filters](merge/parameterized-filters-parameterized-row-filters.md)   
 [Publicar datos y objetos de base de datos](publish/publish-data-and-database-objects.md)   
 [Instantáneas para publicaciones de combinación con filtros con parámetros](snapshots-for-merge-publications-with-parameterized-filters.md)  
  
  