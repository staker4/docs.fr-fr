---
title: SqlStreamChars.Read (Char [], Int32, Int32), méthode (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Read
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: ce89e5f757034b79d5a60a1abbd49fdb2fdf3f06
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/11/2019
ms.locfileid: "54222098"
---
# <a name="sqlstreamcharsreadchar-int32-int32-method"></a><span data-ttu-id="c7ff1-102">Méthode de SqlStreamChars.Read (Char [], Int32, Int32)</span><span class="sxs-lookup"><span data-stu-id="c7ff1-102">SqlStreamChars.Read(Char[], Int32, Int32) Method</span></span>

<span data-ttu-id="c7ff1-103">En cas de substitution dans une classe dérivée, lit le jeu de caractères suivant dans le flux d’entrée.</span><span class="sxs-lookup"><span data-stu-id="c7ff1-103">When overridden in a derived class, reads the next set of characters from the input stream.</span></span> <span data-ttu-id="c7ff1-104">L’assembly qui contient cette méthode a une relation de friend avec SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="c7ff1-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="c7ff1-105">Il est prévu pour une utilisation par SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c7ff1-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="c7ff1-106">Pour les autres bases de données, utilisez le mécanisme d’hébergement fourni par cette base de données.</span><span class="sxs-lookup"><span data-stu-id="c7ff1-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract int Read (char[] buffer, int offset, int count);
```

## <a name="parameters"></a><span data-ttu-id="c7ff1-107">Paramètres</span><span class="sxs-lookup"><span data-stu-id="c7ff1-107">Parameters</span></span>

`buffer`\
<span data-ttu-id="c7ff1-108">Un tableau de caractères à lire.</span><span class="sxs-lookup"><span data-stu-id="c7ff1-108">A char array to read.</span></span>

`offset`\
<span data-ttu-id="c7ff1-109">Un décalage relatif à l’origine.</span><span class="sxs-lookup"><span data-stu-id="c7ff1-109">An offset relative to origin.</span></span>

`count`\
<span data-ttu-id="c7ff1-110">Le nombre de caractères à lire à partir du flux actuel.</span><span class="sxs-lookup"><span data-stu-id="c7ff1-110">The number of characters to be read from the current stream.</span></span>

## <a name="returns"></a><span data-ttu-id="c7ff1-111">Returns (Retours)</span><span class="sxs-lookup"><span data-stu-id="c7ff1-111">Returns</span></span>

<xref:System.Int32>\
<span data-ttu-id="c7ff1-112">Nombre total de caractères lus dans la mémoire tampon.</span><span class="sxs-lookup"><span data-stu-id="c7ff1-112">The total number of characters read into the buffer.</span></span>

## <a name="remarks"></a><span data-ttu-id="c7ff1-113">Notes</span><span class="sxs-lookup"><span data-stu-id="c7ff1-113">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="c7ff1-114">Le `SqlStreamChars.Read` méthode est privée et qu’il n’est pas destiné à être utilisé directement dans votre code.</span><span class="sxs-lookup"><span data-stu-id="c7ff1-114">The `SqlStreamChars.Read` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="c7ff1-115">Microsoft ne prend pas en charge l’utilisation de ce champ dans une application de production en toute circonstance.</span><span class="sxs-lookup"><span data-stu-id="c7ff1-115">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="c7ff1-116">Spécifications</span><span class="sxs-lookup"><span data-stu-id="c7ff1-116">Requirements</span></span>

<span data-ttu-id="c7ff1-117">**Espace de noms :** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="c7ff1-117">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="c7ff1-118">**Assembly :** System.Data (dans System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="c7ff1-118">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="c7ff1-119">**Versions du .NET framework :** Disponible à partir de 2.0.</span><span class="sxs-lookup"><span data-stu-id="c7ff1-119">**.NET Framework versions:** Available since 2.0.</span></span>