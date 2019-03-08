---
title: Mapear membros de dimensão de elemento de custo para um conjunto comum de membros de dimensão
description: Mapeando membros diferentes de dimensões do elemento de custo estimado na comum conjunto de elementos de custo previsto dimensões membros, você mesclam dados em um formato comum para fins de análise.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension, CAMDimensionMember
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 223234
ms.assetid: 4c66a231-aed2-48b5-9727-b3eb4fe6e6aa
ms.search.region: global
ms.author: shylaw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e5c9387d74443ec6ca5dc70ad923b67f962181dc
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "318134"
---
# <a name="map-cost-element-dimension-members-to-a-common-set-of-dimension-members"></a><span data-ttu-id="5435b-103">Mapear membros de dimensão de elemento de custo para um conjunto comum de membros de dimensão</span><span class="sxs-lookup"><span data-stu-id="5435b-103">Map cost element dimension members to a common set of dimension members</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5435b-104">Mapeando membros diferentes de dimensões do elemento de custo estimado na comum conjunto de elementos de custo previsto dimensões membros, você mesclam dados em um formato comum para fins de análise.</span><span class="sxs-lookup"><span data-stu-id="5435b-104">By mapping different cost element dimension members to a common set of cost element dimension members, you merge data into a common format for analysis purposes.</span></span>

<span data-ttu-id="5435b-105">Se for uma empresa e global obedecer os requisitos legais de contabilidade, você pode usar vários gráficos de contas.</span><span class="sxs-lookup"><span data-stu-id="5435b-105">If you're a global company and comply with statutory accounting requirements, you might use multiple charts of accounts.</span></span> <span data-ttu-id="5435b-106">Quando você importa membros da dimensão do elemento de custo previsto de gráfico de contas diferentes, você pode encerrar acima com uma mistura de contas.</span><span class="sxs-lookup"><span data-stu-id="5435b-106">When you import cost element dimension members from different charts of accounts, you can end up with a mix of accounts.</span></span> <span data-ttu-id="5435b-107">Porém, essas contas podem ter a mesma realmente natureza, e você pode querer analisar e alocar custos para eles usando um formato comum.</span><span class="sxs-lookup"><span data-stu-id="5435b-107">However, these accounts might actually have the same nature, and you might want to analyze and allocate costs for them by using a common format.</span></span>

## <a name="map-cost-element-dimension-members-to-a-common-format"></a><span data-ttu-id="5435b-108">Mapear membros da dimensão do elemento de custo estimado em um formato comum</span><span class="sxs-lookup"><span data-stu-id="5435b-108">Map cost element dimension members to a common format</span></span>
<span data-ttu-id="5435b-109">O exemplo a seguir mostra como é, como controlador de custo previsto, pode criar uma nova dimensão de elemento de custo estimado na contabilização de custo previsto que os membros da dimensão do elemento de custo previsto de mapas de gráfico. de E contracheques. estrutura de contas e de plano francês estrutura de contas na comum conjunto de elementos de custo previsto de membros.</span><span class="sxs-lookup"><span data-stu-id="5435b-109">The following example shows how you, as a cost controller, can create a new cost element dimension in Cost accounting that maps cost element dimension members from the US chart of accounts structure and the French chart of accounts structure to a common set of cost element dimension members.</span></span> <span data-ttu-id="5435b-110">Você pode usar a comum definida de membros da dimensão do elemento de custo estimado para analisar dados de custo previsto de duas entidades legais em um motivo de contabilização de custo previsto.</span><span class="sxs-lookup"><span data-stu-id="5435b-110">You can then use the common set of cost element dimension members to analyze cost data from the two legal entities in a cost accounting ledger.</span></span>

| <span data-ttu-id="5435b-111">Fonte: plano de contas dos EUA</span><span class="sxs-lookup"><span data-stu-id="5435b-111">Source: US chart of accounts</span></span>                                          | <span data-ttu-id="5435b-112">Fonte: plano de contas Francês</span><span class="sxs-lookup"><span data-stu-id="5435b-112">Source: French chart of accounts</span></span>                                          | <span data-ttu-id="5435b-113">Novo comum definido de membros da dimensão do elemento de custo previsto</span><span class="sxs-lookup"><span data-stu-id="5435b-113">New common set of cost element dimension members</span></span>                        |
|-----------------------------------------------------------------------|---------------------------------------------------------------------------|-------------------------------------------------------------------------|
| <span data-ttu-id="5435b-114">Membros importados dimensão de elemento de custo previsto plano de contas dos EUA</span><span class="sxs-lookup"><span data-stu-id="5435b-114">Imported cost element dimension members from the US chart of accounts</span></span> | <span data-ttu-id="5435b-115">Membros importados dimensão de elemento de custo previsto do gráfico de contas Francês.</span><span class="sxs-lookup"><span data-stu-id="5435b-115">Imported cost element dimension members from the French chart of accounts</span></span> | <span data-ttu-id="5435b-116">Mapeamento de membros franceses e dos EUA e dimensão de elemento de custo previsto a um conjunto comuns</span><span class="sxs-lookup"><span data-stu-id="5435b-116">Mapping of US and French cost element dimension members to a common set</span></span> |
| <span data-ttu-id="5435b-117">5001: vendas</span><span class="sxs-lookup"><span data-stu-id="5435b-117">5001: Sales</span></span>                                                           | <span data-ttu-id="5435b-118">5001: Vendas e propaganda</span><span class="sxs-lookup"><span data-stu-id="5435b-118">5001: Sales and advertising</span></span>                                               | <span data-ttu-id="5435b-119">5000: Vendas e propaganda</span><span class="sxs-lookup"><span data-stu-id="5435b-119">5000: Sales and advertising</span></span>                                             |
| <span data-ttu-id="5435b-120">5030: Publicidade</span><span class="sxs-lookup"><span data-stu-id="5435b-120">5030: Advertising</span></span>                                                     | <span data-ttu-id="5435b-121">6390: Compra de estoque\*</span><span class="sxs-lookup"><span data-stu-id="5435b-121">6390: Stock purchase\*</span></span>                                                    | <span data-ttu-id="5435b-122">7000: Limpeza de despesas</span><span class="sxs-lookup"><span data-stu-id="5435b-122">7000: Cleaning expenses</span></span>                                                 |
| <span data-ttu-id="5435b-123">7001: Limpeza de despesas</span><span class="sxs-lookup"><span data-stu-id="5435b-123">7001: Cleaning expenses</span></span>                                               | <span data-ttu-id="5435b-124">7001: Despesa de viagens</span><span class="sxs-lookup"><span data-stu-id="5435b-124">7001: Travel expense</span></span>                                                      | <span data-ttu-id="5435b-125">7001: Despesa de viagens</span><span class="sxs-lookup"><span data-stu-id="5435b-125">7001: Travel expenses</span></span>                                                   |

<span data-ttu-id="5435b-126">\*\*\*O membro francês dimensão de elemento de custo previsto de compra de estoque não é mapeado.</span><span class="sxs-lookup"><span data-stu-id="5435b-126">\*The Stock purchase French cost element dimension member isn't mapped.</span></span>

## <a name="currency-conversion"></a><span data-ttu-id="5435b-127">Conversão de moeda</span><span class="sxs-lookup"><span data-stu-id="5435b-127">Currency conversion</span></span>
<span data-ttu-id="5435b-128">Vários gráficos de contas usado podem ser definidos para usar moedas diferentes.</span><span class="sxs-lookup"><span data-stu-id="5435b-128">The various charts of accounts that you use might be set up to use different currencies.</span></span> <span data-ttu-id="5435b-129">Nesse caso, verifique especifique uma conversão de moedas, de modo que os dados de custo previsto são processados usando a moeda correta, como definido no razão da contabilização de custo estimado nos membros da dimensão do elemento de custo previsto são usados.</span><span class="sxs-lookup"><span data-stu-id="5435b-129">In this case, be sure to specify a currency conversion, so that cost data is processed by using the correct currency, as defined in the cost accounting ledger where the cost element dimension members are used.</span></span> <span data-ttu-id="5435b-130">No exemplo acima, se os dólares americanos (USD) são usados no razão da contabilização de custo previsto, você deve criar uma conversão de moeda USD em euro (EUR) para processar transações dos membros mapeados dimensão de elemento de custo previsto.</span><span class="sxs-lookup"><span data-stu-id="5435b-130">In the preceding example, if US dollars (USD) are used in the cost accounting ledger, you must create a currency conversion from USD to euros (EUR) to process transactions for the mapped cost element dimension members.</span></span>

## <a name="update-mappings-at-any-time"></a><span data-ttu-id="5435b-131">Mapeamentos de atualização a qualquer momento</span><span class="sxs-lookup"><span data-stu-id="5435b-131">Update mappings at any time</span></span>
<span data-ttu-id="5435b-132">Você pode atualizar as definições de mapeamento para uma dimensão de elemento de custo previsto a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="5435b-132">You can update the mapping definitions for a cost element dimension at any time.</span></span> <span data-ttu-id="5435b-133">Como os mapeamentos não são efetivos data, as alterações são aplicadas na próxima vez que você processa transações de custo estimado ou cálculos de custo estimados executado.</span><span class="sxs-lookup"><span data-stu-id="5435b-133">Because mappings aren't date-effective, changes are applied the next time that you process cost transactions or run cost calculations.</span></span>



