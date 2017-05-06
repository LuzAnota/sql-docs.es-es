---
title: "Preparación de los datos para exportar o importar de forma masiva (SQL Server) | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- dbe-bulk-import-export
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- bulk importing [SQL Server], planning
- bulk importing [SQL Server], from a CSV file
- data formats [SQL Server], planning operations
- CSV files [SQL Server]
- quoted fields in CSV files [SQL Server]
ms.assetid: 783fd581-2e5f-496b-b79c-d4de1e09ea30
caps.latest.revision: 52
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: fbcca0ce4e711ba22215e9e6ff09389b02d6e80b
ms.lasthandoff: 04/11/2017

---
# <a name="prepare-data-for-bulk-export-or-import-sql-server"></a>Preparar los datos para exportar o importar de forma masiva (SQL Server)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  En esta sección se explican las consideraciones implicadas en el planeamiento de operaciones de exportación masiva y los requisitos para operaciones de importación masiva.  
  
> [!NOTE]  
>  Si no está seguro de cómo dar formato a un archivo de datos para la importación masiva, puede usar la utilidad **bcp** para exportar los datos de la tabla a un archivo de datos. El formato de cada campo de datos de este archivo muestra el formato requerido para la importación masiva de datos en la columna correspondiente de la tabla. Use el mismo formato de los datos para los campos del archivo de datos.  
  
## <a name="data-file-format-considerations-for-bulk-export"></a>Consideraciones sobre los formatos de archivo de datos para la exportación masiva  
 Antes de realizar una operación de exportación masiva mediante el comando **bcp** , tenga en cuenta lo siguiente:  
  
-   Cuando se exportan los datos a un archivo, el comando **bcp** crea el archivo de datos automáticamente mediante el nombre del archivo especificado. Si ese nombre de archivo ya se está usando, los datos que se están copiando masivamente en el archivo de datos sobrescriben el contenido existente del archivo.  
  
-   La exportación masiva de una tabla o una vista en un archivo de datos requiere el permiso SELECT en la tabla o en la vista que está copiando de forma masiva.  
  
-   [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] puede usar exámenes paralelos para recuperar datos. Por tanto, no se garantiza que las filas de la tabla que se está exportando masivamente desde una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estén en un orden específico en el archivo de datos. Para asegurarse de que las filas de la tabla exportada en bloque aparezcan en un determinado orden en el archivo de datos, use la opción **queryout** para exportar en bloque desde una consulta y especifique una cláusula ORDER BY.  
  
## <a name="data-file-format-requirements-for-bulk-import"></a>Requisitos de formato de los archivos de datos para la importación masiva  
 Para importar datos desde un archivo de datos, el archivo debe cumplir los siguientes requisitos básicos:  
  
-   Los datos deben tener un formato de fila y columna.  
  
> [!NOTE]  
>  No es necesario que la estructura del archivo de datos sea idéntica a la estructura de la tabla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ya que las columnas se pueden omitir o se puede cambiar el orden de las columnas durante el proceso de importación masiva.  
  
-   El contenido del archivo de datos debe tener un formato admitido, como un formato de caracteres o nativo.  
  
-   Los datos pueden estar en formato de caracteres o binario nativo, incluido Unicode.  
  
-   Para importar datos mediante un comando **bcp**, una instrucción BULK INSERT o una instrucción INSERT... SELECT * FROM OPENROWSET(BULK...), la tabla de destino ya debe existir.  
  
-   Cada campo del archivo de datos debe ser compatible con la columna correspondiente de la tabla de destino. Por ejemplo, un campo **int** no puede cargarse en una columna **datetime** . Para obtener más información, vea [Formatos de datos para importación o exportación masiva &#40;SQL Server&#41;](../../relational-databases/import-export/data-formats-for-bulk-import-or-bulk-export-sql-server.md) y [Especificar formatos de datos por razones de compatibilidad mediante bcp &#40;SQL Server&#41;](../../relational-databases/import-export/specify-data-formats-for-compatibility-when-using-bcp-sql-server.md).  
  
    > [!NOTE]  
    >  Para especificar un subconjunto de filas para importarlas desde un archivo de datos, en lugar del archivo completo, puede usar un comando **bcp** con el modificador **-F** *first_row* o el modificador **-L** *last_row*. Para obtener más información, consulte [bcp Utility](../../tools/bcp-utility.md).  
  
-   Para importar datos de archivos de datos con campos de longitud fija o ancho fijo, use un archivo de formato. Para obtener más información, vea [XML, archivos de formato &#40;SQL Server&#41;](../../relational-databases/import-export/xml-format-files-sql-server.md).  
  
-   Las operaciones de importación masiva de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no admiten los archivos de valores separados por comas (CSV). Sin embargo, en algunos casos se puede utilizar un archivo de valores separados por comas (CSV) como archivo de datos para una importación masiva de datos en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Tenga en cuenta que el terminador de campo de un archivo CSV no tiene que ser una coma. Para poderse utilizar como archivo de datos para la importación masiva, un archivo CSV debe observar las restricciones siguientes:  
  
    -   Los campos de datos no contienen nunca el terminador de campo.  
  
    -   Todos los valores de un campo de datos, o ninguno de ellos, están entre comillas ("").  
  
     Para realizar la importación masiva de los datos de un archivo de tabla de [!INCLUDE[msCoName](../../includes/msconame-md.md)] FoxPro o de Visual FoxPro (.dbf), o de un archivo de hoja de cálculo de [!INCLUDE[ofprexcel](../../includes/ofprexcel-md.md)] (.xls), habría que convertir los datos en un archivo CSV que cumpliera las restricciones anteriores. La extensión de archivo normalmente será .csv. A continuación, podrá usar el archivo .csv como un archivo de datos en una operación de importación masiva de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
     En sistemas de 32 bits, es posible importar datos CSV en una tabla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sin optimizaciones de importación masiva mediante [OPENROWSET](../../t-sql/functions/openrowset-transact-sql.md) con el proveedor OLE DB para Jet. Jet trata los archivos de texto como tablas, con el esquema definido por un archivo schema.ini que se encuentra en el mismo directorio que el origen de datos.  Con los datos CSV, uno de los parámetros del archivo schema.ini sería "FORMAT=CSVDelimited". Para utilizar esta solución, tendría que entender cómo funciona Jet Test IISAMm: la sintaxis de las cadenas de conexión, el uso de schema.ini, las opciones de los valores del Registro, etc.).  Los orígenes que contienen la información más adecuada sobre esto son la Ayuda de Microsoft Access y los artículos de Knowledge Base (KB). Para más información, consulte los documentos que tratan sobre [la inicialización del controlador de origen de datos de texto](https://msdn.microsoft.com/library/office/ff834391.aspx), [cómo usar una consulta distribuida de SQL Server 7.0 con un servidor vinculado a bases de datos de acceso seguro](http://go.microsoft.com/fwlink/?LinkId=128504), [cómo usar el proveedor OLE DB 4.0 de Jet para conectarse a bases de datos ISAM](http://go.microsoft.com/fwlink/?LinkId=128505)y [cómo abrir archivos de texto delimitados usando texto del proveedor de Jet IIsam](http://go.microsoft.com/fwlink/?LinkId=128501).  
  
 Además, la importación masiva de datos desde un archivo de datos a una tabla requiere lo siguiente:  
  
-   Los usuarios deben tener los permisos INSERT y SELECT para la tabla. Los usuarios también deben tener el permiso ALTER TABLE cuando utilicen opciones que requieren operaciones de lenguaje de definición de datos (DDL), como deshabilitar restricciones.  
  
-   Al importar masivamente datos mediante BULK INSERT o INSERT ... SELECT * FROM OPENROWSET(BULK...), es necesario tener acceso al archivo de datos para opciones de lectura mediante el perfil de seguridad del proceso de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (si el usuario inicia sesión con el inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proporcionado) o con el inicio de sesión de [!INCLUDE[msCoName](../../includes/msconame-md.md)] que se utiliza con seguridad delegada. Adicionalmente, el usuario debe tener el permiso ADMINISTER BULK OPERATIONS para leer el archivo.  
  
> [!NOTE]  
>  La importación masiva en una vista con particiones no está permitida y los intentos de importar datos masivamente en una vista con particiones generarán un error.  
  
## <a name="external-resources"></a>Recursos externos  
 [Cómo importar datos de Excel en SQL Server](http://support.microsoft.com/kb/321686)  
  
## <a name="change-history"></a>Historial de cambios  
  
|Contenido actualizado|  
|---------------------|  
|Se agregó información sobre cómo utilizar el proveedor OLE DB para Jet con el fin de importar datos CSV.|  
  
## <a name="see-also"></a>Vea también  
 [bcp Utility](../../tools/bcp-utility.md)   
 [BULK INSERT &#40;Transact-SQL&#41;](../../t-sql/statements/bulk-insert-transact-sql.md)   
 [Tipos de datos &#40;Transact-SQL&#41;](../../t-sql/data-types/data-types-transact-sql.md)   
 [Usar el formato de caracteres para importar o exportar datos &#40;SQL Server&#41;](../../relational-databases/import-export/use-character-format-to-import-or-export-data-sql-server.md)   
 [Usar el formato nativo para importar o exportar datos &#40;SQL Server&#41;](../../relational-databases/import-export/use-native-format-to-import-or-export-data-sql-server.md)  
  
  