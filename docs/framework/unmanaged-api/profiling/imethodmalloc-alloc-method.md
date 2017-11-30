---
title: "IMethodMalloc::Alloc, méthode"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMethodMalloc.Alloc
api_location: mscorwks.dll
api_type: COM
f1_keywords: IMethodMalloc::Alloc
helpviewer_keywords:
- IMethodMalloc::Alloc method [.NET Framework profiling]
- Alloc method, IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8653bd4c-2290-43d2-a3e1-cbbd50033f4f
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ae0fa84c08cb8e366db36b6727a3058f24789801
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2017
---
# <a name="imethodmallocalloc-method"></a><span data-ttu-id="63918-102">IMethodMalloc::Alloc, méthode</span><span class="sxs-lookup"><span data-stu-id="63918-102">IMethodMalloc::Alloc Method</span></span>
<span data-ttu-id="63918-103">Tente d’allouer une quantité de mémoire spécifiée pour un nouveau corps de fonction MSIL (intermediate language).</span><span class="sxs-lookup"><span data-stu-id="63918-103">Attempts to allocate a specified amount of memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63918-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="63918-104">Syntax</span></span>  
  
```  
PVOID Alloc (  
    [in] ULONG   cb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="63918-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="63918-105">Parameters</span></span>  
 `cb`  
 <span data-ttu-id="63918-106">[in] Le nombre d’octets à allouer pour le corps de méthode.</span><span class="sxs-lookup"><span data-stu-id="63918-106">[in] The number of bytes to allocate for the method body.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63918-107">Remarques</span><span class="sxs-lookup"><span data-stu-id="63918-107">Remarks</span></span>  
 <span data-ttu-id="63918-108">La mémoire allouée commencera à une adresse supérieure à l’adresse de base du module qui est associé à cet allocateur.</span><span class="sxs-lookup"><span data-stu-id="63918-108">The allocated memory will begin at an address greater than the base address of the module that is associated with this allocator.</span></span> <span data-ttu-id="63918-109">En d’autres termes, chaque allocateur est créé pour un module particulier et tentera d’allouer la mémoire à un offset positif à partir de son adresse de base.</span><span class="sxs-lookup"><span data-stu-id="63918-109">In other words, each allocator is created for a particular module, and will attempt to allocate memory at a positive offset from its base address.</span></span> <span data-ttu-id="63918-110">Si `Alloc` ne parvient pas à allouer le nombre requis d’octets à une adresse supérieure à l’adresse de base du module, il retourne E_OUTOFMEMORY, quelle que soit la quantité réelle de l’espace mémoire disponible.</span><span class="sxs-lookup"><span data-stu-id="63918-110">If `Alloc` fails to allocate the requested number of bytes at an address greater than the base address of the module, it returns E_OUTOFMEMORY, regardless of the actual amount of memory space available.</span></span>  
  
 <span data-ttu-id="63918-111">Le `Alloc` méthode doit être utilisée conjointement avec la [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) (méthode).</span><span class="sxs-lookup"><span data-stu-id="63918-111">The `Alloc` method should be used in conjunction with the [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63918-112">Spécifications</span><span class="sxs-lookup"><span data-stu-id="63918-112">Requirements</span></span>  
 <span data-ttu-id="63918-113">**Plateformes :** WindSee [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63918-113">**Platforms:** WindSee [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63918-114">**En-tête :** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="63918-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="63918-115">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63918-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63918-116">**Versions du .NET framework :**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63918-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63918-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="63918-117">See Also</span></span>  
 [<span data-ttu-id="63918-118">IMethodMalloc (Interface)</span><span class="sxs-lookup"><span data-stu-id="63918-118">IMethodMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)