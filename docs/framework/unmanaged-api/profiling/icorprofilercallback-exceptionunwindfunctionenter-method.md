---
title: "ICorProfilerCallback::ExceptionUnwindFunctionEnter, méthode"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionUnwindFunctionEnter
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionUnwindFunctionEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionEnter method [.NET Framework profiling]
- ExceptionUnwindFunctionEnter method [.NET Framework profiling]
ms.assetid: ea3dc625-5650-4bf4-8e67-01e42be065b1
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: cc41dc95776ca31178153402d2e145a3d2c13bf5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackexceptionunwindfunctionenter-method"></a><span data-ttu-id="99dfc-102">ICorProfilerCallback::ExceptionUnwindFunctionEnter, méthode</span><span class="sxs-lookup"><span data-stu-id="99dfc-102">ICorProfilerCallback::ExceptionUnwindFunctionEnter Method</span></span>
<span data-ttu-id="99dfc-103">Notifie le profileur que la phase de déroulement de la gestion des exceptions a commencé à dérouler une fonction.</span><span class="sxs-lookup"><span data-stu-id="99dfc-103">Notifies the profiler that the unwind phase of exception handling has begun to unwind a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99dfc-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="99dfc-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="99dfc-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="99dfc-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="99dfc-106">[in] L’ID de la fonction qui n’est pas vidée.</span><span class="sxs-lookup"><span data-stu-id="99dfc-106">[in] The ID of the function that is being unwound.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99dfc-107">Remarques</span><span class="sxs-lookup"><span data-stu-id="99dfc-107">Remarks</span></span>  
 <span data-ttu-id="99dfc-108">Le profileur ne doit pas bloquer dans son implémentation de cette méthode, car la pile ne peut pas être dans un état qui autorise le garbage collection, et par conséquent, le garbage collection préemptif ne peut pas être activé.</span><span class="sxs-lookup"><span data-stu-id="99dfc-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="99dfc-109">Si le profileur bloque ici et le garbage collection est tenté, le runtime bloque jusqu'à ce que ce rappel retourne.</span><span class="sxs-lookup"><span data-stu-id="99dfc-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="99dfc-110">L’implémentation du profileur de cette méthode ne doit pas appeler dans du code managé ou de quelque manière qu’une allocation de mémoire managée.</span><span class="sxs-lookup"><span data-stu-id="99dfc-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99dfc-111">Spécifications</span><span class="sxs-lookup"><span data-stu-id="99dfc-111">Requirements</span></span>  
 <span data-ttu-id="99dfc-112">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99dfc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99dfc-113">**En-tête :** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="99dfc-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="99dfc-114">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99dfc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99dfc-115">**Versions du .NET framework :**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99dfc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99dfc-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="99dfc-116">See Also</span></span>  
 [<span data-ttu-id="99dfc-117">Interface ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="99dfc-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="99dfc-118">ExceptionUnwindFunctionLeave (méthode)</span><span class="sxs-lookup"><span data-stu-id="99dfc-118">ExceptionUnwindFunctionLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionleave-method.md)