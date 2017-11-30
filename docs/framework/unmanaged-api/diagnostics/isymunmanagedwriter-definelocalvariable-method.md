---
title: "ISymUnmanagedWriter::DefineLocalVariable, méthode"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.DefineLocalVariable
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::DefineLocalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineLocalVariable method [.NET Framework debugging]
- DefineLocalVariable method [.NET Framework debugging]
ms.assetid: 6fab8a58-3883-490f-8b27-64042c90f104
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e454aa2c2dd8ceb8f8dbbc03bdd1e70e8a800de2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriterdefinelocalvariable-method"></a><span data-ttu-id="b7f2b-102">ISymUnmanagedWriter::DefineLocalVariable, méthode</span><span class="sxs-lookup"><span data-stu-id="b7f2b-102">ISymUnmanagedWriter::DefineLocalVariable Method</span></span>
<span data-ttu-id="b7f2b-103">Définit une variable unique dans la portée lexicale actuelle.</span><span class="sxs-lookup"><span data-stu-id="b7f2b-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="b7f2b-104">Cette méthode peut être appelée plusieurs fois pour une variable du même nom qui a plusieurs dossiers de base dans une étendue.</span><span class="sxs-lookup"><span data-stu-id="b7f2b-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="b7f2b-105">Dans ce cas, toutefois, les valeurs de la `startOffset` et `endOffset` paramètres ne doivent pas se chevaucher.</span><span class="sxs-lookup"><span data-stu-id="b7f2b-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7f2b-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="b7f2b-106">Syntax</span></span>  
  
```  
HRESULT DefineLocalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b7f2b-107">Paramètres</span><span class="sxs-lookup"><span data-stu-id="b7f2b-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="b7f2b-108">[in] Un pointeur vers un `WCHAR` qui définit le nom de variable locale.</span><span class="sxs-lookup"><span data-stu-id="b7f2b-108">[in] A pointer to a `WCHAR` that defines the local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="b7f2b-109">[in] Attributs de la variables locale.</span><span class="sxs-lookup"><span data-stu-id="b7f2b-109">[in] The local variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="b7f2b-110">[in] A `ULONG32` qui indique la taille, en octets, de la `signature` mémoire tampon.</span><span class="sxs-lookup"><span data-stu-id="b7f2b-110">[in] A `ULONG32` that indicates the size, in bytes, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="b7f2b-111">[in] La signature de variable locale.</span><span class="sxs-lookup"><span data-stu-id="b7f2b-111">[in] The local variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="b7f2b-112">[in] Le type d’adresse.</span><span class="sxs-lookup"><span data-stu-id="b7f2b-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="b7f2b-113">[in] La première adresse de la spécification du paramètre.</span><span class="sxs-lookup"><span data-stu-id="b7f2b-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="b7f2b-114">[in] La deuxième adresse de la spécification du paramètre.</span><span class="sxs-lookup"><span data-stu-id="b7f2b-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="b7f2b-115">[in] Troisième adresse de la spécification du paramètre.</span><span class="sxs-lookup"><span data-stu-id="b7f2b-115">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="b7f2b-116">[in] Offset de début de la variable.</span><span class="sxs-lookup"><span data-stu-id="b7f2b-116">[in] The start offset for the variable.</span></span> <span data-ttu-id="b7f2b-117">Ce paramètre est optionnel.</span><span class="sxs-lookup"><span data-stu-id="b7f2b-117">This parameter is optional.</span></span> <span data-ttu-id="b7f2b-118">Si la valeur est 0, ce paramètre est ignoré et la variable est définie dans la portée entière.</span><span class="sxs-lookup"><span data-stu-id="b7f2b-118">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="b7f2b-119">Si elle est une valeur différente de zéro, la variable est comprise entre les offsets de la portée actuelle.</span><span class="sxs-lookup"><span data-stu-id="b7f2b-119">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="b7f2b-120">[in] Offset de fin de la variable.</span><span class="sxs-lookup"><span data-stu-id="b7f2b-120">[in] The end offset for the variable.</span></span> <span data-ttu-id="b7f2b-121">Ce paramètre est optionnel.</span><span class="sxs-lookup"><span data-stu-id="b7f2b-121">This parameter is optional.</span></span> <span data-ttu-id="b7f2b-122">Si la valeur est 0, ce paramètre est ignoré et la variable est définie dans la portée entière.</span><span class="sxs-lookup"><span data-stu-id="b7f2b-122">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="b7f2b-123">Si elle est une valeur différente de zéro, la variable est comprise entre les offsets de la portée actuelle.</span><span class="sxs-lookup"><span data-stu-id="b7f2b-123">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b7f2b-124">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="b7f2b-124">Return Value</span></span>  
 <span data-ttu-id="b7f2b-125">S_OK si la méthode réussit ; Sinon, E_FAIL ou un autre code d’erreur.</span><span class="sxs-lookup"><span data-stu-id="b7f2b-125">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7f2b-126">Spécifications</span><span class="sxs-lookup"><span data-stu-id="b7f2b-126">Requirements</span></span>  
 <span data-ttu-id="b7f2b-127">**En-tête :** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b7f2b-127">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7f2b-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b7f2b-128">See Also</span></span>  
 [<span data-ttu-id="b7f2b-129">ISymUnmanagedWriter (Interface)</span><span class="sxs-lookup"><span data-stu-id="b7f2b-129">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="b7f2b-130">DefineGlobalVariable (méthode)</span><span class="sxs-lookup"><span data-stu-id="b7f2b-130">DefineGlobalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)  
 [<span data-ttu-id="b7f2b-131">DefineLocalVariable2 (méthode)</span><span class="sxs-lookup"><span data-stu-id="b7f2b-131">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)