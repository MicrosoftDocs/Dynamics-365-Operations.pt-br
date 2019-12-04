---
title: Configurar custos padrão para trabalho e despesas
description: Este tópico explica como configurar custos padrão para mão de obra e despesas de um projeto.
author: KimANelson
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjCostPriceHour, ProjSalesPriceHour, ProjCostPriceExpense, ProjSalesPriceCost
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 60ab8eb94d4a8a0fb2c1e732ec7b25bfd5e7611e
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185396"
---
# <a name="configure-standard-costs-for-labor-and-expenses"></a><span data-ttu-id="c7d52-103">Configurar custos padrão para trabalho e despesas</span><span class="sxs-lookup"><span data-stu-id="c7d52-103">Configure standard costs for labor and expenses</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c7d52-104">Este tópico explica como configurar custos padrão para mão de obra e despesas de um projeto.</span><span class="sxs-lookup"><span data-stu-id="c7d52-104">This topic explains how to set up standard costs for labor and expenses for a project.</span></span> <span data-ttu-id="c7d52-105">Essa tarefa usa o conjunto de dados de USSI.</span><span class="sxs-lookup"><span data-stu-id="c7d52-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="c7d52-106">No Painel de Navegação, vá para **Módulos > Gerenciamento e contabilidade do projeto > Configuração > Preços > Preço de custo (hora)**.</span><span class="sxs-lookup"><span data-stu-id="c7d52-106">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Cost price (hour)**.</span></span>
2. <span data-ttu-id="c7d52-107">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c7d52-107">Select **New**.</span></span>
3. <span data-ttu-id="c7d52-108">No campo **Data efetiva**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="c7d52-108">In the **Effective date** field, enter a date.</span></span>
4. <span data-ttu-id="c7d52-109">No campo **Preço de custo**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="c7d52-109">In the **Cost price** field, enter a number.</span></span> <span data-ttu-id="c7d52-110">É possível configurar um preço de custo padrão para a categoria de projeto ou configurar um preço de custo por número de trabalhador, número de projeto, categoria, data ou qualquer combinação destes itens.</span><span class="sxs-lookup"><span data-stu-id="c7d52-110">You can set up a standard cost price for the project category, or you can set up a cost price by worker number, project number, category, date, or any combination of these.</span></span> <span data-ttu-id="c7d52-111">O preço de custo que é aplicado é o preço de custo com o nível mais alto de detalhes.</span><span class="sxs-lookup"><span data-stu-id="c7d52-111">The cost price that is applied is the cost price with the highest level of detail.</span></span>  
5. <span data-ttu-id="c7d52-112">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c7d52-112">Select **Save**.</span></span>
6. <span data-ttu-id="c7d52-113">No Painel de Navegação, vá para **Módulos > Gerenciamento e contabilidade do projeto > Configuração > Preços > Preço de venda (hora)**.</span><span class="sxs-lookup"><span data-stu-id="c7d52-113">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Sales price (hour)**.</span></span>
7. <span data-ttu-id="c7d52-114">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c7d52-114">Select **New**.</span></span>
8. <span data-ttu-id="c7d52-115">No campo **Data efetiva**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="c7d52-115">In the **Effective date** field, enter a date.</span></span>
9. <span data-ttu-id="c7d52-116">No campo **Válido para**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="c7d52-116">In the **Valid for** field, select an option.</span></span>
10. <span data-ttu-id="c7d52-117">No campo **Definição de preços**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="c7d52-117">In the **Pricing** field, enter a number.</span></span> <span data-ttu-id="c7d52-118">Você pode configurar um preço de venda padrão para transações de horas ou para uma categoria de projeto.</span><span class="sxs-lookup"><span data-stu-id="c7d52-118">You can set up a standard sales price for hour transactions or for a project category.</span></span> <span data-ttu-id="c7d52-119">Também é possível configurar preços de venda por número do trabalhador, número do projeto, categoria, data da transação ou qualquer outra combinação desses itens.</span><span class="sxs-lookup"><span data-stu-id="c7d52-119">You can also set up sales prices by worker number, project number, category, transaction date, or any combination of these.</span></span> <span data-ttu-id="c7d52-120">O preço de venda real, que é aplicado quando um trabalhador lança uma transação no Diário de horas, é aquele com o nível mais alto de detalhes.</span><span class="sxs-lookup"><span data-stu-id="c7d52-120">The actual sales price, which is applied when a worker enters a transaction in the Hour journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="c7d52-121">Por exemplo, se tanto o preço de venda geral quanto um preço de venda específico do trabalhador estiverem configurados, será usado o preço de venda específico do trabalhador.</span><span class="sxs-lookup"><span data-stu-id="c7d52-121">For example, if both a general sales price and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
11. <span data-ttu-id="c7d52-122">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c7d52-122">Select **Save**.</span></span>
12. <span data-ttu-id="c7d52-123">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c7d52-123">Close the page.</span></span>
13. <span data-ttu-id="c7d52-124">No Painel de Navegação, vá para **Módulos > Gerenciamento e contabilidade do projeto > Configuração > Preços > Preço de custo (despesa)**.</span><span class="sxs-lookup"><span data-stu-id="c7d52-124">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Cost price (expense)**.</span></span>
14. <span data-ttu-id="c7d52-125">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c7d52-125">Select **New**.</span></span>
15. <span data-ttu-id="c7d52-126">No campo **Data efetiva**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="c7d52-126">In the **Effective date** field, enter a date.</span></span>
16. <span data-ttu-id="c7d52-127">No campo **Preço de custo**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="c7d52-127">In the **Cost price** field, enter a number.</span></span> <span data-ttu-id="c7d52-128">Vários campos podem ser preenchidos, mas este é o mínimo necessário salvar o registro.</span><span class="sxs-lookup"><span data-stu-id="c7d52-128">Multiple fields can be filled in, but this is the minimum needed to save the record.</span></span>  
17. <span data-ttu-id="c7d52-129">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c7d52-129">Select **Save**.</span></span>
18. <span data-ttu-id="c7d52-130">No Painel de Navegação, vá para **Módulos > Gerenciamento e contabilidade do projeto > Configuração > Preços > Preço de venda (despesa)**.</span><span class="sxs-lookup"><span data-stu-id="c7d52-130">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Sales price (expense)**.</span></span>
19. <span data-ttu-id="c7d52-131">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c7d52-131">Select **New**.</span></span>
20. <span data-ttu-id="c7d52-132">No campo **Data efetiva**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="c7d52-132">In the **Effective date** field, enter a date.</span></span>
21. <span data-ttu-id="c7d52-133">No campo **Válido para**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="c7d52-133">In the **Valid for** field, select an option.</span></span>
22. <span data-ttu-id="c7d52-134">No campo **Definição de preços**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="c7d52-134">In the **Pricing** field, enter a number.</span></span> <span data-ttu-id="c7d52-135">O preço de venda real, que é aplicado quando um trabalhador insere transações em um diário de despesas, é o preço de venda com o nível mais alto de detalhes.</span><span class="sxs-lookup"><span data-stu-id="c7d52-135">The actual sales price, which is applied when a worker enters transactions in an expense journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="c7d52-136">Por exemplo, se tanto o preço de venda geral quanto um preço de venda específico do trabalhador estiverem configurados, será usado o preço de venda específico do trabalhador.</span><span class="sxs-lookup"><span data-stu-id="c7d52-136">For example, if both a general and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
23. <span data-ttu-id="c7d52-137">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c7d52-137">Select **Save**.</span></span>
