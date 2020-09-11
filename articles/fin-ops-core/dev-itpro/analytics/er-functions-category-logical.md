---
title: Lista de funções ER na categoria lógica
description: Este tópico fornece informações sobre as funções lógicas que são compatíveis no relatório eletrônico (ER).
author: NickSelin
manager: kfend
ms.date: 08/19/2020
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
ms.openlocfilehash: e622778c60646e5cc84cd6e23a5d4954a0fe0bb3
ms.sourcegitcommit: 38ad6f791c3d5688a5dc201a234ba89f155f7f03
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/19/2020
ms.locfileid: "3705086"
---
# <a name="list-of-er-functions-in-the-logical-category"></a><span data-ttu-id="92566-103">Lista de funções ER na categoria lógica</span><span class="sxs-lookup"><span data-stu-id="92566-103">List of ER functions in the logical category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="92566-104">As funções lógicas relatório eletrônico (ER) podem ser usadas para trabalhar com valores lógicos a fim de executar mais de uma comparação em uma única expressão ou testar várias condições.</span><span class="sxs-lookup"><span data-stu-id="92566-104">Electronic reporting (ER) logical functions can be used to work with logical values to perform more than one comparison in a single expression or test multiple conditions.</span></span> <span data-ttu-id="92566-105">Este tópico fornece um resumo dessas funções.</span><span class="sxs-lookup"><span data-stu-id="92566-105">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="92566-106">Lista de funções com suporte</span><span class="sxs-lookup"><span data-stu-id="92566-106">List of supported functions</span></span>

| <span data-ttu-id="92566-107">Função</span><span class="sxs-lookup"><span data-stu-id="92566-107">Function</span></span> | <span data-ttu-id="92566-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="92566-108">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="92566-109">E</span><span class="sxs-lookup"><span data-stu-id="92566-109">And</span></span>](er-functions-logical-and.md)                       | <span data-ttu-id="92566-110">Essa função retorna um valor *Booliano* de **TRUE** se todas as condições especificadas forem verdadeiras.</span><span class="sxs-lookup"><span data-stu-id="92566-110">This function returns a *Boolean* value of **TRUE** if all the specified conditions are true.</span></span> <span data-ttu-id="92566-111">Caso contrário, ela retorna um valor *Booliano* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="92566-111">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> |
| [<span data-ttu-id="92566-112">Caixa</span><span class="sxs-lookup"><span data-stu-id="92566-112">Case</span></span>](er-functions-logical-case.md)                     | <span data-ttu-id="92566-113">Essa função avalia o valor da expressão especificada em relação às opções alternativas especificadas e retorna o resultado da primeira opção igual ao valor dessa expressão.</span><span class="sxs-lookup"><span data-stu-id="92566-113">This function evaluates the value of the specified expression against the specified alternative options and returns the result of the first option that equals the value of the specified expression.</span></span> <span data-ttu-id="92566-114">Caso contrário, ela retorna um resultado padrão opcional, se um resultado padrão for especificado como o último argumento da função chamada não precedida por uma opção.</span><span class="sxs-lookup"><span data-stu-id="92566-114">Otherwise, it returns an optional default result, if a default result is specified as the last argument of the called function that isn't preceded by an option.</span></span> <span data-ttu-id="92566-115">O valor retornado pode ser um valor de qualquer um dos tipos de dados com suporte.</span><span class="sxs-lookup"><span data-stu-id="92566-115">The value that is returned can be a value of any of the supported data types.</span></span> |
| [<span data-ttu-id="92566-116">Se</span><span class="sxs-lookup"><span data-stu-id="92566-116">If</span></span>](er-functions-logical-if.md)                         | <span data-ttu-id="92566-117">Essa função retorna o primeiro valor especificado se a condição especificada for atendida.</span><span class="sxs-lookup"><span data-stu-id="92566-117">This function returns the first specified value if the specified condition is met.</span></span> <span data-ttu-id="92566-118">Caso contrário, ele retorna o segundo valor especificado.</span><span class="sxs-lookup"><span data-stu-id="92566-118">Otherwise, it returns the second specified value.</span></span> <span data-ttu-id="92566-119">O valor retornado pode ser um valor de qualquer um dos tipos de dados com suporte.</span><span class="sxs-lookup"><span data-stu-id="92566-119">The value that is returned can be a value of any of the supported data types.</span></span> |
| [<span data-ttu-id="92566-120">Não</span><span class="sxs-lookup"><span data-stu-id="92566-120">Not</span></span>](er-functions-logical-not.md)                       | <span data-ttu-id="92566-121">Essa função retorna o valor lógico revertido da condição especificada como um valor *Booliano*.</span><span class="sxs-lookup"><span data-stu-id="92566-121">This function returns the reversed logical value of the specified condition as a *Boolean* value.</span></span> |
| [<span data-ttu-id="92566-122">Or</span><span class="sxs-lookup"><span data-stu-id="92566-122">Or</span></span>](er-functions-logical-or.md)                         | <span data-ttu-id="92566-123">Essa função retorna um valor *Booliano* de **FALSE** se todas as condições especificadas forem falsas.</span><span class="sxs-lookup"><span data-stu-id="92566-123">This function returns a *Boolean* value of **FALSE** if all the specified conditions are false.</span></span> <span data-ttu-id="92566-124">Se qualquer condição especificada for verdade, a função retorna um valor *Booliano* como **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="92566-124">If any specified condition is true, the function returns a *Boolean* value of **TRUE**.</span></span> |
| [<span data-ttu-id="92566-125">ValueIn</span><span class="sxs-lookup"><span data-stu-id="92566-125">ValueIn</span></span>](er-functions-logical-valuein.md)               | <span data-ttu-id="92566-126">Essa função determina se a entrada especificada corresponde a algum valor de um item especificado na lista especificada.</span><span class="sxs-lookup"><span data-stu-id="92566-126">This function determines whether the specified input matches any value of a specified item in the specified list.</span></span> <span data-ttu-id="92566-127">Ela retorna um valor *Booliano* de **TRUE** se a entrada especificada corresponder ao resultado da execução da expressão especificada para pelo menos um registro da lista especificada.</span><span class="sxs-lookup"><span data-stu-id="92566-127">It returns a *Boolean* value of **TRUE** if the specified input matches the result of running the specified expression for at least one record of the specified list.</span></span> <span data-ttu-id="92566-128">Caso contrário, ela retorna um valor *Booliano* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="92566-128">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> |
| [<span data-ttu-id="92566-129">ValueInLarge</span><span class="sxs-lookup"><span data-stu-id="92566-129">ValueInLarge</span></span>](er-functions-logical-valueinlarge.md)     | <span data-ttu-id="92566-130">Esta função determina se a entrada especificada do tipo *Int64* ou *Inteiro* corresponde a algum valor de um item especificado na lista especificada.</span><span class="sxs-lookup"><span data-stu-id="92566-130">This function determines whether the specified input of the *Int64* or *Integer* type matches any value of a specified item in the specified list.</span></span> <span data-ttu-id="92566-131">Ela retorna um valor *Booliano* de **TRUE** se a entrada especificada corresponder ao resultado da execução da expressão especificada para pelo menos um registro da lista especificada.</span><span class="sxs-lookup"><span data-stu-id="92566-131">It returns a *Boolean* value of **TRUE** if the specified input matches the result of running the specified expression for at least one record of the specified list.</span></span> <span data-ttu-id="92566-132">Caso contrário, ela retorna um valor *Booliano* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="92566-132">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> |


## <a name="additional-resources"></a><span data-ttu-id="92566-133">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="92566-133">Additional resources</span></span>

[<span data-ttu-id="92566-134">Visão geral do Relatório Eletrônico</span><span class="sxs-lookup"><span data-stu-id="92566-134">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="92566-135">Designer de fórmulas no Relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="92566-135">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="92566-136">Linguagem da fórmula de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="92566-136">Electronic reporting formula language</span></span>](er-formula-language.md)
