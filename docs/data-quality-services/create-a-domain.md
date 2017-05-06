---
title: "Crear un dominio | Microsoft Docs"
ms.custom: ""
ms.date: "11/08/2011"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "data-quality-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.dqs.kb.createdomain.f1"
ms.assetid: 5c4828f5-bd51-4c29-b3de-87b7d2f2d3e5
caps.latest.revision: 23
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 23
---
# Crear un dominio
  En este tema se describe cómo crear un dominio en [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS). Los valores del dominio son una representación semántica de los datos de un campo. Para obtener más información sobre dominios, consulte [administrar un dominio](../data-quality-services/managing-a-domain.md).  
  
 Hay dos maneras de crear un nuevo dominio. La primera es durante el paso de asignación de la actividad de detección de conocimiento, cuando se analiza una muestra de los datos para agregar conocimiento a una base de conocimiento nueva o a una ya existente. La segunda es durante la actividad de administración de dominios, cuando se crea un nuevo dominio en lugar de modificar uno ya existente.  
  
##  <a name="BeforeYouBegin"></a> Antes de empezar  
  
###  <a name="Prerequisites"></a> Requisitos previos  
 Para crear un dominio, debe haber creado y abierto una base de conocimiento.  
  
###  <a name="Security"></a> Seguridad  
  
####  <a name="Permissions"></a> Permisos  
 Debe disponer del rol dqs_kb_editor o dqs_administrator en la base de datos DQS_MAIN para crear un dominio.  
  
##  <a name="Discovery"></a> Crear un dominio en la actividad Detección de conocimiento  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)] [Ejecute la aplicación de cliente de calidad de datos](../data-quality-services/run-the-data-quality-client-application.md).  
  
2.  En la página de inicio de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , haga clic en **Abrir base de conocimiento** y seleccione una base de conocimiento, o haga clic en **Nueva base de conocimiento** y especifique las propiedades para la nueva base de conocimiento.  
  
3.  Seleccione **Detección de conocimiento** como actividad y, a continuación, haga clic en **Crear** para crear la nueva base de conocimiento o en **Abrir** para abrir una ya existente.  
  
4.  En la página **Asignación** , especifique una conexión con el origen de datos. Para obtener más información, vea [Perform Knowledge Discovery](../data-quality-services/perform-knowledge-discovery.md).  
  
5.  En el **asignaciones** tabla, seleccione una columna de origen en la lista desplegable de la **columna de origen** columna de una fila vacía. Si no existe ningún dominio correspondiente, haga clic en el icono **Crear un dominio** .  
  
##  <a name="DomainManagement"></a> Crear un dominio en la actividad Administración de dominios  
  
1.  En la página de inicio de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , haga clic en **Abrir base de conocimiento** y seleccione una base de conocimiento, o haga clic en **Nueva base de conocimiento** y especifique las propiedades para la nueva base de conocimiento.  
  
2.  Seleccione **Administración de dominios** como actividad y, a continuación, haga clic en **Crear** para crear la nueva base de conocimiento o en **Abrir** para abrir una ya existente.  
  
3.  En la página **Administración de dominios** , haga clic en el icono **Crear un dominio** situado sobre la lista de dominios.  
  
##  <a name="Properties"></a> Establecer las propiedades de dominio  
  
1.  En el cuadro de diálogo **Crear dominio** , escriba un nombre que sea único en la base de conocimiento y una descripción con una longitud máxima de 256 caracteres.  
  
    > [!NOTE]  
    >  Para obtener más información acerca de las propiedades de dominio, consulte [establecer propiedades del dominio](../data-quality-services/set-domain-properties.md).  
  
2.  En la lista **Tipo de datos** , seleccione un tipo de datos para los valores del dominio. El tipo de datos puede ser **cadena** (valor predeterminado), **fecha**, **entero**, o **Decimal**.  
  
3.  Seleccione **Usar valores iniciales** para especificar que se mostrará el valor inicial de un grupo de sinónimos en lugar de un valor que sea un sinónimo. Anule la selección **Usar valores iniciales** para especificar que cada valor de sinónimo se mostrará en su forma correcta o corregida, y que no será reemplazado por el valor inicial de su grupo.  
  
4.  Si el tipo de datos es **Cadena**, seleccione **Normalizar cadena** para quitar caracteres especiales de los valores de dominio, lo que puede aumentar las probabilidades de que se produzcan coincidencias.  
  
5.  Desde el **formato de salida para** lista de lista desplegable, seleccione el formato que se aplicará cuando los valores de datos en el dominio. El formato es específico del tipo de datos seleccionado en el paso 2, tal como se muestra en la lista siguiente:  
  
    -   Para un valor de cadena, puede especificar que esta se genere en mayúsculas, en minúsculas o con la inicial en mayúsculas.  
  
    -   Para un valor de fecha, puede especificar el formato del día, del mes y del año.  
  
    -   Para un valor entero, puede especificar el tipo de máscara de formato que se aplicará.  
  
    -   Para un valor decimal, puede especificar la precisión y el tipo de máscara de formato que se aplicará.  
  
     Seleccionar **Ninguno** en el **formato de salida para** lista desplegable significa que se aplicará ninguno de los formatos de la lista.  
  
6.  Si el tipo de datos es **cadena**, en la **idioma** lista de lista desplegable, seleccione la versión de idioma del corrector ortográfico que desea aplicar si se habilita el corrector ortográfico.  
  
7.  Si el tipo de datos es **Cadena**, seleccione **Habilitar corrector ortográfico** para ejecutar el corrector ortográfico en todos los valores de cadena al rellenar el dominio.  
  
8.  Si el tipo de datos es **Cadena**, seleccione **Deshabilitar algoritmos de error de sintaxis** para rellenar el dominio sin comprobar la existencia de errores de sintaxis en los valores de cadena.  
  
9. Haga clic en **Aceptar**.  
  
10. Haga clic en **Finalizar** para finalizar la actividad de administración de dominios, tal como se describe en [End the Domain Management Activity](../Topic/End%20the%20Domain%20Management%20Activity.md).  
  
##  <a name="FollowUp"></a> Seguimiento: después de crear un dominio  
 Una vez creado el dominio, puede realizar otras tareas de administración en el dominio, ejecutar la detección de conocimiento para agregar conocimiento al dominio o agregar a este una directiva de coincidencia. Para obtener más información, consulte [realizar la detección de conocimiento](../data-quality-services/perform-knowledge-discovery.md), [administrar un dominio](../data-quality-services/managing-a-domain.md), o [crear una directiva de coincidencia](../data-quality-services/create-a-matching-policy.md).  
  
  