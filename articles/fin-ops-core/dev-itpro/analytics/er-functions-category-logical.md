---
title: Lista de funções ER na categoria lógica
description: Este tópico fornece informações sobre as funções lógicas que são compatíveis no relatório eletrônico (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 408b3c5ec37b24e0ccf6e368012a936701eedf0f
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916628"
---
# <a name="list-of-er-functions-in-the-logical-category"></a><span data-ttu-id="ccce7-103">Lista de funções ER na categoria lógica</span><span class="sxs-lookup"><span data-stu-id="ccce7-103">List of ER functions in the logical category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ccce7-104">As funções lógicas relatório eletrônico (ER) podem ser usadas para trabalhar com valores lógicos a fim de executar mais de uma comparação em uma única expressão ou testar várias condições.</span><span class="sxs-lookup"><span data-stu-id="ccce7-104">Electronic reporting (ER) logical functions can be used to work with logical values to perform more than one comparison in a single expression or test multiple conditions.</span></span> <span data-ttu-id="ccce7-105">Este tópico fornece um resumo dessas funções.</span><span class="sxs-lookup"><span data-stu-id="ccce7-105">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="ccce7-106">Lista de funções com suporte</span><span class="sxs-lookup"><span data-stu-id="ccce7-106">List of supported functions</span></span>

| <span data-ttu-id="ccce7-107">Função</span><span class="sxs-lookup"><span data-stu-id="ccce7-107">Function</span></span> | <span data-ttu-id="ccce7-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="ccce7-108">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="ccce7-109">E</span><span class="sxs-lookup"><span data-stu-id="ccce7-109">And</span></span>](er-functions-logical-and.md)                       | <span data-ttu-id="ccce7-110">Essa função retorna um valor *Booliano* de **TRUE** se todas as condições especificadas forem verdadeiras.</span><span class="sxs-lookup"><span data-stu-id="ccce7-110">This function returns a *Boolean* value of **TRUE** if all the specified conditions are true.</span></span> <span data-ttu-id="ccce7-111">Caso contrário, ela retorna um valor *Booliano* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="ccce7-111">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> |
| [<span data-ttu-id="ccce7-112">Caixa</span><span class="sxs-lookup"><span data-stu-id="ccce7-112">Case</span></span>](er-functions-logical-case.md)                     | <span data-ttu-id="ccce7-113">Essa função avalia o valor da expressão especificada em relação às opções alternativas especificadas e retorna o resultado da primeira opção igual ao valor dessa expressão.</span><span class="sxs-lookup"><span data-stu-id="ccce7-113">This function evaluates the value of the specified expression against the specified alternative options and returns the result of the first option that equals the value of the specified expression.</span></span> <span data-ttu-id="ccce7-114">Caso contrário, ela retorna um resultado padrão opcional, se um resultado padrão for especificado como o último argumento da função chamada não precedida por uma opção.</span><span class="sxs-lookup"><span data-stu-id="ccce7-114">Otherwise, it returns an optional default result, if a default result is specified as the last argument of the called function that isn't preceded by an option.</span></span> <span data-ttu-id="ccce7-115">O valor retornado pode ser um valor de qualquer um dos tipos de dados com suporte.</span><span class="sxs-lookup"><span data-stu-id="ccce7-115">The value that is returned can be a value of any of the supported data types.</span></span> |
| [<span data-ttu-id="ccce7-116">Se</span><span class="sxs-lookup"><span data-stu-id="ccce7-116">If</span></span>](er-functions-logical-if.md)                         | <span data-ttu-id="ccce7-117">Essa função retorna o primeiro valor especificado se a condição especificada for atendida.</span><span class="sxs-lookup"><span data-stu-id="ccce7-117">This function returns the first specified value if the specified condition is met.</span></span> <span data-ttu-id="ccce7-118">Caso contrário, ele retorna o segundo valor especificado.</span><span class="sxs-lookup"><span data-stu-id="ccce7-118">Otherwise, it returns the second specified value.</span></span> <span data-ttu-id="ccce7-119">O valor retornado pode ser um valor de qualquer um dos tipos de dados com suporte.</span><span class="sxs-lookup"><span data-stu-id="ccce7-119">The value that is returned can be a value of any of the supported data types.</span></span> |
| [<span data-ttu-id="ccce7-120">Não</span><span class="sxs-lookup"><span data-stu-id="ccce7-120">Not</span></span>](er-functions-logical-not.md)                       | <span data-ttu-id="ccce7-121">Essa função retorna o valor lógico revertido da condição especificada como um valor *Booliano*.</span><span class="sxs-lookup"><span data-stu-id="ccce7-121">This function returns the reversed logical value of the specified condition as a *Boolean* value.</span></span> |
| [<span data-ttu-id="ccce7-122">Or</span><span class="sxs-lookup"><span data-stu-id="ccce7-122">Or</span></span>](er-functions-logical-or.md)                         | <span data-ttu-id="ccce7-123">Essa função retorna um valor *Booliano* de **FALSE** se todas as condições especificadas forem falsas.</span><span class="sxs-lookup"><span data-stu-id="ccce7-123">This function returns a *Boolean* value of **FALSE** if all the specified conditions are false.</span></span> <span data-ttu-id="ccce7-124">Se qualquer condição especificada for verdade, a função retorna um valor *Booliano* como **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="ccce7-124">If any specified condition is true, the function returns a *Boolean* value of **TRUE**.</span></span> |
| [<span data-ttu-id="ccce7-125">ValueIn</span><span class="sxs-lookup"><span data-stu-id="ccce7-125">ValueIn</span></span>](er-functions-logical-valuein.md)               | <span data-ttu-id="ccce7-126">Essa função determina se a entrada especificada corresponde a algum valor de um item especificado na lista especificada.</span><span class="sxs-lookup"><span data-stu-id="ccce7-126">This function determines whether the specified input matches any value of a specified item in the specified list.</span></span> <span data-ttu-id="ccce7-127">Ela retorna um valor *Booliano* de **TRUE** se a entrada especificada corresponder ao resultado da execução da expressão especificada para pelo menos um registro da lista especificada.</span><span class="sxs-lookup"><span data-stu-id="ccce7-127">It returns a *Boolean* value of **TRUE** if the specified input matches the result of running the specified expression for at least one record of the specified list.</span></span> <span data-ttu-id="ccce7-128">Caso contrário, ela retorna um valor *Booliano* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="ccce7-128">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="ccce7-129">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="ccce7-129">Additional resources</span></span>

[<span data-ttu-id="ccce7-130">Visão geral do Relatório Eletrônico</span><span class="sxs-lookup"><span data-stu-id="ccce7-130">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="ccce7-131">Designer de fórmulas no Relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="ccce7-131">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="ccce7-132">Linguagem da fórmula de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="ccce7-132">Electronic reporting formula language</span></span>](er-formula-language.md)
