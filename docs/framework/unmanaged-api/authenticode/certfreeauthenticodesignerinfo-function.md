---
title: CertFreeAuthenticodeSignerInfo, fonction
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeSignerInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 8029633c-b6e4-4665-a7c2-89607c3247ef
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4282be8e57c965e14398a9284002b1191c5169fa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54708036"
---
# <a name="certfreeauthenticodesignerinfo-function"></a>CertFreeAuthenticodeSignerInfo, fonction
Libère les ressources allouées pour le [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pSignerInfo`  
 [en entrée, en sortie] Les informations du signataire à libérer. Consultez le [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.  
  
## <a name="return-value"></a>Valeur de retour  
 `S_OK` si la fonction réussit. Sinon, retourne un code d'erreur.  
  
## <a name="see-also"></a>Voir aussi
- [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
