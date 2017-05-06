---
title: "Instalar el servidor de informes en modo nativo de Reporting Services | Microsoft Docs"
ms.custom: 
  - "SQL2016_New_Updated"
ms.date: "03/30/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "reporting-services-native"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
helpviewer_keywords: 
  - "configuración predeterminada [Reporting Services]"
  - "servidores de informes [Reporting Services], configuraciones predeterminadas"
  - "opciones de instalación [Reporting Services]"
ms.assetid: 8f25e6dc-b753-400e-9e9a-50f4f35bf6c4
caps.latest.revision: 68
author: "guyinacube"
ms.author: "asaxton"
manager: "erikre"
caps.handback.revision: 65
---
# Instalar el servidor de informes en modo nativo de Reporting Services
Aprenda a instalar [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en modo nativo. Esto le proporcionará acceso a un [!INCLUDE[ssRSWebPortal](../../includes/ssrswebportal.md)] donde puede administrar informes y otros elementos.

Un servidor de informes en modo nativo de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] es el modo de servidor de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] predeterminado y se puede instalar desde el Asistente para la instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o desde la línea de comandos. En el Asistente para la instalación, puede seleccionar instalar archivos y configurar el servidor con los valores predeterminados o instalar solo los archivos. En este tema se examina la *configuración predeterminada para el modo nativo* donde el programa de instalación instala y configura una instancia del servidor de informes. Una vez finalizada la instalación, el servidor de informes se ejecuta y está listo para usar para la visualización básica de informes y la administración de informes.  Otras características adicionales, como la integración de [!INCLUDE[sspowerbi](../../includes/sspowerbi-md.md)] y la entrega de correo electrónico con procesamiento de suscripciones, requieren una configuración adicional.  
  
||  
|-|  
|**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] |  
  
##  <a name="bkmk_whatisdefaultconfiguration"></a> ¿Qué es la configuración predeterminada?  
 El programa de instalación instala las siguientes características de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] al seleccionar la configuración predeterminada para la opción en modo nativo:  
  
-   El servicio del servidor de informes (que incluye el servicio web del servidor de informes, la aplicación de procesamiento en segundo plano y el [!INCLUDE[ssRSWebPortal-Non-Markdown](../../includes/ssrswebportal-non-markdown-md.md)] para ver y administrar informes, además de permisos).  
  
-   El Administrador de configuración de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
-   Las utilidades de línea de comandos de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] rsconfig.exe, rskeymgmt.exe y rs.exe.  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] y [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] son ahora descargas independientes.  
  
 El programa de instalación configura lo siguiente en una instalación del servidor de informes en modo nativo:  
  
-   La cuenta de servicio del servicio web del servidor de informes.  
  
-   Dirección URL del servicio web del servidor de informes.  
  
-   Dirección URL de [!INCLUDE[ssRSWebPortal-Non-Markdown](../../includes/ssrswebportal-non-markdown-md.md)].  
  
-   La base de datos del servidor de informes.  
  
-   Acceso de la cuenta del servicio a las bases de datos del servidor de informes.  
  
-   Información de conexión, también conocida como el nombre del origen de datos (DSN) para las bases de datos del servidor de informes.  
  
 El programa de instalación no configura la cuenta de ejecución desatendida, el correo electrónico del servidor de informes, la copia de seguridad de las claves de cifrado ni una implementación escalada. Puede usar el Administrador de configuración de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] para configurar estas propiedades. Para obtener más información, vea [Administrador de configuración de Reporting Services &#40;modo nativo&#41;](../../reporting-services/install-windows/reporting-services-configuration-manager-native-mode.md).
  
##  <a name="bkmk_whentoinstalldefaultconfig"></a> Cuándo instalar la configuración predeterminada en el modo nativo  
 Una configuración predeterminada instala [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en un estado operativo para que se pueda utilizar el servidor de informes inmediatamente una vez finalizada la instalación. Especifique este modo si desea ahorrar pasos eliminando las tareas de configuración necesarias que de otro modo tendría que realizar en la herramienta Configuración de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .  
  
 Instalar la configuración predeterminada no garantiza que el servidor de informes vaya a funcionar una vez finalizada la instalación. Las direcciones URL predeterminadas podrían no registrarse cuando el servicio se inicie. Siempre pruebe la instalación para comprobar que el servicio se inicia y se ejecuta como debería.  Consulte [Verify a Reporting Services Installation](../../reporting-services/install-windows/verify-a-reporting-services-installation.md).
  
##  <a name="bkmk_requirements"></a> Requisitos  
 La opción de configuración predeterminada usa los valores predeterminados con el fin de establecer la configuración básica necesaria para hacer que un servidor de informes esté operativo. Tiene los requisitos siguientes:  
  
-   Vea [Hardware and Software Requirements for Installing SQL Server 2016](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server-2016.md) .  
  
-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] y [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] se deben instalar juntos en la misma instancia. La instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)] hospeda la base de datos del servidor de informes que el programa de instalación crea y configura.  
  
-   La cuenta de usuario utilizada para ejecutar el programa de instalación debe ser miembro del grupo local de administradores y tener permiso para obtener acceso y crear las bases de datos en la instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)] que hospeda las bases de datos del servidor de informes.  
  
-   El programa de instalación debe poder usar los valores predeterminados para reservar las direcciones URL que proporcionan acceso al servidor de informes y al [!INCLUDE[ssRSWebPortal-Non-Markdown](../../includes/ssrswebportal-non-markdown-md.md)]. Estos valores son el puerto 80, un carácter comodín seguro y los nombres de directorios virtuales con el formato **ReportServer_\<***nombre_instancia***>** y **Reports_\<***nombre_instancia***>**.  
  
-   El programa de instalación debe poder utilizar los valores predeterminados para crear las bases de datos del servidor de informes. Estos valores son **ReportServer** y **ReportServerTempDB**. Si tiene bases de datos de una instalación anterior, el programa de instalación se bloqueará porque no puede configurar el servidor de informes en la configuración predeterminada del modo nativo. Debe cambiar el nombre, mover o eliminar las bases de datos para desbloquear la instalación.  
  
 Si el equipo no cumple todos los requisitos para una instalación predeterminada, debe instalar [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en el modo de solo archivos y, a continuación, usar el Administrador de configuración de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] para configurarlo una vez finalizada la instalación.
  
##  <a name="bkmk_defaultURLreservations"></a> Reservas de direcciones URL predeterminadas  
 Las reservas de direcciones URL están compuestas de un prefijo, un nombre de host, un puerto y un directorio virtual:  
  
|Parte|Descripción|  
|----------|-----------------|  
|Prefijo|El prefijo predeterminado es HTTP. Si instaló anteriormente un certificado de Capa de sockets seguros (SSL), el programa de instalación intentará crear reservas de direcciones URL que usen el prefijo HTTPS.|  
|Nombre de host|El nombre de host predeterminado es un carácter comodín (+) seguro. Especifica que el servidor de informes aceptará cualquier solicitud HTTP en el puerto designado para cualquier nombre de host que se resuelva como el equipo, incluidos http://\<nombreDePC>/reportserver, http://localhost/reportserver o http://\<DirecciónIP>/reportserver.|  
|Puerto|El puerto predeterminado es 80. Tenga en cuenta que si utiliza cualquier puerto distinto del 80, tendrá que agregarlo explícitamente a la dirección URL cuando abra una aplicación web de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en una ventana del explorador.|  
|Directorio virtual|De forma predeterminada, los directorios virtuales se crean en el formato de ReportServer_\<*instance_name*> para el servicio web del servidor de informes y Reports_\<*instance_name*> para el [!INCLUDE[ssRSWebPortal-Non-Markdown](../../includes/ssrswebportal-non-markdown-md.md)]. Para el servicio web del servidor de informes, el nombre del directorio virtual predeterminado es **reportserver**. Para el [!INCLUDE[ssRSWebPortal-Non-Markdown](../../includes/ssrswebportal-non-markdown-md.md)], el directorio virtual predeterminado es **reports**.|  
  
 Un ejemplo de cadena de dirección URL completa podría ser el siguiente:  
  
-   http://+:80/reportserver, proporciona acceso al servidor de informes.  
  
-   http://+:80/reports, proporciona acceso al [!INCLUDE[ssRSWebPortal-Non-Markdown](../../includes/ssrswebportal-non-markdown-md.md)].
  
##  <a name="bkmk_installwithwizard"></a> Instalar el modo nativo mediante el Asistente para la instalación de SQL Server  
 En la lista siguiente se describen los pasos y las opciones específicos de  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] que se seleccionan en el Asistente para la instalación de SQL Server. En la lista no se describe cada página que aparece en el asistente para la instalación, solo las páginas relacionadas con [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] que forman parte de una instalación de modo nativo.  
  
1.  Ejecute el Asistente para la instalación de SQL Server (setup.exe) y vea las siguientes páginas preliminares:  
  
    -   Clave de producto  
  
    -   Términos de licencia  
  
    -   Reglas globales  
  
    -   Microsoft Update  
  
    -   Actualizaciones del producto  
  
    -   Instalar archivos de instalación  
  
    -   Reglas de instalación  
  
2.  En la página **Rol de instalación** , seleccione **Instalación de características de SQL Server**.  
  
     ![SQL Server Feature Installation for setup role](../../reporting-services/install-windows/media/rs-setuprole.png "SQL Server Feature Installation for setup role")  
  
3.  En la página **Selección de características** , seleccione lo siguiente:  
  
    -   (1) **Servicios de Motor de base de datos**, a menos que ya esté instalada anteriormente una instancia del motor de base de datos.  
  
    -   (2) **Reporting Services: nativo**.  
  
     ![SSRS Native Mode Select in Feature Selection](../../reporting-services/install-windows/media/rs-setupfeatureselection-native-withcircles.png "SSRS Native Mode Select in Feature Selection")  
  
4.  Revise que se hayan pasado las **Reglas de características** .  
  
5.  En la página de configuración de la instancia, recuerde que, si decide configurar una **Instancia con nombre**, deberá usar el nombre de la instancia en direcciones URL cuando vaya al Administrador de informes y al propio servidor de informes. Si el nombre de la instancia era "THESQLINSTANCE", las direcciones URL tendrían el siguiente aspecto:  
  
    -   `http://[ServerName]/ReportServer_THESQLINSTANCE`  
  
    -   `http://[ServerName]/Reports_THESQLINSTANCE`  
  
6.  **Configuración del servidor**: si piensa usar la característica de suscripción [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , en la página **Configuración del servidor** , configure el Agente SQL Server en el tipo de inicio **Automático** .   El valor predeterminado es manual.  
  
7.  Agregue los administradores de SQL Server en la página **Configuración del motor de base de datos** .  
  
8.  En la página **Configuración de Reporting Services** , seleccione **Instalar y configurar**.  
  
     ![SSRS Native Mode Configuration](../../reporting-services/install-windows/media/rs-setupconfiguration-native-with-circles.png "SSRS Native Mode Configuration")  
  
    > [!NOTE]  
    >  **Instalar y configurar** no estará disponible a menos que la característica de base de datos también se seleccione para instalarse.  
  
9. Reglas de configuración de la característica: compruebe que se han superado las reglas. El asistente para la instalación avanza automáticamente a **Preparado para instalar** si se superan todas las reglas.  En concreto en [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], las reglas comprueban que no existan ya un catálogo del servidor de informes ni una base de datos del catálogo temporal.  
  
10. ![nota](../../analysis-services/instances/install-windows/media/ssrs-fyi-note.png "nota")En la página **Preparado para instalar**, anote la ruta de acceso al archivo de configuración, ya que puede consultarlo más adelante para obtener un buen resumen de la configuración inicial de los servidores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], incluidos los componentes instalados, las cuentas de servicio y los administradores.  
  
11. Una vez completado el asistente para la instalación de SQL Server, compruebe la instalación de modo nativo predeterminada con los siguientes pasos básicos.  
  
    -   Abra el Administrador de configuración de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] y confirme que se puede conectar con el servidor de informes.  
  
    -   Abra el explorador **con privilegios de administrador** y conéctese al [!INCLUDE[ssRSWebPortal-Non-Markdown](../../includes/ssrswebportal-non-markdown-md.md)], por ejemplo `http://localhost/Reports`.  
  
    -   Abra el explorador con privilegios de administrador y conéctese a la página del servidor de informes de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]. Por ejemplo,  `http://localhost/ReportServer`  
  
 Para obtener más información, consulte la sección Nativo de los dos temas siguientes:  
  
 [Comprobar una instalación de Reporting Services](../../reporting-services/install-windows/verify-a-reporting-services-installation.md)  
  
 [Solucionar problemas en una instalación de Reporting Services](../../reporting-services/install-windows/troubleshoot-a-reporting-services-installation.md)   
  
##  <a name="bkmk_additional_configuration"></a> Configuración adicional  
  
-   Para configurar la integración de [!INCLUDE[sspowerbi](../../includes/sspowerbi-md.md)], de modo que pueda anclar elementos de informe a un panel de [!INCLUDE[sspowerbi](../../includes/sspowerbi-md.md)], vea [Integración del servidor de informes de Power BI &#40;Administrador de configuración&#41;](../../reporting-services/install-windows/power-bi-report-server-integration-configuration-manager.md).  
  
-   Para configurar el correo electrónico para el procesamiento de suscripciones, vea [Configuración de correo electrónico: Modo nativo de Reporting Services &#40;Administrador de configuración&#41;](../../reporting-services/install-windows/e-mail-settings-reporting-services-native-mode-configuration-manager.md) y [Entrega por correo electrónico en Reporting Services](../../reporting-services/subscriptions/e-mail-delivery-in-reporting-services.md).  
  
-   Para configurar el [!INCLUDE[ssRSWebPortal-Non-Markdown](../../includes/ssrswebportal-non-markdown-md.md)] para que pueda obtener acceso a él en un equipo para ver y administrar informes, vea [Configurar un firewall para el acceso al servidor de informes](../../reporting-services/report-server/configure-a-firewall-for-report-server-access.md) y [Configurar un servidor de informes para la administración remota](../../reporting-services/report-server/configure-a-report-server-for-remote-administration.md).  
  
## Vea también  
 [Solucionar problemas en una instalación de Reporting Services](../../reporting-services/install-windows/troubleshoot-a-reporting-services-installation.md)   
 [Comprobar una instalación de Reporting Services](../../reporting-services/install-windows/verify-a-reporting-services-installation.md)   
 [Configurar la cuenta de servicio del servidor de informes &#40;Administrador de configuración de SSRS&#41;](../../reporting-services/install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md)   
 [Configurar las direcciones URL del servidor de informes &#40;Administrador de configuración de SSRS&#41;](../../reporting-services/install-windows/configure-report-server-urls-ssrs-configuration-manager.md)   
 [Configurar una conexión a la base de datos del servidor de informes &#40;Administrador de configuración de SSRS&#41;](../../reporting-services/install-windows/configure-a-report-server-database-connection-ssrs-configuration-manager.md)   
 [Instalación de solo archivos &#40;Reporting Services&#41;](../../reporting-services/install-windows/files-only-installation-reporting-services.md)   
 [Inicializar un servidor de informes &#40;Administrador de configuración de SSRS&#41;](../../reporting-services/install-windows/initialize-a-report-server-ssrs-configuration-manager.md)   
 [Configurar conexiones SSL en un servidor de informes en modo nativo](../../reporting-services/security/configure-ssl-connections-on-a-native-mode-report-server.md)   
 [Configurar los permisos y las cuentas de servicio de Windows](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md)   
 [Quick-Start Installation of SQL Server 2016 (Instalación de SQL Server 2016)](../Topic/Quick-Start%20Installation%20of%20SQL%20Server%202016.md)  
  
  