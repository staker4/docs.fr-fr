---
title: "IHostAssemblyStore::ProvideAssembly, méthode"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostAssemblyStore.ProvideAssembly
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostAssemblyStore::ProvideAssembly
helpviewer_keywords:
- ProvideAssembly method [.NET Framework hosting]
- IHostAssemblyStore::ProvideAssembly method [.NET Framework hosting]
ms.assetid: 625c3dd5-a3f0-442c-adde-310dadbb5054
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cda88c2e93b4f90844ad3dec2ed0fa4366dba6d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostassemblystoreprovideassembly-method"></a><span data-ttu-id="a77ee-102">IHostAssemblyStore::ProvideAssembly, méthode</span><span class="sxs-lookup"><span data-stu-id="a77ee-102">IHostAssemblyStore::ProvideAssembly Method</span></span>
<span data-ttu-id="a77ee-103">Obtient une référence à un assembly qui n’est pas référencé par le [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) qui est retourné à partir de [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span><span class="sxs-lookup"><span data-stu-id="a77ee-103">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that is returned from [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span> <span data-ttu-id="a77ee-104">Le common language runtime (CLR) appelle `ProvideAssembly` pour chaque assembly qui n’apparaît pas dans la liste.</span><span class="sxs-lookup"><span data-stu-id="a77ee-104">The common language runtime (CLR) calls `ProvideAssembly` for each assembly that does not appear in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a77ee-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="a77ee-105">Syntax</span></span>  
  
```  
HRESULT ProvideAssembly (  
    [in]  AssemblyBindInfo *pBindInfo,  
    [out] UINT64           *pAssemblyId,  
    [out] UINT64           *pHostContext,  
    [out] IStream          **ppStmAssemblyImage,  
    [out] IStream          **ppStmPDB  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a77ee-106">Paramètres</span><span class="sxs-lookup"><span data-stu-id="a77ee-106">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="a77ee-107">[in] Un pointeur vers un [AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) instance que l’hôte utilise pour déterminer certaines caractéristiques de liaison, y compris la présence ou l’absence de toute stratégie de contrôle de version et l’assembly à lier.</span><span class="sxs-lookup"><span data-stu-id="a77ee-107">[in] A pointer to an [AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) instance that the host uses to determine certain bind characteristics, including the presence or absence of any versioning policy, and which assembly to bind to.</span></span>  
  
 `pAssemblyId`  
 <span data-ttu-id="a77ee-108">[out] Un pointeur vers un identificateur unique pour l’assembly demandé pour ce `IStream`.</span><span class="sxs-lookup"><span data-stu-id="a77ee-108">[out] A pointer to a unique identifier for the requested assembly for this `IStream`.</span></span>  
  
 `pHostContext`  
 <span data-ttu-id="a77ee-109">[out] Un pointeur vers les données spécifiques à l’hôte qui sont utilisés pour déterminer la preuve de l’assembly demandé sans avoir besoin d’une plateforme de l’appel.</span><span class="sxs-lookup"><span data-stu-id="a77ee-109">[out] A pointer to host-specific data that is used to determine the evidence of the requested assembly without the need of a platform invoke call.</span></span> <span data-ttu-id="a77ee-110">`pHostContext`correspond à la <xref:System.Reflection.Assembly.HostContext%2A> propriété managé <xref:System.Reflection.Assembly> classe.</span><span class="sxs-lookup"><span data-stu-id="a77ee-110">`pHostContext` corresponds to the <xref:System.Reflection.Assembly.HostContext%2A> property of the managed <xref:System.Reflection.Assembly> class.</span></span>  
  
 `ppStmAssemblyImage`  
 <span data-ttu-id="a77ee-111">[out] Un pointeur vers l’adresse d’un `IStream` qui contient l’image exécutable portable (PE) à charger, ou null si l’assembly est introuvable.</span><span class="sxs-lookup"><span data-stu-id="a77ee-111">[out] A pointer to the address of an `IStream` that contains the portable executable (PE) image to be loaded, or null if the assembly could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="a77ee-112">[out] Un pointeur vers l’adresse d’un `IStream` qui contient les informations de débogage (PDB) de programme, ou null si le fichier .pdb est introuvable.</span><span class="sxs-lookup"><span data-stu-id="a77ee-112">[out] A pointer to the address of an `IStream` that contains the program debug (PDB) information, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a77ee-113">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="a77ee-113">Return Value</span></span>  
  
|<span data-ttu-id="a77ee-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a77ee-114">HRESULT</span></span>|<span data-ttu-id="a77ee-115">Description</span><span class="sxs-lookup"><span data-stu-id="a77ee-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a77ee-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="a77ee-116">S_OK</span></span>|<span data-ttu-id="a77ee-117">`ProvideAssembly`retourné avec succès.</span><span class="sxs-lookup"><span data-stu-id="a77ee-117">`ProvideAssembly` returned successfully.</span></span>|  
|<span data-ttu-id="a77ee-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a77ee-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a77ee-119">Le CLR n’a pas été chargé dans un processus ou le CLR est dans un état dans lequel il ne peut pas exécuter du code managé ou traiter l’appel avec succès.</span><span class="sxs-lookup"><span data-stu-id="a77ee-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a77ee-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a77ee-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a77ee-121">L’appel a expiré.</span><span class="sxs-lookup"><span data-stu-id="a77ee-121">The call timed out.</span></span>|  
|<span data-ttu-id="a77ee-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a77ee-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a77ee-123">L’appelant ne possède pas le verrou.</span><span class="sxs-lookup"><span data-stu-id="a77ee-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a77ee-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a77ee-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a77ee-125">Un événement a été annulé alors qu’un thread bloqué ou une fibre l’attendait.</span><span class="sxs-lookup"><span data-stu-id="a77ee-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a77ee-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a77ee-126">E_FAIL</span></span>|<span data-ttu-id="a77ee-127">Une défaillance grave et inconnue s’est produite.</span><span class="sxs-lookup"><span data-stu-id="a77ee-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a77ee-128">Lorsqu’une méthode retourne E_FAIL, le CLR n’est plus utilisable dans le processus.</span><span class="sxs-lookup"><span data-stu-id="a77ee-128">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a77ee-129">Les appels suivants aux méthodes d’hébergement retournent HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a77ee-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a77ee-130">COR_E_FILENOTFOUND (0 X 80070002)</span><span class="sxs-lookup"><span data-stu-id="a77ee-130">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="a77ee-131">L’assembly demandé n’a pas pu être localisé.</span><span class="sxs-lookup"><span data-stu-id="a77ee-131">The requested assembly could not be located.</span></span>|  
|<span data-ttu-id="a77ee-132">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="a77ee-132">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="a77ee-133">La taille de mémoire tampon spécifiée par `pAssemblyId` n’est pas suffisamment grande pour contenir l’identificateur que l’hôte souhaite retourner.</span><span class="sxs-lookup"><span data-stu-id="a77ee-133">The buffer size specified by `pAssemblyId` is not large enough to hold the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a77ee-134">Remarques</span><span class="sxs-lookup"><span data-stu-id="a77ee-134">Remarks</span></span>  
 <span data-ttu-id="a77ee-135">La valeur d’identité retournée pour `pAssemblyId` est spécifiée par l’hôte.</span><span class="sxs-lookup"><span data-stu-id="a77ee-135">The identity value returned for `pAssemblyId` is specified by the host.</span></span> <span data-ttu-id="a77ee-136">Les identificateurs doivent être uniques au sein de la durée de vie d’un processus.</span><span class="sxs-lookup"><span data-stu-id="a77ee-136">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="a77ee-137">Le CLR utilise cette valeur comme identificateur unique pour le flux.</span><span class="sxs-lookup"><span data-stu-id="a77ee-137">The CLR uses this value as a unique identifier for the stream.</span></span> <span data-ttu-id="a77ee-138">Il vérifie chaque valeur sur les valeurs de `pAssemblyId` retourné par d’autres appels à `ProvideAssembly`.</span><span class="sxs-lookup"><span data-stu-id="a77ee-138">It checks each value against the values for `pAssemblyId` returned by other calls to `ProvideAssembly`.</span></span> <span data-ttu-id="a77ee-139">Si l’hôte retourne la même `pAssemblyId` valeur d’un autre `IStream`, le CLR vérifie si le contenu de ce flux a déjà été mappé.</span><span class="sxs-lookup"><span data-stu-id="a77ee-139">If the host returns the same `pAssemblyId` value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="a77ee-140">Dans ce cas, le runtime charge la copie existante de l’image au lieu de mapper une nouvelle.</span><span class="sxs-lookup"><span data-stu-id="a77ee-140">If so, the runtime loads the existing copy of the image instead of mapping a new one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a77ee-141">Spécifications</span><span class="sxs-lookup"><span data-stu-id="a77ee-141">Requirements</span></span>  
 <span data-ttu-id="a77ee-142">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a77ee-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a77ee-143">**En-tête :** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a77ee-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a77ee-144">**Bibliothèque :** inclus en tant que ressource dans MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a77ee-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a77ee-145">**Versions du .NET framework :**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a77ee-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a77ee-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a77ee-146">See Also</span></span>  
 [<span data-ttu-id="a77ee-147">ICLRAssemblyReferenceList (Interface)</span><span class="sxs-lookup"><span data-stu-id="a77ee-147">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="a77ee-148">IHostAssemblyManager (Interface)</span><span class="sxs-lookup"><span data-stu-id="a77ee-148">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="a77ee-149">IHostAssemblyStore (Interface)</span><span class="sxs-lookup"><span data-stu-id="a77ee-149">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)