---
title: ExportNestedTypeForwarder, méthode
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedTypeForwarder
helpviewer_keywords:
- ExportNestedTypeForwarder method
ms.assetid: 886ea6c5-6b26-4b88-8bf6-448d6d191950
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 25b7a708bb2f16433d9de9b5fc1c178cb48874a7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54658466"
---
# <a name="exportnestedtypeforwarder-method"></a>ExportNestedTypeForwarder, méthode
Ajoute un redirecteur de type pour un type imbriqué à la table de type de l’assembly donné.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT ExportNestedTypeForwarder(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `AssemblyID`  
 ID de l’assembly à exporter à partir de.  
  
 `FileToken`  
 ID de jeton ou l’assembly du fichier qui définit le type de fichier.  
  
 `TypeToken`  
 Jeton pour le type.  
  
 `ParentType`  
 Jeton de type parent.  
  
 `pszTypename`  
 Nom de type qualifié complet à exporter.  
  
 `dwFlags`  
 `ComType` indicateurs tels que `tdPublic` ou `tdNested`.  
  
 `pType`  
 Reçoit le jeton de type d’exportation. Cela est nécessaire uniquement pour émettre des types imbriqués.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne S_OK si la méthode réussit.  
  
## <a name="requirements"></a>Spécifications  
 Nécessite alink.h  
  
## <a name="see-also"></a>Voir aussi
- [IALink, interface](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [IALink2, interface](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [API ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
