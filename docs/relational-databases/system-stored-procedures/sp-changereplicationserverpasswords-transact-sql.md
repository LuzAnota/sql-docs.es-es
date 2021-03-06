---
title: sp_changereplicationserverpasswords (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- sp_changereplicationserverpasswords_TSQL
- sp_changereplicationserverpasswords
helpviewer_keywords:
- sp_changereplicationserverpasswords
ms.assetid: 9333da96-3a1c-4adb-9a74-5dac9ce596df
author: VanMSFT
ms.author: vanto
manager: craigg
ms.openlocfilehash: bfe5d9f7bc5c95055af06b0582f2ddcf88ae7cdf
ms.sourcegitcommit: 7aa6beaaf64daf01b0e98e6c63cc22906a77ed04
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54125715"
---
# <a name="spchangereplicationserverpasswords-transact-sql"></a>sp_changereplicationserverpasswords (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Cambia las contraseñas almacenadas para la [!INCLUDE[msCoName](../../includes/msconame-md.md)] cuenta de Windows o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] inicio de sesión utilizado por los agentes de replicación al conectarse a servidores en una topología de replicación. Normalmente tendría que cambiar una contraseña para cada agente individual que se ejecutara en un servidor, aunque todos utilizaran el mismo inicio de sesión o la misma cuenta. Este procedimiento almacenado permite cambiar la contraseña para todas las instancias de un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o una cuenta de Windows específicos utilizados por todos los agentes de replicación que se ejecutan en un servidor. Este procedimiento almacenado se ejecuta en cualquier servidor de la topología de replicación de la base de datos maestra.  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
sp_changereplicationserverpasswords [ @login_type = ] login_type  
        , [ @login = ] 'login'   
        , [ @password = ] 'password'  
    [ , [ @server = ] 'server' ]  
```  
  
## <a name="arguments"></a>Argumentos  
 [ **@login_type** =] *login_type*  
 Es el tipo de autenticación de las credenciales proporcionadas. *LOGIN_TYPE* es **tinyint**, no tiene ningún valor predeterminado.  
  
 **1** = autenticación integrada de Windows  
  
 **0**  =  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] autenticación  
  
 [ **@login** =] **'**_inicio de sesión_**'**  
 Es el nombre de la cuenta de Windows o del inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que se va a cambiar. *inicio de sesión* es **nvarchar (257)**, no tiene ningún valor predeterminado  
  
 [ **@password** =] **'**_contraseña_**'**  
 Es la nueva contraseña que se almacenará para el elemento especificado *inicio de sesión*. *contraseña* es **sysname**, no tiene ningún valor predeterminado.  
  
> [!NOTE]  
>  Después de cambiar una contraseña de replicación, es necesario detener y reiniciar cada agente que utilice la contraseña para que el cambio surta efecto en dicho agente.  
  
 [ **@server** =] **'**_server_**'**  
 Es la conexión con el servidor cuya contraseña almacenada se está cambiando. *servidor* es **sysname**, y puede tener uno de estos valores:  
  
|Valor|Descripción|  
|-----------|-----------------|  
|**distribuidor**|Todas las conexiones del agente al distribuidor.|  
|**publicador**|Todas las conexiones del agente al publicador.|  
|**suscriptor**|Todas las conexiones del agente al suscriptor.|  
|**%** (valor predeterminado)|Todas las conexiones del agente a todos los servidores de una topología de replicación.|  
  
## <a name="return-code-values"></a>Valores de código de retorno  
 **0** (correcto) o **1** (error)  
  
## <a name="remarks"></a>Comentarios  
 **sp_changereplicationserverpasswords** se utiliza con todos los tipos de replicación.  
  
## <a name="permissions"></a>Permisos  
 Solo los miembros de la **sysadmin** rol fijo de servidor puede ejecutar **sp_changereplicationserverpasswords**.  
  
## <a name="see-also"></a>Vea también  
 [Ver y modificar la configuración de seguridad de la replicación](../../relational-databases/replication/security/view-and-modify-replication-security-settings.md)  
  
  
