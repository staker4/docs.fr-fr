---
title: ICorConfiguration::AddDebuggerSpecialThread, méthode
ms.date: 03/30/2017
api_name:
- ICorConfiguration.AddDebuggerSpecialThread
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AddDebuggerSpecialThread
helpviewer_keywords:
- AddDebuggerSpecialThread method [.NET Framework hosting]
- ICorConfiguration::AddDebuggerSpecialThread method [.NET Framework hosting]
ms.assetid: 1f1e3239-438e-4be9-a3bb-7d0722d3a76d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca33c8eb5e214cdaaa49905c311fd62042285d4f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569285"
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a>ICorConfiguration::AddDebuggerSpecialThread, méthode
Pour les services de débogage, indique qu’un thread particulier doit être autorisé à continuer à s’exécuter pendant que le débogueur arrête les scénarios de débogage managées ou une application.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `dwSpecialThreadId`  
 [in] L’ID du thread qui doit être autorisée à se poursuivre l’exécution.  
  
## <a name="remarks"></a>Notes  
 Le thread spécifié ne pas exécuter du code managé ou entrez le runtime en aucune façon. Un exemple d’un tel thread serait un thread de processus pour prendre en charge les débogueurs de script hérité.  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** MSCorEE.h  
  
 **Bibliothèque :** Inclus en tant que ressource dans MSCorEE.dll  
  
 **Versions du .NET Framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi
- [ICorConfiguration, interface](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
