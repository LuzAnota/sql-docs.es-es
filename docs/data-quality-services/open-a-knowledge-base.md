---
title: "Abrir una base de conocimiento | Microsoft Docs"
ms.custom: ""
ms.date: "06/04/2013"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "data-quality-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.dqs.kb.openkb.f1"
ms.assetid: a5f010a5-b762-41c9-881b-bf0c192dca83
caps.latest.revision: 20
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 20
---
# Abrir una base de conocimiento
  En este tema se describe cómo abrir una base de conocimiento existente en [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) y cómo prepararla para la administración de dominios, la detección de conocimiento o la adición de una directiva de coincidencia.  
  
##  <a name="BeforeYouBegin"></a> Antes de comenzar  
  
###  <a name="Prerequisites"></a> Requisitos previos  
 Para abrir una base de conocimiento, previamente esta debe haberse creado y estar publicada (si la ha creado otra persona) o cerrada (si la ha creado usted).  
  
###  <a name="Security"></a> Seguridad  
  
####  <a name="Permissions"></a> Permisos  
 Para abrir una base de conocimiento, debe disponer del rol dqs_kb_editor o dqs_administrator en la base de datos DQS_MAIN.  
  
##  <a name="Open"></a> Abrir una base de conocimiento  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)] [Ejecute la aplicación de cliente de calidad de datos](../data-quality-services/run-the-data-quality-client-application.md).  
  
2.  En la página de inicio de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , haga clic en **Abrir base de conocimiento**.  
  
3.  Seleccione una base de conocimiento en la tabla. Los dominios y las reglas de coincidencia de la base de conocimiento se mostrarán en el panel derecho de la página.  
  
    > [!NOTE]  
    >  Para realizar operaciones en una base de conocimiento, haga clic en ella con el botón secundario dentro de la tabla. Puede abrir la base de conocimiento, guardarla con otro nombre, desbloquearla, descartar los cambios realizados, cambiar su nombre o mostrar sus propiedades.  
  
4.  En **Seleccione la actividad**, seleccione la actividad que desea realizar en la base de conocimiento:  
  
    -   Seleccione **Administración de dominios** para tener acceso a las pantallas que se utilizan para modificar los dominios de la base de conocimiento.  
  
    -   Seleccione **Detección de conocimiento** para iniciar el asistente que se usa para analizar una muestra de datos y rellenar los dominios de la base de conocimiento con los resultados.  
  
    -   Seleccione **Directiva de coincidencia** para crear una directiva de coincidencia y agregarla a la base de conocimiento.  
  
5.  Haga clic en **Abrir**.  
  
    > [!NOTE]  
    >  Para abrir la base de conocimiento, también puede hacer clic en ella con el botón secundario y seleccionar Abrir. Otros comandos del menú contextual permiten guardarla con otro nombre, desbloquearla, descartar los cambios realizados, cambiar su nombre o mostrar sus propiedades.  
  
    > [!NOTE]  
    >  Si no puede abrir la base de conocimiento porque está bloqueada, vea la sección siguiente.  
  
## Abrir una base de conocimiento reciente  
 En la lista **Base de conocimiento reciente** de la página de inicio de DQS se muestran las cinco últimas bases de conocimiento que se han abierto. Esto le da la posibilidad de abrir una base de conocimiento en la que ha trabajado recientemente sin necesidad de pasar por la página **Abrir base de conocimiento** .  
  
-   Para abrir una base de conocimiento de la lista que no esté bloqueada, haga clic en la flecha derecha de la base de conocimiento y seleccione la actividad que desea abrir.  
  
-   Para abrir una base de conocimiento de la lista que ha bloqueado usted, haga clic en ella; la base de conocimiento se abrirá en la actividad y en la página indicadas entre paréntesis.  
  
-   Para abrir una base de conocimiento de la lista que ha bloqueado otra persona, póngase en contacto con dicha persona y pídale que la desbloquee.  
  
##  <a name="FollowUp"></a> Seguimiento: después de abrir una base de conocimiento  
 Después de abrir una base de conocimiento, esta adquiere el estado indicado en la columna Estado de la tabla de bases de conocimiento. Para las actividades de detección de conocimiento y directiva de coincidencia, la base de conocimiento se abre en una página específica del asistente. Para la actividad de administración de dominios, la base de conocimiento se abre en la página Administración de dominios. Para obtener más información acerca de los Estados, consulte [realizar la detección de conocimiento](../data-quality-services/perform-knowledge-discovery.md), [administrar un dominio](../data-quality-services/managing-a-domain.md), o [crear una directiva de coincidencia](../data-quality-services/create-a-matching-policy.md).  
  
##  <a name="Locked"></a> Si la base de conocimiento está bloqueada  
 El icono de candado en la primera columna indica si la base de conocimiento está bloqueada. Cuando una base de conocimiento está bloqueada, su nombre aparece en color rojo. Si un usuario específico está modificando una base de conocimiento a través de una actividad, la base de conocimiento se marca como bloqueada. En una base de conocimiento bloqueada no puede trabajar un segundo usuario. El usuario que está trabajando en la base de conocimiento puede desbloquearla haciendo clic en la base de conocimiento en la tabla en la página Abrir Base de conocimiento y haga clic en **Unlock**, o su publicación. Cuando el cursor se sitúa en una base de conocimiento bloqueada, DQS muestra una sugerencia que indica quién la bloqueó y cuándo lo hizo.  
  
##  <a name="State"></a> Estado de una base de conocimiento  
 El campo Estado indica en qué fase de una actividad se encuentra la base de conocimiento. Si abre la base de conocimiento, se abrirá en esa fase.  
  
-   **\< vacío>**: el campo estado aparece vacío para una base de conocimiento si ha publicado haciendo clic en la base de conocimiento **publicar** en la actividad de administración de dominios y haga clic en **Sí – publicar la base de conocimiento y salir**.  
  
-   **Trabajando**: el trabajo realizado en la base de conocimiento se ha guardado haciendo clic en **Publicar** en la actividad Administración de dominios y haciendo clic en **No – Guardar el trabajo en la base de conocimiento y salir**.  
  
-   **Administración de dominios**: se han especificado datos para un dominio de la base de conocimiento, pero esta no se ha publicado y el trabajo permanece en la actividad Administración de dominios. La actividad Detección de conocimiento no está disponible. Esto sucede si se hace clic en **Cerrar** en la pantalla **Administración de dominios** .  
  
-   **Detección - asignación**: la base de conocimiento se cerró en la **administración de la Base de conocimiento: asignación** página. La base de conocimiento está bloqueada y las actividades de administración de dominios y búsqueda de coincidencias no están disponibles.  
  
-   **Detección - detectar**: la base de conocimiento se cerró en la **administración de la Base de conocimiento: analizar** página. La base de conocimiento está bloqueada y la actividad Administración de dominios no está disponible.  
  
-   **Detección de conocimiento: administrar valores del dominio**: la base de datos se cerró en la página **Administración de la base de conocimiento: Administrar valores del dominio** . La base de conocimiento está bloqueada y la actividad Administración de dominios no está disponible.  
  
-   **Directiva de coincidencia: directiva de coincidencia**: La base de conocimiento se cerró en la página **Directiva de coincidencia: directiva de coincidencia** . La base de conocimiento está bloqueada y las actividades de detección de conocimiento y administración de dominios no están disponibles.  
  
-   **Directiva de coincidencia: resultados**: La base de conocimiento se cerró en la página de **Directiva de coincidencia: resultados** . La base de conocimiento está bloqueada y las actividades de detección de conocimiento y administración de dominios no están disponibles.  
  
  