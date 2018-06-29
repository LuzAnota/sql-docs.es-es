---
title: Cuadro de diálogo Detalles de conversión de columna (Asistente para importación y exportación de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- sql12.dts.impexpwizard.issuedetails.f1
ms.assetid: e2d00a39-dfbd-4821-a4d8-a5bd1164ed4d
caps.latest.revision: 12
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: cd97a1bb27858b9107312f3ac32ea61ce07f415b
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36111591"
---
# <a name="column-conversion-details-dialog-box-sql-server-import-and-export-wizard"></a>Cuadro de diálogo Detalles de conversión de columna (Asistente para importación y exportación de SQL Server)
  Use la **detalles de conversión de columna** cuadro de diálogo para revisar la información de conversión detallada sobre una columna individual. Esta información de conversión contiene el tipo de datos de la columna en el origen y el destino, y la conversión que el asistente realizará. En esta página también se enumeran los archivos de asignación de tipos de datos que el asistente utiliza para determinar las conversiones de tipos de datos que se requieren. [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] instala estos archivos de asignación de tipos de datos durante la instalación.  
  
 **Para abrir el cuadro de diálogo Detalles de la conversión de columna**  
  
1.  En el **revisar problemas de tipos de datos** página de la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard, en la **tabla** lista, seleccione una tabla.  
  
2.  En el **asignar tipos de datos** lista, haga doble clic en la fila que contiene la columna para la que desea ver los detalles de conversión.  
  
 Para obtener más información sobre la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard, vea [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md). Para obtener información acerca de las opciones para iniciar el asistente y sobre los permisos necesarios para ejecutar el asistente correctamente, consulte [ejecutar la importación de SQL Server y el Asistente para exportación de](start-the-sql-server-import-and-export-wizard.md).  
  
 El propósito de la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard consiste en copiar datos desde un origen a un destino. El asistente también puede crear una base de datos y tablas de destino. Sin embargo, si tiene que copiar diversas bases de datos o tablas, u otros tipos de objetos de bases de datos, debe utilizar el Asistente para copiar bases de datos. Para más información, consulte [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).  
  
  