---
title: Crear casos de prueba (OracleToSQL) | Documentos de Microsoft
ms.prod: sql-non-specified
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- sql-ssma
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Test Case Wizard
ms.assetid: 22f38901-ec35-4707-a911-784e6ad8dafb
caps.latest.revision: 7
author: sabotta
ms.author: carlasab
manager: v-thobro
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: c40ee9da718fec017381740d69b6fa71045572bd
ms.contentlocale: es-es
ms.lasthandoff: 08/02/2017

---
# <a name="creating-test-cases-oracletosql"></a>Crear casos de prueba (OracleToSQL)
Utilice al Asistente de caso de prueba para crear una prueba. Este asistente le permite crear casos de prueba eligiendo probados y comprobados los objetos y especificando los parámetros de pruebas.  
  
## <a name="starting-the-test-case-wizard"></a>Para iniciar al Asistente de caso de prueba  
Para iniciar el Asistente de caso de prueba, haga clic **nuevo caso de prueba...** desde el **Tester** menú.  
  
Cuando inicia, el asistente busca esquema SSMATESTER_ORACLE en el servidor de Oracle de origen. Es el esquema de extensión de evaluador utilizado para almacenar los objetos auxiliares. Si el Asistente de caso de prueba no se encuentra SSMATESTER_ORACLE, muestra una ventana de cuadro de diálogo que propone para crear el esquema. (Esta situación normalmente se produce durante la primera ejecución del evaluador de SSMA.)  
  
Si aparece el cuadro de diálogo, haga clic en **Sí** para crear el esquema SSMATESTER_ORACLE en el servidor de origen. Tenga en cuenta que debe tener privilegios de Oracle para crear un nuevo usuario y crear objetos en el esquema de este usuario.  
  
## <a name="overview-of-creating-test-cases-using-the-wizard"></a>Información general de creación de casos de prueba mediante el Asistente  
El proceso de creación de un caso de prueba consta de cinco pasos:  
  
1.  [Inicialización de casos de prueba &#40; OracleToSQL &#41;](../../ssma/oracle/initializing-test-cases-oracletosql.md)  
  
2.  [Seleccionar y configurar los objetos para pruebas &#40; OracleToSQL &#41;](../../ssma/oracle/selecting-and-configuring-objects-to-test-oracletosql.md)  
  
3.  [Seleccionar y configurar afectados objetos &#40; OracleToSQL &#41;](../../ssma/oracle/selecting-and-configuring-affected-objects-oracletosql.md)  
  
4.  [Personalizar el orden de las llamadas &#40; OracleToSQL &#41;](../../ssma/oracle/customizing-calls-order-oracletosql.md)  
  
5.  [Preparación de caso de prueba acabado &#40; OracleToSQL &#41;](../../ssma/oracle/finishing-test-case-preparation-oracletosql.md)  
  
## <a name="see-also"></a>Vea también  
[Pruebas migran objetos de base de datos &#40; OracleToSQL &#41;](../../ssma/oracle/testing-migrated-database-objects-oracletosql.md)  
  
