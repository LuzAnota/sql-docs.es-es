---
title: "Proteger elementos de or&#237;genes de datos compartidos | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "reporting-services-sharepoint"
  - "reporting-services-native"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "orígenes de datos compartidos [Reporting Services]"
  - "orígenes de datos [Reporting Services], compartidos"
  - "seguridad [Reporting Services], orígenes de datos"
ms.assetid: 7299e498-0a1a-4821-a22a-5199bb773ce0
caps.latest.revision: 35
author: "guyinacube"
ms.author: "asaxton"
manager: "erikre"
caps.handback.revision: 35
---
# Proteger elementos de or&#237;genes de datos compartidos
  Puede establecer la seguridad en un origen de datos compartido para habilitar o deshabilitar el acceso a él.  
  
 Un usuario con acceso mínimo a un origen de datos compartido (por ejemplo, el acceso concedido con el rol **Explorador**) puede ver la lista de informes que usan el elemento, siempre que el usuario también esté autorizado a ver los informes.  
  
 Un usuario con acceso adicional (como el concedido con el rol **Administrador de contenido**) puede ver y establecer propiedades para el origen de datos compartido.  
  
 Para establecer la seguridad, cree una asignación de roles que especifique la cuenta de usuario o de grupo que tiene acceso al origen de datos compartido. Los usuarios con acceso a un origen de datos compartido pueden cambiar su nombre, descripción, cadena de conexión o información de credenciales.  
  
## Tareas y acceso a elementos  
 Cuando cree asignaciones de roles, utilice un rol que tenga estas tareas para asignar los permisos apropiados a usuarios y grupos.  
  
|Seleccione esta tarea|Para conceder a los usuarios permiso para|  
|----------------------|---------------------------------|  
|Ver orígenes de datos|Ver el origen de datos compartido en la jerarquía de carpetas. Sin esta tarea, el elemento no está visible para los usuarios y no pueden saber que el origen de datos está disponible.|  
|Administrar orígenes de datos|Ver propiedades que especifican el nombre, la descripción y la información de conexión. Esta tarea también se utiliza para mostrar un origen de datos compartido en la jerarquía de carpetas. Si elige esta tarea, puede omitir la tarea "Ver orígenes de datos".|  
|Establecer la seguridad de elementos individuales|Crear y modificar asignaciones de roles que controlen el acceso al origen de datos compartido. Esta tarea debe utilizarse con las tareas "Ver orígenes de datos" o "Administrar orígenes de datos". De lo contrario, no surte efecto porque el usuario no puede seleccionar el elemento.|  
  
## Vea también  
 [Administrar orígenes de datos de informe](../../reporting-services/report-data/manage-report-data-sources.md)   
 [Proteger carpetas](../../reporting-services/security/secure-folders.md)   
 [Proteger informes y recursos](../../reporting-services/security/secure-reports-and-resources.md)   
 [Conceder permisos en un servidor de informes en modo nativo](../../reporting-services/security/granting-permissions-on-a-native-mode-report-server.md)   
 [Almacenamiento de las credenciales en un origen de datos de Reporting Services](../../reporting-services/report-data/store-credentials-in-a-reporting-services-data-source.md)  
  
  