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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b29302ffe534f2439519e57c6a6b8c94c1df8d62
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917134"
---
# <span data-ttu-id="659ef-103"><a name="IF">Função de ER IF</a></span><span class="sxs-lookup"><span data-stu-id="659ef-103"><a name="IF">IF ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="659ef-104">A função `IF` retorna o primeiro valor especificado se a condição especificada for atendida.</span><span class="sxs-lookup"><span data-stu-id="659ef-104">The `IF` function returns the first specified value if the specified condition is met.</span></span> <span data-ttu-id="659ef-105">Caso contrário, ele retorna o segundo valor especificado.</span><span class="sxs-lookup"><span data-stu-id="659ef-105">Otherwise, it returns the second specified value.</span></span> <span data-ttu-id="659ef-106">O valor retornado pode ser um valor de qualquer um dos tipos de dados com suporte.</span><span class="sxs-lookup"><span data-stu-id="659ef-106">The value that is returned can be a value of any of the supported data types.</span></span>

## <a name="syntax"></a><span data-ttu-id="659ef-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="659ef-107">Syntax</span></span>

```
IF (condition, first value, second value) as any of the supported data types
```

## <a name="arguments"></a><span data-ttu-id="659ef-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="659ef-108">Arguments</span></span>

<span data-ttu-id="659ef-109">`condition`: *Booliano*</span><span class="sxs-lookup"><span data-stu-id="659ef-109">`condition`: *Boolean*</span></span>

<span data-ttu-id="659ef-110">Uma expressão condicional válida que deve ser testada.</span><span class="sxs-lookup"><span data-stu-id="659ef-110">A valid conditional expression that must be tested.</span></span>

<span data-ttu-id="659ef-111">`first value`: *Qualquer um dos tipos de dados com suporte*</span><span class="sxs-lookup"><span data-stu-id="659ef-111">`first value`: *Any of the supported data types*</span></span>

<span data-ttu-id="659ef-112">O resultado que será retornado se a condição for atendida.</span><span class="sxs-lookup"><span data-stu-id="659ef-112">The result that is returned if the condition is met.</span></span>

<span data-ttu-id="659ef-113">`second value`: *Qualquer um dos tipos de dados com suporte*</span><span class="sxs-lookup"><span data-stu-id="659ef-113">`second value`: *Any of the supported data types*</span></span>

<span data-ttu-id="659ef-114">O resultado que será retornado se a condição não for atendida.</span><span class="sxs-lookup"><span data-stu-id="659ef-114">The result that is returned if the condition isn't met.</span></span>

## <a name="return-values"></a><span data-ttu-id="659ef-115">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="659ef-115">Return values</span></span>

<span data-ttu-id="659ef-116">*Qualquer um dos tipos de dados com suporte*</span><span class="sxs-lookup"><span data-stu-id="659ef-116">*Any of the supported data types*</span></span>

<span data-ttu-id="659ef-117">O valor resultante de qualquer um dos tipos de dados com suporte.</span><span class="sxs-lookup"><span data-stu-id="659ef-117">The resulting value of any of the supported data types.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="659ef-118">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="659ef-118">Usage notes</span></span>

<span data-ttu-id="659ef-119">Os argumentos `first value` e `second value` devem ser especificados usando o mesmo tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="659ef-119">The `first value` and `second value` arguments must be specified by using the same data type.</span></span> <span data-ttu-id="659ef-120">Uma exceção é gerada no momento do design se os tipos de dados dos valores configurados não forem correspondentes.</span><span class="sxs-lookup"><span data-stu-id="659ef-120">An exception is thrown at design time if the data types of the configured values don't match.</span></span>

<span data-ttu-id="659ef-121">Se o primeiro e o segundo valor forem valores do tipo de dados *Contêiner (registro)* ou *Lista de registros*, o resultado terá somente os campos existentes nos dois valores.</span><span class="sxs-lookup"><span data-stu-id="659ef-121">If the first value and the second value are values of the *Container (record)* or *Record list* data type, the result has only the fields that exist in both values.</span></span>

## <a name="example"></a><span data-ttu-id="659ef-122">Exemplo</span><span class="sxs-lookup"><span data-stu-id="659ef-122">Example</span></span>

<span data-ttu-id="659ef-123">`IF (1=2, "condition is met", "condition is not met")` retorna a cadeia de caracteres **"condição não atendida"**.</span><span class="sxs-lookup"><span data-stu-id="659ef-123">`IF (1=2, "condition is met", "condition is not met")` returns the string **"condition is not met"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="659ef-124">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="659ef-124">Additional resources</span></span>

[<span data-ttu-id="659ef-125">Funções lógicas</span><span class="sxs-lookup"><span data-stu-id="659ef-125">Logical functions</span></span>](er-functions-category-logical.md)
