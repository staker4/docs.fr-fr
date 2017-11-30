---
title: "ICorDebugMutableDataTarget::ContinueStatusChanged, méthode"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 5a66d3f4-dd16-4d62-9dcc-0eab7041d894
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2f4f3890f2cfb2e3b017b8c7d0705d8c8e063957
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmutabledatatargetcontinuestatuschanged-method"></a><span data-ttu-id="2f03a-102">ICorDebugMutableDataTarget::ContinueStatusChanged, méthode</span><span class="sxs-lookup"><span data-stu-id="2f03a-102">ICorDebugMutableDataTarget::ContinueStatusChanged Method</span></span>
<span data-ttu-id="2f03a-103">Modifie l'état de continuation de l'événement de débogage en suspens sur le thread spécifié.</span><span class="sxs-lookup"><span data-stu-id="2f03a-103">Changes the continuation status for the outstanding debug event on the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f03a-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="2f03a-104">Syntax</span></span>  
  
```  
HRESULT ContinueStatusChanged(  
   [in] DWORD dwThreadId,  
   [in] CORDB_CONTINUE_STATUS continueStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2f03a-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="2f03a-105">Parameters</span></span>  
 `dwThreadId`  
 <span data-ttu-id="2f03a-106">Identificateur de thread défini par le système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="2f03a-106">The operating system-defined thread identifier.</span></span>  
  
 `continueStatus`  
 <span data-ttu-id="2f03a-107">A[COREDB_CONTINUE_STATUS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)valeur qui représente le nouvel état de continuation de demandé.</span><span class="sxs-lookup"><span data-stu-id="2f03a-107">A[COREDB_CONTINUE_STATUS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)value that represents the new requested continuation status.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f03a-108">Remarques</span><span class="sxs-lookup"><span data-stu-id="2f03a-108">Remarks</span></span>  
 <span data-ttu-id="2f03a-109">Le débogueur appelle la méthode `ContinueStatusChanged` quand il appelle une méthode ICorDebug qui nécessite une gestion potentiellement anormale de l'événement de débogage actif.</span><span class="sxs-lookup"><span data-stu-id="2f03a-109">The debugger calls the `ContinueStatusChanged` method when it calls an ICorDebug method that requires the current debug event to be handled in a way that is potentially different from the way in which it normally would be handled.</span></span> <span data-ttu-id="2f03a-110">Par exemple, s’il existe une exception en attente, et le débogueur demande une opération susceptible d’annuler l’exception (tel que [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) ou `FuncEval`), cette API est utilisée pour demander que l’exception soit annulé.</span><span class="sxs-lookup"><span data-stu-id="2f03a-110">For example, if there is an outstanding exception, and the debugger requests an operation that would cancel the exception (such as [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) or `FuncEval`), this API is used to request that the exception be cancelled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f03a-111">Spécifications</span><span class="sxs-lookup"><span data-stu-id="2f03a-111">Requirements</span></span>  
 <span data-ttu-id="2f03a-112">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f03a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f03a-113">**En-tête :** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2f03a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2f03a-114">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f03a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f03a-115">**Versions du .NET framework :**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f03a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f03a-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2f03a-116">See Also</span></span>  
 [<span data-ttu-id="2f03a-117">Icordebugmutabledatatarget, Interface</span><span class="sxs-lookup"><span data-stu-id="2f03a-117">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 [<span data-ttu-id="2f03a-118">Interfaces de débogage</span><span class="sxs-lookup"><span data-stu-id="2f03a-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)