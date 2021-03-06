---
title: GetRequestedRuntimeVersionForCLSID, fonction
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersionForCLSID
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersionForCLSID
helpviewer_keywords:
- GetRequestedRuntimeVersionForCLSID function [.NET Framework hosting]
ms.assetid: 5bb12f9a-0612-434b-b4ed-2db636a20bec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e00bc95dd9b54d5451da65cefbfff13395e467f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54511957"
---
# <a name="getrequestedruntimeversionforclsid-function"></a>GetRequestedRuntimeVersionForCLSID, fonction
Obtient les informations de version du common language runtime (CLR) approprié pour la classe avec la valeur `CLSID`.  
  
 Cette fonction a été déconseillée dans le [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,   
    [out]  LPWSTR     pVersion,   
    [in]  DWORD      cchBuffer,   
    [out] DWORD*     dwLength,   
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `rclsid`  
 [in]  Le `CLSID` du composant.  
  
 `pVersion`  
 [out]  Une mémoire tampon qui contient la chaîne de numéro de version en cas de réussite.  
  
 `cchBuffer`  
 [in]  La taille, en caractères larges, de la `pVersion` mémoire tampon.  
  
 `dwLength`  
 [out] La longueur, en octets, de la mémoire tampon retournée.  
  
 `dwResolutionFlags`  
 [in]  Une des valeurs CLSID_RESOLUTION_FLAGS. Les valeurs suivantes sont prises en charge :  
  
-   CLSID_RESOLUTION_DEFAULT : (0 x 0) Spécifie que le comportement d’interopérabilité par défaut doit être utilisé.  
  
-   CLSID_RESOLUTION_REGISTERED : (0 x 1) Spécifie que le Registre doit être recherché et stratégie de shim doit être appliquée.  
  
## <a name="return-value"></a>Valeur de retour  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|La fonction a été retourné avec succès.|  
|E_INVALIDARG|L’un des paramètres a un type non valide ou le format.|  
|ERROR_INSUFFICIENT_BUFFER|Le `pVersion` mémoire tampon n’est pas assez grand pour contenir la chaîne de version entière.|  
|REGDB_E_CLASSNOTREG|Aucune classe n’est enregistrée avec la valeur `CLSID`.|  
|E_POINTER|`dwLength` a la valeur null, ou `cchBuffer` est suffisamment grande pour contenir la chaîne de version, mais `pVersion` est null.|  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** MSCorEE.h  
  
 **Versions du .NET Framework :** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi
- [Fonctions d’hébergement CLR dépréciées](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
