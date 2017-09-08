---
title: "CREAR SUBCUBO (instrucción, MDX) | Documentos de Microsoft"
ms.custom: 
ms.date: 03/02/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- CREATE_SUBCUBE
- CREATE SUBCUBE
- CREATE
- SUBCUBE
dev_langs:
- kbMDX
helpviewer_keywords:
- subcubes [MDX]
- CREATE SUBCUBE statement
ms.assetid: 15b6ac4c-b68a-4f9f-b33c-f5f7c4a74535
caps.latest.revision: 32
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: b7a444247915755ca1e9d002acf868a7d6eecc4f
ms.contentlocale: es-es
ms.lasthandoff: 08/02/2017

---
# <a name="mdx-data-definition---create-subcube"></a>Definición de datos MDX - crear SUBCUBO
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Redefine el espacio del cubo de un cubo o subcubo especificado a un subcubo especificado. Esta instrucción cambia el espacio aparente del cubo para operaciones posteriores.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
CREATE SUBCUBE Cube_Name AS Select_Statement  
                                                  | NON VISUAL ( Select_Statement )  
```  
  
## <a name="arguments"></a>Argumentos  
 *Restricciones obligatorias Cube_Name*  
 Expresión de cadena válida que proporciona el nombre del cubo o la perspectiva que se está restringiendo, que se convierte en el nombre del subcubo.  
  
 *Select_Statement*  
 Expresión MDX (Expresiones multidimensionales) válida SELECT que no contiene cláusulas WITH, NON EMPTY o HAVING y no solicita propiedades de dimensión o celda.  
  
 Vea [seleccione instrucción &#40; MDX &#41; ](../mdx/mdx-data-manipulation-select.md) para obtener una explicación detallada de sintaxis en instrucciones Select y **NON VISUAL** cláusula.  
  
## <a name="remarks"></a>Comentarios  
 Cuando se excluyen los miembros predeterminados de la definición de un subcubo, las coordenadas cambian a su vez. Para los atributos que pueden agregarse, el miembro predeterminado se mueve al miembro [Todos]. Para los atributos que no pueden agregarse, el miembro predeterminado se mueve a un miembro que existe en el subcubo. En la tabla siguiente se ofrece un ejemplo de subcubo y las combinaciones de miembros predeterminados.  
  
|Miembro predeterminado original|Puede agregarse|Subselección|Miembro predeterminado revisado|  
|-----------------------------|-----------------------|---------------|----------------------------|  
|Time.Year.All|Sí|{Time.Year.2003}|No hay ningún cambio|  
|Time.Year. [1997]|Sí|{Time.Year.2003}|Time.Year.All|  
|Time.Year. [1997]|No|{Time.Year.2003}|Time.Year. [2003]|  
|Time.Year. [1997]|Sí|{Time.Year.2003, Time.Year.2004}|Time.Year.All|  
|Time.Year. [1997]|No|{Time.Year.2003, Time.Year.2004}|Time.Year.[2003] o<br /><br /> Time.Year.[2004]|  
  
 Los miembros [Todos] siempre existirán en un subcubo.  
  
 Los objetos de sesión creados en el contexto de un área de subcubo se quitan cuando se quita el subcubo.  
  
 Para obtener más información acerca de los subcubos, vea [generar subcubos en MDX &#40; MDX &#41; ](../analysis-services/multidimensional-models/mdx/building-subcubes-in-mdx-mdx.md).  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente crea un subcubo que limita el espacio aparente del cubo a los miembros que existen con el país Canadá. A continuación, utiliza el **miembros** función para devolver todos los miembros del país en el nivel de jerarquía definida por el usuario Geography - devuelve solo el país Canadá.  
  
```  
CREATE SUBCUBE [Adventure Works] AS  
   SELECT [Geography].[Country].&[Canada] ON 0  
   FROM [Adventure Works]  
  
SELECT [Geography].[Country].[Country].MEMBERS ON 0  
   FROM [Adventure Works]  
  
```  
  
 En el ejemplo siguiente se crea un subcubo que limita el espacio aparente del cubo a los miembros {Accessories, Clothing} de Products.Category y {[Value Added Reseller], [Warehouse]} en Resellers.[Business Type].  
  
 `CREATE SUBCUBE [Adventure Works] AS`  
  
 `Select {[Category].Accessories, [Category].Clothing} on 0,`  
  
 `{[Business Type].[Value Added Reseller], [Business Type].[Warehouse]} on 1`  
  
 `from [Adventure Works]`  
  
 La consulta de todos los miembros del subcubo en Products.Category y Resellers. [Business Type] con el MDX siguiente:  
  
 `select [Category].members on 0,`  
  
 `[Business Type].members on 1`  
  
 `from [Adventure Works]`  
  
 `where [Measures].[Reseller Sales Amount]`  
  
 Produce los resultados siguientes:  
  
|||||  
|-|-|-|-|  
||All Products|Accessories|Clothing|  
|All Resellers|$2,031,079.39|$506,172.45|$1,524,906.93|  
|Value Added Reseller|$767,388.52|$175,002.81|$592,385.71|  
|Warehouse|$1,263,690.86|$331,169.64|$932,521.23|  
  
 Si se quita y se vuelve a crear el subcubo con la cláusula NO VISUAL, se creará un subcubo con los verdaderos totales de todos los miembros de Products.Category y Resellers.[Business Type], estén o no visibles en el subcubo.  
  
 `CREATE SUBCUBE [Adventure Works] AS`  
  
 `NON VISUAL (Select {[Category].Accessories, [Category].Clothing} on 0,`  
  
 `{[Business Type].[Value Added Reseller], [Business Type].[Warehouse]} on 1`  
  
 `from [Adventure Works])`  
  
 La ejecución de la misma consulta MDX anterior:  
  
 `select [Category].members on 0,`  
  
 `[Business Type].members on 1`  
  
 `from [Adventure Works]`  
  
 `where [Measures].[Reseller Sales Amount]`  
  
 Produce los resultados diferentes siguientes:  
  
|||||  
|-|-|-|-|  
||All Products|Accessories|Clothing|  
|All Resellers|$80,450,596.98|$571,297.93|$1,777,840.84|  
|Value Added Reseller|$34,967,517.33|$175,002.81|$592,385.71|  
|Warehouse|$38,726,913.48|$331,169.64|$932,521.23|  
  
 La columna [All Products] y la fila [All Resellers] contienen los totales de todos los miembros y no solo de los que están visibles.  
  
## <a name="see-also"></a>Vea también  
 [Conceptos clave de MDX &#40; Analysis Services &#41;](../analysis-services/multidimensional-models/mdx/key-concepts-in-mdx-analysis-services.md)   
 [Instrucciones de Scripting de MDX &#40; MDX &#41;](../mdx/mdx-scripting-statements-mdx.md)   
 [DROP SUBCUBE, instrucción &#40; MDX &#41;](../mdx/mdx-data-definition-drop-subcube.md)   
 [Instrucción SELECT &#40; MDX &#41;](../mdx/mdx-data-manipulation-select.md)  
  
  
