---
title: ISymUnmanagedVariable::GetAddressField1, méthode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField1
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField1
helpviewer_keywords:
- GetAddressField1 method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressField1 method [.NET Framework debugging]
ms.assetid: 25788ed1-0ce3-4b97-96fc-88f8997812a3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d37de6dee14ad2c24c21a2d1a97d112fd0b9f3d7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706402"
---
# <a name="isymunmanagedvariablegetaddressfield1-method"></a>ISymUnmanagedVariable::GetAddressField1, méthode
Obtient le premier champ d’adresse pour cette variable. Sa signification dépend du type d’adresse.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetAddressField1(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pRetVal`  
 [out] Un pointeur vers un `ULONG32` qui reçoit le premier champ d’adresse.  
  
## <a name="return-value"></a>Valeur de retour  
 S_OK si la méthode réussit ; Sinon, E_FAIL ou un autre code d’erreur.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Voir aussi
- [ISymUnmanagedVariable, interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [GetAddressField2, méthode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)
- [GetAddressField3, méthode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)
- [GetAddressKind, méthode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
