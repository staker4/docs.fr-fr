---
title: Propriété SqlStreamChars.CanSeek (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.CanSeek
- System.Data.SqlTypes.SqlStreamChars.get_CanSeek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: bde4764af9d0160997dc202f722a12393cfa59c1
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55826848"
---
# <a name="sqlstreamcharscanseek-property"></a>Propriété de SqlStreamChars.CanSeek

En cas de substitution dans une classe dérivée, obtient une valeur qui indique si le flux actuel prend en charge l’opération de recherche. L’assembly qui contient cette propriété a une relation de friend avec SQLAccess.dll. Il est prévu pour une utilisation par SQL Server. Pour les autres bases de données, utilisez le mécanisme d’hébergement fourni par cette base de données.

```csharp
public abstract bool CanSeek { get; }
```

## <a name="property-value"></a>Valeur de propriété

<xref:System.Boolean>\
`true` Si le flux actuel prend en charge l’opération de recherche ; Sinon, `false`.

## <a name="remarks"></a>Notes

> [!WARNING]
> Le `SqlStreamChars.CanSeek` propriété est privée et qu’il n’est pas destinée à être utilisé directement dans votre code.
>
> Microsoft ne prend pas en charge l’utilisation de ce champ dans une application de production en toute circonstance.

## <a name="requirements"></a>Spécifications

**Espace de noms :** <xref:System.Data.SqlTypes>

**Assembly :** System.Data (dans System.Data.dll)

**Versions du .NET framework :** Disponible à partir de 2.0.