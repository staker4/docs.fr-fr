---
title: ICorProfilerInfo2::GetThreadStaticAddress, méthode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetThreadStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetThreadStaticAddress
helpviewer_keywords:
- GetThreadStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetThreadStaticAddress method [.NET Framework profiling]
ms.assetid: 8e7dbf14-98a2-4384-a950-58a7640e59df
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3574d7e889481931f40dbfb3158ad523c7e5637e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534993"
---
# <a name="icorprofilerinfo2getthreadstaticaddress-method"></a>ICorProfilerInfo2::GetThreadStaticAddress, méthode
Obtient l’adresse du champ statique de thread spécifié qui est dans la portée du thread spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetThreadStaticAddress(  
    [in] ClassID     classId,  
    [in] mdFieldDef  fieldToken,  
    [in] ThreadID    threadId,  
    [out] void       **ppAddress);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `classId`  
 [in] ID de la classe qui contient le champ thread-static demandé.  
  
 `fieldToken`  
 [in] Le jeton de métadonnées pour le champ statique de thread demandé.  
  
 `threadId`  
 [in] L’ID du thread qui est la portée pour le champ statique demandé.  
  
 `ppAddress`  
 [out] Pointeur vers l’adresse du champ statique qui se trouve dans le thread spécifié.  
  
## <a name="remarks"></a>Notes  
 Le `GetThreadStaticAddress` méthode peut retourner l’une des opérations suivantes :  
  
-   Un HRESULT CORPROF_E_DATAINCOMPLETE si le champ statique donné n’a pas été assigné une adresse dans le contexte spécifié.  
  
-   Les adresses des objets qui peuvent être dans le tas de garbage collection. Ces adresses peuvent devenir non valides après le garbage collection, après que les profileurs de garbage collection ne doivent pas supposer qu’ils sont valides.  
  
 Avant la fin de constructeur de classe d’une classe, `GetThreadStaticAddress` retournera CORPROF_E_DATAINCOMPLETE pour tous ses champs statiques, bien que certains des champs statiques peuvent déjà être initialisés et utiliser des objets de garbage collection racine.  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** CorProf.idl, CorProf.h  
  
 **Bibliothèque :** CorGuids.lib  
  
 **Versions du .NET Framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi
- [ICorProfilerInfo, interface](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2, interface](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
