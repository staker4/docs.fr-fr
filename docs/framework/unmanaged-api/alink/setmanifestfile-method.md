---
title: SetManifestFile, méthode
ms.date: 03/30/2017
api_name:
- IALink3.SetManifestFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetManifestFile
helpviewer_keywords:
- SetManifestFile method
ms.assetid: 1b33de4c-19cb-4a36-a93f-8675b2a36d58
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a253503f3046c004cc7109a31b5aa8fd8e8dc195
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54618049"
---
# <a name="setmanifestfile-method"></a>SetManifestFile, méthode
Vous permet de spécifier ou de réinitialiser le fichier manifest que l’éditeur de liens utilise lorsqu’il crée l’assembly.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pszFile`  
  
 Le nom du fichier manifeste dont le contenu est placé dans le blob de ressources Win32.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne S_OK si la méthode réussit.  
  
## <a name="remarks"></a>Notes  
 Appelé avant de demander pour le Win32ResBlob. La valeur de la `pszFile` paramètre est le nom du fichier manifeste dont le contenu est lu et mis dans les ressources Win32 avec l’ID de RT_MANIFEST. Lorsqu’elle est appelée à l’aide d’un paramètre de valeur NULL, tout manifeste lu précédemment est effacé. Cela permet de réinitialiser l’état de l’éditeur de liens à celle du moment de l’initialisation.  
  
## <a name="requirements"></a>Spécifications  
 Nécessite aLink.h  
  
## <a name="see-also"></a>Voir aussi
- [IALink3, interface](../../../../docs/framework/unmanaged-api/alink/ialink3-interface.md)
- [API ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
- [IALink, interface](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [Al.exe (Assembly Linker)](../../../../docs/framework/tools/al-exe-assembly-linker.md)
