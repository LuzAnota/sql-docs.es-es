---
title: Quitar una extensión de representación | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.topic: reference
helpviewer_keywords:
- deleting rendering extensions
- removing rendering extensions
- rendering extensions [Reporting Services], removing
ms.assetid: 2abfebfb-065f-45cc-a904-c914394cf900
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: 5c8f55dd0fa663d5516938e9ca39b5a6dc2caed9
ms.sourcegitcommit: dfb1e6deaa4919a0f4e654af57252cfb09613dd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "56014636"
---
# <a name="removing-a-rendering-extension"></a>Quitar una extensión de representación
  Para quitar un [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] extensión de representación, basta con quitar el `Extension` (elemento) para la extensión de representación del archivo rsreportserver.config, situado en **%ProgramFiles%\Microsoft SQL Server\MSRS10_50.\< Nombre de instancia > \Reporting** carpeta. Si efectuó entradas para un diseñador de informes, así como un servidor de informes, quite el `Extension` elemento desde el [RSReportDesigner Configuration File](../../report-server/rsreportdesigner-configuration-file.md) también. Después de quitar la información de configuración, la extensión de representación de datos ya no estará disponible en el componente.  
  
## <a name="see-also"></a>Vea también  
 [Archivos de configuración de Reporting Services](../../report-server/reporting-services-configuration-files.md)   
 [Implementar una extensión de representación](implementing-a-rendering-extension.md)   
 [Información general de las extensiones de representación](rendering-extensions-overview.md)   
 [Implementar la interfaz IRenderingExtension](implementing-the-irenderingextension-interface.md)   
 [Consideraciones de seguridad para las extensiones](../security-considerations-for-extensions.md)   
 [Implementación de una extensión de representación](deploying-a-rendering-extension.md)  
  
  
