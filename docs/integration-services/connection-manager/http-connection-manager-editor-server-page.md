---
title: "Editor del administrador de conexiones HTTP (p&#225;gina Servidor) | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "integration-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.dts.designer.httpconnection.server.f1"
helpviewer_keywords: 
  - "administrador de conexiones HTTP, editor del"
ms.assetid: 774778a0-ece6-4971-b93f-b121d8fc1fc1
caps.latest.revision: 32
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 32
---
# Editor del administrador de conexiones HTTP (p&#225;gina Servidor)
  Utilice la pestaña **Servidor** del cuadro de diálogo **Editor del administrador de conexiones HTTP** para configurar el Administrador de conexiones HTTP especificando propiedades como la dirección URL y las credenciales de seguridad. Una conexión HTTP habilita a un paquete para obtener acceso a un servidor web mediante HTTP para enviar o recibir archivos. Después de configurar el Administrador de conexiones HTTP, también puede probar la conexión.  
  
> [!IMPORTANT]  
>  El administrador de conexiones HTTP solo es compatible con la autenticación anónima y la autenticación básica. No es compatible con la autenticación de Windows.  
  
 Para obtener más información acerca del administrador de conexiones HTTP, vea [HTTP Connection Manager](../../integration-services/connection-manager/http-connection-manager.md). Para obtener más información acerca de un escenario común de uso para el Administrador de conexiones HTTP, vea [Web Service Task](../../integration-services/control-flow/web-service-task.md).  
  
## Opciones  
 **Dirección URL del servidor**  
 Escriba la dirección URL del servidor.  
  
 Si piensa utilizar el botón **Descargar WSDL** de la página **General** del **Editor de la tarea Servicio web** para descargar un archivo WSDL, escriba la dirección URL del archivo WSDL. Esta dirección URL finaliza con"?wsdl".  
  
 **Utilizar credenciales**  
 Especifique si desea que el Administrador de conexiones HTTP utilice las credenciales de seguridad del usuario para la autenticación.  
  
 **Nombre de usuario.**  
 Si el Administrador de conexiones HTTP utiliza credenciales, debe especificar un nombre de usuario, una contraseña y un dominio.  
  
 **Contraseña**  
 Si el Administrador de conexiones HTTP utiliza credenciales, debe especificar un nombre de usuario, una contraseña y un dominio.  
  
 **Dominio**  
 Si el Administrador de conexiones HTTP utiliza credenciales, debe especificar un nombre de usuario, una contraseña y un dominio.  
  
 **Utilizar certificado de cliente**  
 Especifique si desea que el Administrador de conexiones HTTP utilice un certificado de cliente para la autenticación.  
  
 **Certificado**  
 Seleccione un certificado de la lista mediante el cuadro de diálogo **Seleccionar certificado**. El cuadro de texto muestra el nombre asociado con este certificado.  
  
 **Tiempo de espera (en segundos)**  
 Indique un tiempo de espera para conectar con el servidor web. El valor predeterminado de esta propiedad es 30 segundos.  
  
 **Tamaño del fragmento (en KB)**  
 Indique un tamaño de fragmento para escribir datos.  
  
 **Probar conexión**  
 Después de configurar el Administrador de conexiones HTTP, haga clic en **Probar conexión** para confirmar que la conexión es viable.  
  
## Vea también  
 [Referencia de errores y mensajes de Integration Services](../../integration-services/integration-services-error-and-message-reference.md)   
 [Editor del administrador de conexiones HTTP &#40;página Proxy&#41;](../../integration-services/connection-manager/http-connection-manager-editor-proxy-page.md)  
  
  