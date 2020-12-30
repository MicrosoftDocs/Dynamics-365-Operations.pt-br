---
title: Função de ER IF
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) IF é usada.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b8733022b44f3460e34a610140fd6d584ab990c2
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686993"
---
# <a name="if-er-function"></a><span data-ttu-id="9088d-103">Função de ER IF</span><span class="sxs-lookup"><span data-stu-id="9088d-103">IF ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9088d-104">A função `IF` retorna o primeiro valor especificado se a condição especificada for atendida.</span><span class="sxs-lookup"><span data-stu-id="9088d-104">The `IF` function returns the first specified value if the specified condition is met.</span></span> <span data-ttu-id="9088d-105">Caso contrário, ele retorna o segundo valor especificado.</span><span class="sxs-lookup"><span data-stu-id="9088d-105">Otherwise, it returns the second specified value.</span></span> <span data-ttu-id="9088d-106">O valor retornado pode ser um valor de qualquer um dos tipos de dados com suporte.</span><span class="sxs-lookup"><span data-stu-id="9088d-106">The value that is returned can be a value of any of the supported data types.</span></span>

## <a name="syntax"></a><span data-ttu-id="9088d-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9088d-107">Syntax</span></span>

```vb
IF (condition, first value, second value) as any of the supported data types
```

## <a name="arguments"></a><span data-ttu-id="9088d-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="9088d-108">Arguments</span></span>

<span data-ttu-id="9088d-109">`condition`: *Booliano*</span><span class="sxs-lookup"><span data-stu-id="9088d-109">`condition`: *Boolean*</span></span>

<span data-ttu-id="9088d-110">Uma expressão condicional válida que deve ser testada.</span><span class="sxs-lookup"><span data-stu-id="9088d-110">A valid conditional expression that must be tested.</span></span>

<span data-ttu-id="9088d-111">`first value`: *Qualquer um dos tipos de dados com suporte*</span><span class="sxs-lookup"><span data-stu-id="9088d-111">`first value`: *Any of the supported data types*</span></span>

<span data-ttu-id="9088d-112">O resultado que será retornado se a condição for atendida.</span><span class="sxs-lookup"><span data-stu-id="9088d-112">The result that is returned if the condition is met.</span></span>

<span data-ttu-id="9088d-113">`second value`: *Qualquer um dos tipos de dados com suporte*</span><span class="sxs-lookup"><span data-stu-id="9088d-113">`second value`: *Any of the supported data types*</span></span>

<span data-ttu-id="9088d-114">O resultado que será retornado se a condição não for atendida.</span><span class="sxs-lookup"><span data-stu-id="9088d-114">The result that is returned if the condition isn't met.</span></span>

## <a name="return-values"></a><span data-ttu-id="9088d-115">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="9088d-115">Return values</span></span>

<span data-ttu-id="9088d-116">*Qualquer um dos tipos de dados com suporte*</span><span class="sxs-lookup"><span data-stu-id="9088d-116">*Any of the supported data types*</span></span>

<span data-ttu-id="9088d-117">O valor resultante de qualquer um dos tipos de dados com suporte.</span><span class="sxs-lookup"><span data-stu-id="9088d-117">The resulting value of any of the supported data types.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="9088d-118">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="9088d-118">Usage notes</span></span>

<span data-ttu-id="9088d-119">Os argumentos `first value` e `second value` devem ser especificados usando o mesmo tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="9088d-119">The `first value` and `second value` arguments must be specified by using the same data type.</span></span> <span data-ttu-id="9088d-120">Uma exceção é gerada no momento do design se os tipos de dados dos valores configurados não forem correspondentes.</span><span class="sxs-lookup"><span data-stu-id="9088d-120">An exception is thrown at design time if the data types of the configured values don't match.</span></span>

<span data-ttu-id="9088d-121">Se o primeiro e o segundo valor forem valores do tipo de dados *Contêiner (registro)* ou *Lista de registros*, o resultado terá somente os campos existentes nos dois valores.</span><span class="sxs-lookup"><span data-stu-id="9088d-121">If the first value and the second value are values of the *Container (record)* or *Record list* data type, the result has only the fields that exist in both values.</span></span>

## <a name="example"></a><span data-ttu-id="9088d-122">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9088d-122">Example</span></span>

<span data-ttu-id="9088d-123">`IF (1=2, "condition is met", "condition is not met")` retorna a cadeia de caracteres **"condição não atendida"**.</span><span class="sxs-lookup"><span data-stu-id="9088d-123">`IF (1=2, "condition is met", "condition is not met")` returns the string **"condition is not met"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9088d-124">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="9088d-124">Additional resources</span></span>

[<span data-ttu-id="9088d-125">Funções lógicas</span><span class="sxs-lookup"><span data-stu-id="9088d-125">Logical functions</span></span>](er-functions-category-logical.md)
