---
title: LoadStringRC, fonction
ms.date: 03/30/2017
api_name:
- LoadStringRC
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRC
helpviewer_keywords:
- LoadStringRC function [.NET Framework hosting]
ms.assetid: 752e49b4-987c-4c28-a118-1a0c1ed510c5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a3e6230d245ad36b8d5346aa3b6f8911ef008b61
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54526845"
---
# <a name="loadstringrc-function"></a>LoadStringRC, fonction
Traduit une valeur HRESULT dans un message d’erreur à l’aide de la culture par défaut du thread actuel.  
  
 Cette fonction a été déconseillée dans le [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `iResourceID`  
 [in] Une valeur HRESULT.  
  
 `szBuffer`  
 [out] Une mémoire tampon qui contient le message d’erreur en cas de réussite.  
  
 `iMax`  
 [in] La taille de la mémoire tampon de message.  
  
 `bQuiet`  
 [in] Ignoré.  
  
## <a name="return-value"></a>Valeur de retour  
 Cette méthode retourne des codes d’erreur de composant COM (Object Model) standard, tel que défini dans WinError.h, en plus des valeurs suivantes.  
  
|Code de retour|Description|  
|-----------------|-----------------|  
|S_OK|La commande s'est correctement terminée.|  
|E_INVALIDARG|`szBuffer` a la valeur null ou `iMax` est zéro (0).|  
  
## <a name="remarks"></a>Notes  
 Si la méthode ne se termine pas correctement, `szBuffer` contient une chaîne vide.  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** MSCorEE.h  
  
 **Bibliothèque :** MSCorEE.dll et Mscorwks.dll. Utilisez MSCorEE.dll plutôt que Mscorwks.dll pour garantir que vous ciblez la version correcte du .NET Framework.  
  
 **Versions du .NET Framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi
- [LoadStringRCEx, fonction](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)
- [Fonctions d’hébergement CLR dépréciées](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
