---
title: "Origen de archivo plano | Microsoft Docs"
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
  - "sql13.dts.designer.flatfilesource.f1"
helpviewer_keywords: 
  - "orígenes [Integration Services], archivo plano"
  - "archivo de texto, leer [Integration Services]"
  - "archivos planos"
  - "origen de archivo plano"
ms.assetid: 4a64f7f3-f25d-4db0-93b3-a29496030e58
caps.latest.revision: 50
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 50
---
# Origen de archivo plano
  El origen de archivo plano lee datos de un archivo de texto. El archivo de texto puede tener formato delimitado, de ancho fijo o mixto.  
  
-   El formato delimitado utiliza columna y delimitadores de filas para definir columnas y filas.  
  
-   El formato de ancho fijo utiliza el ancho para definir columnas y filas. Este formato también incluye un carácter para rellenar los campos hasta alcanzar el ancho máximo.  
  
-   El formato derecho irregular utiliza el ancho para definir todas las columnas, excepto la última, que se delimita mediante el delimitador de filas.  
  
 Puede configurar el origen de archivo plano de las maneras siguientes:  
  
-   Agregue una columna a la salida de transformación que contiene el nombre del archivo de texto del que el origen de archivo plano extrae datos.  
  
-   Especifique si el origen de archivo plano interpreta las cadenas de longitud cero de las columnas como valores NULL.  
  
    > [!NOTE]  
    >  El administrador de conexiones de archivos planos utilizado por el origen de archivo plano debe configurarse para usar un formato delimitado a fin de interpretar cadenas de longitud cero como valores NULL. Si el administrador de conexiones utiliza los formatos de ancho fijo o derecho irregular, los datos que estén formados por espacios no se podrán interpretar como valores NULL.  
  
 Las columnas de salida en la salida del origen de archivo plano incluyen la propiedad FastParse. FastParse indica si la columna usa las rutinas de análisis más rápidas que no distinguen la configuración regional y permiten un análisis rápido que [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] proporciona, o las rutinas de análisis estándar que sí distinguen la configuración regional. Para obtener más información, consulte [Fast Parse](../Topic/Fast%20Parse.md) y [Standard Parse](../Topic/Standard%20Parse.md).  
  
 Las columnas de salida también incluyen la propiedad UseBinaryFormat. Esta propiedad se usa para implementar en archivos la compatibilidad con datos binarios, como los datos con formato decimal. De forma predeterminada se establece UseBinaryFormat en **False**. Si quiere usar un formato binario, establezca UseBinaryFormat en **True** y el tipo de datos de la columna de salida en **DT_BYTES**. Al hacer esto, el origen de archivos planos omite la conversión de los datos y los pasa a la columna de salida tal y como están. A continuación, se puede usar una transformación como Columna derivada o Conversión de datos para convertir los datos **DT_BYTES** en otro tipo de datos; también se puede escribir un script personalizado en una transformación de script para interpretar los datos. Por último, también se puede escribir un componente de flujo de datos personalizado que interprete los datos. Para obtener más información sobre los tipos de datos en que se pueden convertir los datos **DT_BYTES**, vea [Conversión &#40;expresión de SSIS&#41;](../../integration-services/expressions/cast-ssis-expression.md).  
  
 Este origen utiliza un administrador de conexiones de archivos planos para tener acceso al archivo de texto. Si establece las propiedades del administrador de conexiones de archivos planos, puede proporcionar información sobre el archivo y cada columna que contiene, y especificar cómo debe controlar el origen de archivo plano los datos del archivo de texto. Por ejemplo, puede especificar los caracteres que delimitan columnas y filas en el archivo, así como el tipo de datos y la longitud de cada columna. Para más información, consulte [Flat File Connection Manager](../../integration-services/connection-manager/flat-file-connection-manager.md).  
  
 Este origen tiene una salida y una salida de error.  
  
## Configuración del origen de archivo plano  
 Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.  
  
 Para obtener más información acerca de las propiedades que puede establecer en el cuadro de diálogo **Editor de origen de archivos planos** , haga clic en uno de los temas siguientes:  
  
-   [Editor de origen de archivos planos &#40;página Administrador de conexiones&#41;](../../integration-services/data-flow/flat-file-source-editor-connection-manager-page.md)  
  
-   [Editor de origen de archivos planos &#40;página Columnas&#41;](../../integration-services/data-flow/flat-file-source-editor-columns-page.md)  
  
-   [Editor de origen de archivos planos &#40;página Salida de error&#41;](../../integration-services/data-flow/flat-file-source-editor-error-output-page.md)  
  
 El cuadro de diálogo **Editor avanzado** indica las propiedades que se pueden establecer mediante programación. Para obtener más información acerca de las propiedades que puede establecer a través del cuadro de diálogo **Editor avanzado** o mediante programación, haga clic en uno de los temas siguientes:  
  
-   [Propiedades comunes](../Topic/Common%20Properties.md)  
  
-   [Propiedades personalizadas de archivo plano](../../integration-services/data-flow/flat-file-custom-properties.md)  
  
## Tareas relacionadas  
 Para obtener más detalles sobre cómo establecer las propiedades de un componente de flujo de datos, vea [Establecer las propiedades de un componente de flujo de datos](../../integration-services/data-flow/set-the-properties-of-a-data-flow-component.md).  
  
## Vea también  
 [Destino de archivo plano](../../integration-services/data-flow/flat-file-destination.md)   
 [Flujo de datos](../../integration-services/data-flow/data-flow.md)  
  
  