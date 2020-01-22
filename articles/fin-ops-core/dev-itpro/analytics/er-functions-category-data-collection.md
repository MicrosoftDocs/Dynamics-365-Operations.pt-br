---
title: Lista de funções ER na categoria de coleção de dados
description: Este tópico fornece informações sobre as funções de coleção de dados que são compatíveis no relatório eletrônico (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: b318945c9cd10b237843d26cfdc46fc08e84e268
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917801"
---
# <a name="list-of-er-functions-in-the-data-collection-category"></a><span data-ttu-id="c6a07-103">Lista de funções ER na categoria de coleção de dados</span><span class="sxs-lookup"><span data-stu-id="c6a07-103">List of ER functions in the data collection category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c6a07-104">As funções de coleta de dados de relatório eletrônico (ER) são usadas para contabilizar e somar em um formato ER que está sendo executado, com base nos dados da saída que já foram gerados no formato **Texto** ou **XML**.</span><span class="sxs-lookup"><span data-stu-id="c6a07-104">Electronic reporting (ER) data collection functions are used to do counting and summing in an ER format that is being run, based on data of the output that has already been generated in **Text** or **Xml** format.</span></span> <span data-ttu-id="c6a07-105">Essa abordagem é usada para ajudar a melhorar o desempenho de um formato ER que é executado, inserir valores de totais acumulados em documentos gerados e para outros fins.</span><span class="sxs-lookup"><span data-stu-id="c6a07-105">This approach is used to help improve performance of an ER format that is run, to enter values of running totals in generated documents, and for other purposes.</span></span> <span data-ttu-id="c6a07-106">Este tópico fornece um resumo dessas funções.</span><span class="sxs-lookup"><span data-stu-id="c6a07-106">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="c6a07-107">Lista de funções com suporte</span><span class="sxs-lookup"><span data-stu-id="c6a07-107">List of supported functions</span></span>

| <span data-ttu-id="c6a07-108">Função</span><span class="sxs-lookup"><span data-stu-id="c6a07-108">Function</span></span> | <span data-ttu-id="c6a07-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="c6a07-109">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="c6a07-110">CollectedList</span><span class="sxs-lookup"><span data-stu-id="c6a07-110">CollectedList</span></span>](er-functions-datacollection-collectedlist.md) | <span data-ttu-id="c6a07-111">Essa função retorna um valor de *Lista de registros* que contém a lista de valores que foram retornados pela propriedade **Valor da chave de dados coletada** de formato e coletados quando os elementos de formato foram usados para gerar um documento de saída durante a execução do formato, e que satisfaçam as condições especificadas.</span><span class="sxs-lookup"><span data-stu-id="c6a07-111">This function returns a *Record list* value that contains the list of values that were returned by the **Collected data key value** property of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="c6a07-112">Cada condição consiste em um intervalo de chaves e um valor de chave.</span><span class="sxs-lookup"><span data-stu-id="c6a07-112">Each condition consists of a key range and a key value.</span></span> |
| [<span data-ttu-id="c6a07-113">CountIF</span><span class="sxs-lookup"><span data-stu-id="c6a07-113">CountIF</span></span>](er-functions-datacollection-countif.md) | <span data-ttu-id="c6a07-114">Essa função retorna um valor *Inteiro* que representa o número de elementos de formato que foram coletados quando os elementos de formato foram usados para gerar um documento de saída durante a execução do formato, e que satisfaçam a condição especificada.</span><span class="sxs-lookup"><span data-stu-id="c6a07-114">This function returns an *Integer* value that represents the number of format elements that was collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified condition.</span></span> <span data-ttu-id="c6a07-115">A condição consiste em um intervalo de chaves e um valor de chave.</span><span class="sxs-lookup"><span data-stu-id="c6a07-115">The condition consists of a key range and a key value.</span></span> |
| [<span data-ttu-id="c6a07-116">CountIFs</span><span class="sxs-lookup"><span data-stu-id="c6a07-116">CountIFs</span></span>](er-functions-datacollection-countifs.md) | <span data-ttu-id="c6a07-117">Essa função retorna um valor *Inteiro* que representa o número de elementos de formato que foram coletados quando os elementos de formato foram usados para gerar um documento de saída durante a execução do formato, e que satisfaçam as condições especificadas.</span><span class="sxs-lookup"><span data-stu-id="c6a07-117">This function returns an *Integer* value that represents the number of format elements that was collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="c6a07-118">Cada condição consiste em um intervalo de chaves e um valor de chave.</span><span class="sxs-lookup"><span data-stu-id="c6a07-118">Each condition consists of a key range and a key value.</span></span> |
| [<span data-ttu-id="c6a07-119">FormatElementName</span><span class="sxs-lookup"><span data-stu-id="c6a07-119">FormatElementName</span></span>](er-functions-datacollection-formatelementname.md) | <span data-ttu-id="c6a07-120">Esta função retorna um valor de *Cadeia de caracteres* que representa o nome do elemento do formato ER atual.</span><span class="sxs-lookup"><span data-stu-id="c6a07-120">This function returns a *String* value that represents the name of the current ER format's element.</span></span> |
| [<span data-ttu-id="c6a07-121">SumIF</span><span class="sxs-lookup"><span data-stu-id="c6a07-121">SumIF</span></span>](er-functions-datacollection-sumif.md) | <span data-ttu-id="c6a07-122">Essa função retorna um valor *Real* que representa a soma de valores que foram retornados por associações de elementos de formato e coletados quando os elementos de formato foram usados para gerar um documento de saída durante a execução do formato, e que satisfaçam a condição especificada.</span><span class="sxs-lookup"><span data-stu-id="c6a07-122">This function returns a *Real* value that represents the sum of values that were returned by bindings of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified condition.</span></span> <span data-ttu-id="c6a07-123">A condição consiste em um intervalo de chaves e um valor de chave.</span><span class="sxs-lookup"><span data-stu-id="c6a07-123">The condition consists of a key range and a key value.</span></span> |
| [<span data-ttu-id="c6a07-124">SumIFs</span><span class="sxs-lookup"><span data-stu-id="c6a07-124">SumIFs</span></span>](er-functions-datacollection-sumifs.md) | <span data-ttu-id="c6a07-125">Essa função retorna um valor *Real* que representa a soma de valores que foram retornados por associações de elementos de formato e coletados quando os elementos de formato foram usados para gerar um documento de saída durante a execução do formato, e que satisfaçam as condições especificadas.</span><span class="sxs-lookup"><span data-stu-id="c6a07-125">This function returns a *Real* value that represents the sum of values that were returned by bindings of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="c6a07-126">Cada condição consiste em um intervalo de chaves e um valor de chave.</span><span class="sxs-lookup"><span data-stu-id="c6a07-126">Each condition consists of a key range and a key value.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="c6a07-127">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="c6a07-127">Additional resources</span></span>

[<span data-ttu-id="c6a07-128">Visão geral do Relatório Eletrônico</span><span class="sxs-lookup"><span data-stu-id="c6a07-128">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="c6a07-129">Designer de fórmulas no Relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="c6a07-129">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="c6a07-130">Linguagem da fórmula de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="c6a07-130">Electronic reporting formula language</span></span>](er-formula-language.md)
