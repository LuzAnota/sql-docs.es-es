---
title: Elemento AttributeAllMemberTranslations (ASSL) | Documentos de Microsoft
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- AttributeAllMemberTranslations Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- AttributeAllMemberTranslations
helpviewer_keywords:
- AttributeAllMemberTranslations element
ms.assetid: 1a0d86ea-d95d-4d93-b321-acd35ed4ac26
caps.latest.revision: 36
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: d3e9208e7b4568a751b3a3a65ab9f17c0919093f
ms.contentlocale: es-es
ms.lasthandoff: 09/01/2017

---
# <a name="attributeallmembertranslations-element-assl"></a>Elemento AttributeAllMemberTranslations (ASSL)
  Contiene la colección de traducciones para el título del miembro All de la dimensión.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
  
<Dimension>  
   ...  
   <AttributeAllMemberTranslations>  
      <AttributeAllMemberTranslation xsi:type="Translation">...</AttributeAllMemberTranslation>  
   </AttributeAllMemberTranslations>  
      ...  
</Dimension>  
```  
  
## <a name="element-characteristics"></a>Características de los elementos  
  
|Característica|Descripción|  
|--------------------|-----------------|  
|Tipo y longitud de los datos|Ninguno|  
|Valor predeterminado|Ninguno|  
|Cardinalidad|0-1: Elemento opcional que puede aparecer solo una vez.|  
  
## <a name="element-relationships"></a>Relaciones del elemento  
  
|Relación|Elemento|  
|------------------|-------------|  
|Elementos primarios|[Dimension](../../../analysis-services/scripting/objects/dimension-element-assl.md)|  
|Elementos secundarios|[AttributeAllMemberTranslation](../../../analysis-services/scripting/objects/attributeallmembertranslation-element-assl.md)|  
  
## <a name="remarks"></a>Comentarios  
 El elemento que corresponde al elemento primario de **AttributeAllMemberTranslations** en el objeto de Analysis Management Objects (AMO) es el modelo <xref:Microsoft.AnalysisServices.Dimension>.  
  
## <a name="see-also"></a>Vea también  
 [Translation, elemento &#40; ASSL &#41;](../../../analysis-services/scripting/objects/translation-element-assl.md)   
 [Colecciones de &#40; ASSL &#41;](../../../analysis-services/scripting/collections/collections-assl.md)  
  
  