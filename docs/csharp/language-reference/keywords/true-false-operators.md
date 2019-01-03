---
title: Opérateurs true et false - Référence C#
ms.custom: seodec18
ms.date: 12/10/2018
helpviewer_keywords:
- false operator [C#]
- true operator [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
ms.openlocfilehash: 0a75566fdb6222157ecda12a50fd78e22f92fcb4
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245730"
---
# <a name="true-and-false-operators-c-reference"></a><span data-ttu-id="6f4df-102">Opérateurs true et false (Référence C#)</span><span class="sxs-lookup"><span data-stu-id="6f4df-102">true and false operators (C# Reference)</span></span>

<span data-ttu-id="6f4df-103">L’opérateur `true` retourne la valeur [bool](bool.md) `true` pour indiquer qu’un opérande est true.</span><span class="sxs-lookup"><span data-stu-id="6f4df-103">The `true` operator returns the [bool](bool.md) value `true` to indicate that an operand is definitely true.</span></span> <span data-ttu-id="6f4df-104">L’opérateur `false` retourne la valeur `bool` `true` pour indiquer qu’un opérande est false.</span><span class="sxs-lookup"><span data-stu-id="6f4df-104">The `false` operator returns the `bool` value `true` to indicate that an operand is definitely false.</span></span> <span data-ttu-id="6f4df-105">Les opérateurs `true` et `false` ne sont pas forcément complémentaires.</span><span class="sxs-lookup"><span data-stu-id="6f4df-105">The `true` and `false` operators are not guaranteed to complement each other.</span></span> <span data-ttu-id="6f4df-106">Autrement dit, les opérateurs `true` et `false` peuvent retourner la valeur `bool` `false` pour le même opérande.</span><span class="sxs-lookup"><span data-stu-id="6f4df-106">That is, both the `true` and `false` operator might return the `bool` value `false` for the same operand.</span></span> <span data-ttu-id="6f4df-107">Si un type définit un des deux opérateurs, il doit aussi définir un autre opérateur.</span><span class="sxs-lookup"><span data-stu-id="6f4df-107">If a type defines one of the two operators, it must also define another operator.</span></span>

<span data-ttu-id="6f4df-108">Si un type avec les opérateurs `true` et `false` définis [surcharge](operator.md) [l’opérateur OR logique](../operators/or-operator.md) `|` ou [l’opérateur AND logique](../operators/and-operator.md) `&` d’une façon, [l’opérateur OR logique conditionnel](../operators/conditional-or-operator.md) `||` ou [l’opérateur AND logique conditionnel](../operators/conditional-and-operator.md) `&&`, respectivement, peut être évalué pour les opérandes de ce type.</span><span class="sxs-lookup"><span data-stu-id="6f4df-108">If a type with the defined `true` and `false` operators [overloads](operator.md) the [logical OR operator](../operators/or-operator.md) `|` or the [logical AND operator](../operators/and-operator.md) `&` in a certain way, the [conditional logical OR operator](../operators/conditional-or-operator.md) `||` or [conditional logical AND operator](../operators/conditional-and-operator.md) `&&`, respectively, can be evaluated for the operands of that type.</span></span> <span data-ttu-id="6f4df-109">Pour plus d’informations, consultez la section [Opérateurs logiques conditionnels définis par l’utilisateur](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) de la [spécification du langage C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="6f4df-109">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

<span data-ttu-id="6f4df-110">Un type avec l’opérateur `true` défini peut être le type de résultat d’une expression conditionnelle de contrôle dans les instructions [if](if-else.md), [do](do.md), [while](while.md) et [for](for.md) et dans [l’opérateur conditionnel `?:`](../operators/conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="6f4df-110">A type with the defined `true` operator can be the type of a result of a controlling conditional expression in the [if](if-else.md), [do](do.md), [while](while.md), and [for](for.md) statements and in the [conditional operator `?:`](../operators/conditional-operator.md).</span></span> <span data-ttu-id="6f4df-111">Pour plus d’informations, voir la section [Expressions booléennes](~/_csharplang/spec/expressions.md#boolean-expressions) de la [spécification du langage C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="6f4df-111">For more information, see the [Boolean expressions](~/_csharplang/spec/expressions.md#boolean-expressions) section of the [C# language specification](../language-specification/index.md).</span></span>

> [!TIP]
> <span data-ttu-id="6f4df-112">Utilisez le type `bool?` si vous voulez suivre une logique à trois valeurs, par exemple, lorsque vous travaillez avec des bases de données qui acceptent un type de logique à trois valeurs.</span><span class="sxs-lookup"><span data-stu-id="6f4df-112">Use the `bool?` type, if you need to support the three-valued logic, for example, when you work with databases that support a three-valued logical type.</span></span> <span data-ttu-id="6f4df-113">Pour plus d’informations, voir la section [Type bool?](../../programming-guide/nullable-types/using-nullable-types.md#the-bool-type) de l’article [Utiliser des types Nullable](../../programming-guide/nullable-types/using-nullable-types.md).</span><span class="sxs-lookup"><span data-stu-id="6f4df-113">For more information, see [The bool? type](../../programming-guide/nullable-types/using-nullable-types.md#the-bool-type) section of the [Using nullable types](../../programming-guide/nullable-types/using-nullable-types.md) article.</span></span>

<span data-ttu-id="6f4df-114">L’exemple suivant présente le type qui définit les opérateurs `true` et `false`.</span><span class="sxs-lookup"><span data-stu-id="6f4df-114">The following example presents the type that defines both `true` and `false` operators.</span></span> <span data-ttu-id="6f4df-115">Par ailleurs, il surcharge l’opérateur AND logique `&` de sorte que l’opérateur `&&` peut aussi être évalué pour les opérandes de ce type.</span><span class="sxs-lookup"><span data-stu-id="6f4df-115">Moreover, it overloads the logical AND operator `&` in such a way that the operator `&&` also can be evaluated for the operands of that type.</span></span>

[!code-csharp-interactive[true and false operators example](~/samples/snippets/csharp/keywords/TrueFalseOperatorsExample.cs)]

<span data-ttu-id="6f4df-116">Remarquez le comportement de court-circuit de l’opérateur `&&`.</span><span class="sxs-lookup"><span data-stu-id="6f4df-116">Notice the short-circuiting behavior of the `&&` operator.</span></span> <span data-ttu-id="6f4df-117">Lorsque la méthode `GetFuelLaunchStatus` retourne `LaunchStatus.Red`, le second opérande de l’opérateur `&&` n’est pas évalué.</span><span class="sxs-lookup"><span data-stu-id="6f4df-117">When the `GetFuelLaunchStatus` method returns `LaunchStatus.Red`, the second operand of the `&&` operator is not evaluated.</span></span> <span data-ttu-id="6f4df-118">En effet, `LaunchStatus.Red` est false.</span><span class="sxs-lookup"><span data-stu-id="6f4df-118">That is because `LaunchStatus.Red` is definitely false.</span></span> <span data-ttu-id="6f4df-119">Le résultat du AND logique ne dépend donc pas la valeur du second opérande.</span><span class="sxs-lookup"><span data-stu-id="6f4df-119">Then the result of the logical AND doesn't depend on the value of the second operand.</span></span> <span data-ttu-id="6f4df-120">Voici la sortie de l’exemple :</span><span class="sxs-lookup"><span data-stu-id="6f4df-120">The output of the example is as follows:</span></span>

```console
Getting fuel launch status...
Wait!
```

## <a name="see-also"></a><span data-ttu-id="6f4df-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6f4df-121">See also</span></span>

- [<span data-ttu-id="6f4df-122">Référence C#</span><span class="sxs-lookup"><span data-stu-id="6f4df-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="6f4df-123">Guide de programmation C#</span><span class="sxs-lookup"><span data-stu-id="6f4df-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="6f4df-124">Mots clés C#</span><span class="sxs-lookup"><span data-stu-id="6f4df-124">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="6f4df-125">Opérateurs C#</span><span class="sxs-lookup"><span data-stu-id="6f4df-125">C# Operators</span></span>](../operators/index.md)
- [<span data-ttu-id="6f4df-126">`true`, littéral</span><span class="sxs-lookup"><span data-stu-id="6f4df-126">`true` literal</span></span>](true-literal.md)
- [<span data-ttu-id="6f4df-127">`false`, littéral</span><span class="sxs-lookup"><span data-stu-id="6f4df-127">`false` literal</span></span>](false-literal.md)