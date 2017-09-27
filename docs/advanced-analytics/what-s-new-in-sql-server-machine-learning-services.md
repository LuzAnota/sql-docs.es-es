---
title: "¿Qué &#39; s nuevo en servicios de aprendizaje de máquina | Documentos de Microsoft"
ms.custom:
- SQL2016_New_Updated
ms.date: 09/08/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- r-services
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6aff043a-8b37-4f3f-9827-10a671e1ad1c
caps.latest.revision: 36
author: jeannt
ms.author: jeannt
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: fffe2ab906f659a2fb0e2996363ac8e7da000707
ms.openlocfilehash: 34a404511d72c5775f25dd182b018926b6d0d62e
ms.contentlocale: es-es
ms.lasthandoff: 09/18/2017

---
# <a name="whats-new-in-machine-learning-services-in-sql-server"></a>Novedades en servicios de aprendizaje de máquina en SQL Server

En SQL Server 2016, Microsoft introdujo SQL Server R Services, una característica que admita la ciencia de datos de escala empresarial, integrando el lenguaje R con el motor de base de datos de SQL Server.

En SQL Server 2017, aprendizaje automático pasa a ser más eficaz, con la adición de compatibilidad con el popular lenguaje de Python. Y la compatibilidad con nuevos idiomas incluye un nuevo nombre: **Machine Learning Services (In-Database)**.

¡Detectar el último anuncio! [Python en SQL Server 2017: mejorada de aprendizaje automático en bases de datos](https://blogs.technet.microsoft.com/dataplatforminsider/2017/04/19/python-in-sql-server-2017-enhanced-in-database-machine-learning/)

## <a name="whats-new-in-sql-server-2017"></a>Novedades de SQL Server 2017

Servidor de aprendizaje de máquina de Microsoft en SQL Server proporciona ahora compatibilidad completa para crear e implementar soluciones de aprendizaje de máquina en R o Python. Estos son los aspectos destacados de esta versión:

> [!IMPORTANT]
> 
> Servicios de aprendizaje de máquina, incluido el uso de R o Python, no se admiten cuando se ejecuta SQL Server en Linux o en la base de datos SQL de Azure. Buscar cambios en una versión posterior.
> 
> Puntuación nativo mediante la función de PREDICCIÓN se admite actualmente en la edición de Linux.
 
### <a name="in-database-python-integration"></a>Integración de Python en bases de datos

Puede ejecutar Python en procedimientos almacenados, o ejecutar de forma remota con el equipo de SQL Server como el contexto de ejecución de Python. Esta integración abre nuevas vías para la amplia comunidad de desarrolladores de Python y científicos de datos para aprovechar la eficacia de SQL Server. 

Los desarrolladores de SQL Server obtienen acceso a las bibliotecas de Python amplia desde el ecosistema de código abierto, incluidos los marcos conocidos como scikit-obtener, Tensorflow, Caffe y Theano/Keras. Y no olvide explorar las innovaciones de Microsoft como **revoscalepy** y **microsoftml**!

Ejecución de Python en bases de datos no está casi de aprendizaje automático, a la forma. Hay una gran cantidad de otras aplicaciones posibles para la integración de Python con SQL y el uso de la potencia de cada lenguaje para entregar soluciones más inteligentes y eficaces.

+ **revoscalepy**

    Esta versión incluye la versión final de **revoscalepy**, lo que proporciona equivalentes de Python de los algoritmos de RevoScaleR. Puede crear modelos de Python para las regresiones lineales y logísticas, árboles de decisión, los árboles impulsados y bosques aleatorios, paralelizar todas y puede que se ejecutan en contextos de proceso remoto.

    Para obtener más información, consulte [¿qué es revoscalepy](python/what-is-revoscalepy.md).

+ Contextos de proceso remoto de Python

    Esta versión admite el uso de varios orígenes de datos y contextos de proceso remoto. El científico de datos o el desarrollador puede ejecutar código Python en un servidor SQL Server remoto, para explorar datos o crear modelos sin mover los datos. El uso de contextos de proceso remoto requiere **revoscalepy**.

+ Compatibilidad con Python en aprendizaje de máquina de Microsoft Server (independiente)

    SQL Server 2017 incluye la opción para instalar una versión independiente de la plataforma de aprendizaje de automático de Microsoft. Mediante el uso de servidor de aprendizaje de máquina, puede distribuir y escalar código R o Python sin usar SQL Server.

    Para obtener un ejemplo de Python que se ejecuta en el servidor de aprendizaje de máquina de Microsoft, consulte [publicar y consumir código Python](python/publish-consume-python-code.md).

### <a name="new-algorithms"></a>Nuevos algoritmos

El **MicrosoftML** paquete de R y Python contiene algoritmos de aprendizaje automático de última generación y contextos de proceso de transformación de datos que puede ser escalado ni se ejecutarán en remoto. Los algoritmos incluyen redes neurales profundas personalizables, árboles de decisión rápida y bosques de decisión, regresión lineal y regresión logística.

El paquete MicrosoftML viene con interfaces de R y Python y se basa en la versión 9.2.0 del servidor de aprendizaje de máquina de Microsoft.

Para obtener más información, consulte [Introducción a MicrosoftML](using-the-microsoftml-package.md) y [microsoftml para Python](https://docs.microsoft.com/r-server/python-reference/microsoftml/microsoftml-package).

### <a name="operationalization"></a>Puesta en marcha

Esta versión contiene varias opciones y características para ayudarle a implementar y distribuir tareas de aprendizaje automático:

+ Implementar e integrar soluciones de Python de máquina, con T-SQL

    La integración de Python con T-SQL significa que se puede llamar a cualquier código de Python mediante `sp_execute_external_script`. Esta infraestructura segura permite la implementación de nivel empresarial de los modelos de Python y las secuencias de comandos que se pueda llamar desde una aplicación mediante un procedimiento almacenado simple. El rendimiento adicional es mediante transmisión por secuencias de datos de SQL a procesos de Python y la paralelización de anillo MPI.

+ **mrsdeploy** para Python

    El **mrsdeploy** el paquete para Microsoft R Server ahora admite la implementación de modelos de Python y las secuencias de comandos como servicios web y está disponible como una opción en el servidor de aprendizaje de máquina (independiente). Para obtener un ejemplo de cómo funciona, consulte [publicar y consumir código Python](python/publish-consume-python-code.md).

+ Rendimiento

    Microsoft ha impulsado sus límites de rendimiento de la puntuación. Con la puntuación en bases de datos, se procesa un millón de filas por segundo a través de modelos de R. En esta versión, nuevas características para **en tiempo real de puntuación** y **puntuación nativo** compatible con un mejor rendimiento en varias filas y la puntuación del lote. 

### <a name="realtime-scoring-and-native-scoring"></a>En tiempo real de puntuación y de puntuación nativo

En tiempo real de puntuación se basa en las bibliotecas de C++ nativo para leer un modelo que se almacenan en un formato binario optimizado y, a continuación, generar predicciones sin tener que llamar al runtime de R. Esto hace que las operaciones de puntuación mucho más rápidas.

Además, esta versión de SQL Server 2017 incluye una función nativa de T-SQL para puntuar rápido que se pueden ejecutar en cualquier edición de SQL Server, incluso en Linux. La función no requiere ninguna instalación de R o una configuración adicional. Esto significa que puede entrenar un modelo en otra parte, guárdela en SQL Server y, a continuación, realizar puntuaciones sin llamar nunca a R. Esta característica se conoce como _puntuación native_.

  - Puntuación nativo solo está disponible en SQL Server 2017. Utiliza una función de T-SQL que se puede ejecutar en cualquier edición de SQL Server, como Linux.
 - En tiempo real de puntuación se admite en SQL Server 2017 y en el servidor de aprendizaje de máquina de Microsoft. Puede ejecutar un procedimiento almacenado o realizar en tiempo real desde el código de R de puntuación.
 - En tiempo real de puntuación también está disponible para SQL Server 2016, si la instancia se actualiza a la versión más reciente de Microsoft R Server.

Para más información, vea estos artículos:

 + [En tiempo real de puntuación](real-time-scoring.md)
 + [Puntuación nativa](sql-native-scoring.md)
 + [Cómo realizar la puntuación en tiempo real o puntuación nativo](r/how-to-do-realtime-scoring.md)

### <a name="upgrade-your-machine-learning-experience-and-get-pre-trained-models"></a>Actualice su experiencia de aprendizaje automático y obtener modelos previamente entrenados

Si instaló una versión anterior de SQL Server 2016 R Services, ahora puede actualizar a la versión más reciente al cambiar el servidor para usar la directiva de ciclo de vida de Software modernas. Al hacerlo, puede sacar provecho de un ciclo de versiones más rápido para R y actualizar automáticamente todos los componentes de R. Para más información, consulte [Microsoft R Server 9.0.1](https://docs.microsoft.com/r-server/whats-new-in-r-server).

El instalador también ofrece la opción para instalar una colección de modelos previamente entrenados en formato binario. Estos modelos soportan aprendizaje automático en escenarios como reconocimiento de imágenes, que puede ser difícil para los clientes buscar grandes conjuntos de datos para entrenar un modelo. Después de instalar uno de los modelos previamente entrenados, puede usar para la predicción en sus propios datos sin el tiempo y el gasto que supone en el entrenamiento de dicho modelo grande y complejo.

Para obtener más información, vea [instalar modelos previamente entrenados en SQL Server](r/install-pretrained-models-sql-server.md)

### <a name="package-management"></a>Administración de paquetes

Esta versión incluye muchas mejoras en administración de paquetes de SQL Server. Estos incluyen:

- roles de base de datos para ayudar a lo DBA administrar y permisos de auditoría
- La instrucción crear biblioteca externa en T-SQL, para ayudar a los administradores administrar los paquetes sin necesidad de conocer R
- Un amplio conjunto de funciones de R que ayuden a instalar, quitar o enumerar los paquetes que pertenecen a los usuarios

Para obtener más información, consulte [administración del paquete](r/r-package-management-for-sql-server-r-services.md).

### <a name="get-started"></a>Introducción

+ [Configurar Python en servicios de aprendizaje de máquina de SQL Server](../advanced-analytics/python/setup-python-machine-learning-services.md)

+ [Configurar R en servicios de aprendizaje de máquina de SQL Server](r/set-up-sql-server-r-services-in-database.md)

+ [Ejemplos y tutoriales de aprendizaje de máquina](tutorials/machine-learning-services-tutorials.md)