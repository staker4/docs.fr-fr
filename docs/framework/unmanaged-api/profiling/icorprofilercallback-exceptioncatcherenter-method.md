---
title: ICorProfilerCallback::ExceptionCatcherEnter, méthode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCatcherEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter method [.NET Framework profiling]
- ExceptionCatcherEnter method [.NET Framework profiling]
ms.assetid: 41462329-a648-46f0-ae6d-728b94c31aa9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cb31da8b3fb9148bb41cf7216b44e7cbf610eaee
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671614"
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a>ICorProfilerCallback::ExceptionCatcherEnter, méthode
Notifie le profileur que le contrôle est passé à approprié `catch` bloc.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `functionId`  
 [in] L’identificateur de la fonction contenant le `catch` bloc.  
  
 `objectId`  
 [in] Identificateur de l’exception en cours de traitement.  
  
## <a name="remarks"></a>Notes  
 Le `ExceptionCatcherEnter` méthode est appelée uniquement si le point catch est dans le code compilé avec le compilateur juste-à-temps (JIT). Une exception est interceptée dans le code non managé ou dans le code interne du runtime n’appelle pas cette notification. Le `objectId` la valeur est passée à nouveau dans la mesure où un garbage collection pourrait avoir déplacé l’objet depuis le `ExceptionThrown` notification.  
  
 Le profileur ne doit pas bloquer dans son implémentation de cette méthode, car la pile ne peut pas être dans un état qui autorise le garbage collection, et par conséquent, le garbage collection préemptif ne peut pas être activé. Si le profileur bloque ici et le garbage collection est tenté, le runtime bloque jusqu'à ce que ce rappel renvoie.  
  
 L’implémentation du profileur de cette méthode ne doit pas appeler dans du code managé ou de quelque manière qu’une allocation de mémoire managée.  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** CorProf.idl, CorProf.h  
  
 **Bibliothèque :** CorGuids.lib  
  
 **Versions du .NET Framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi
- [ICorProfilerCallback, interface](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ExceptionCatcherLeave, méthode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)
