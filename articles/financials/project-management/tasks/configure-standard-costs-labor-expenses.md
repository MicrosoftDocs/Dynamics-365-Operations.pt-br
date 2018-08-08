--- 
title: "Configurar custos padrão para trabalho e despesas"
description: "Este procedimento mostra como configurar custos padrão para mão de obra e despesas de um projeto."
author: KimANelson
manager: AnnBe
ms.date: 02/13/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: c69fff5d9ec031d0ffa7d45f658317cd3296615f
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---
# <a name="configure-standard-costs-for-labor-and-expenses"></a><span data-ttu-id="8fead-103">Configurar custos padrão para trabalho e despesas</span><span class="sxs-lookup"><span data-stu-id="8fead-103">Configure standard costs for labor and expenses</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8fead-104">Este procedimento mostra como configurar custos padrão para mão de obra e despesas de um projeto.</span><span class="sxs-lookup"><span data-stu-id="8fead-104">This procedure shows you how to set up standard costs for labor and expenses for a project.</span></span> <span data-ttu-id="8fead-105">Essa tarefa usa o conjunto de dados de USSI.</span><span class="sxs-lookup"><span data-stu-id="8fead-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="8fead-106">Vá para Gerenciamento e contabilidade de projeto > Configuração > Preços > Preço de custo (hora).</span><span class="sxs-lookup"><span data-stu-id="8fead-106">Go to Project management and accounting > Setup > Prices > Cost price (hour).</span></span>
2. <span data-ttu-id="8fead-107">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="8fead-107">Click New.</span></span>
3. <span data-ttu-id="8fead-108">No campo Data efetiva, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="8fead-108">In the Effective date field, enter a date.</span></span>
4. <span data-ttu-id="8fead-109">No campo Preço de custo, insira um número.</span><span class="sxs-lookup"><span data-stu-id="8fead-109">In the Cost price field, enter a number.</span></span>
    * <span data-ttu-id="8fead-110">É possível configurar um preço de custo padrão para a categoria de projeto ou configurar um preço de custo por número de trabalhador, número de projeto, categoria, data ou qualquer combinação destes itens.</span><span class="sxs-lookup"><span data-stu-id="8fead-110">You can set up a standard cost price for the project category, or you can set up a cost price by worker number, project number, category, date, or any combination of these.</span></span> <span data-ttu-id="8fead-111">O preço de custo que é aplicado é o preço de custo com o nível mais alto de detalhes.</span><span class="sxs-lookup"><span data-stu-id="8fead-111">The cost price that is applied is the cost price with the highest level of detail.</span></span>  
5. <span data-ttu-id="8fead-112">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="8fead-112">Click Save.</span></span>
6. <span data-ttu-id="8fead-113">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8fead-113">Close the page.</span></span>
7. <span data-ttu-id="8fead-114">Vá para Gerenciamento e contabilidade de projeto > Configuração > Preços > Preço de venda (hora).</span><span class="sxs-lookup"><span data-stu-id="8fead-114">Go to Project management and accounting > Setup > Prices > Sales price (hour).</span></span>
8. <span data-ttu-id="8fead-115">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="8fead-115">Click New.</span></span>
9. <span data-ttu-id="8fead-116">No campo Data efetiva, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="8fead-116">In the Effective date field, enter a date.</span></span>
10. <span data-ttu-id="8fead-117">No campo Válido para, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="8fead-117">In the Valid for field, select an option.</span></span>
11. <span data-ttu-id="8fead-118">No campo Definição de preços, insira um número.</span><span class="sxs-lookup"><span data-stu-id="8fead-118">In the Pricing field, enter a number.</span></span>
    * <span data-ttu-id="8fead-119">Você pode configurar um preço de venda padrão para transações de horas ou para uma categoria de projeto.</span><span class="sxs-lookup"><span data-stu-id="8fead-119">You can set up a standard sales price for hour transactions or for a project category.</span></span> <span data-ttu-id="8fead-120">Também é possível configurar preços de venda por número do trabalhador, número do projeto, categoria, data da transação ou qualquer outra combinação desses itens.</span><span class="sxs-lookup"><span data-stu-id="8fead-120">You can also set up sales prices by worker number, project number, category, transaction date, or any combination of these.</span></span> <span data-ttu-id="8fead-121">O preço de venda real, que é aplicado quando um trabalhador lança uma transação no Diário de horas, é aquele com o nível mais alto de detalhes.</span><span class="sxs-lookup"><span data-stu-id="8fead-121">The actual sales price, which is applied when a worker enters a transaction in the Hour journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="8fead-122">Por exemplo, se tanto o preço de venda geral quanto um preço de venda específico do trabalhador estiverem configurados, será usado o preço de venda específico do trabalhador.</span><span class="sxs-lookup"><span data-stu-id="8fead-122">For example, if both a general sales price and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
12. <span data-ttu-id="8fead-123">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="8fead-123">Click Save.</span></span>
13. <span data-ttu-id="8fead-124">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8fead-124">Close the page.</span></span>
14. <span data-ttu-id="8fead-125">Vá para Gerenciamento e contabilidade de projeto > Configuração > Preços > Preço de custo (despesa).</span><span class="sxs-lookup"><span data-stu-id="8fead-125">Go to Project management and accounting > Setup > Prices > Cost price (expense).</span></span>
15. <span data-ttu-id="8fead-126">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="8fead-126">Click New.</span></span>
16. <span data-ttu-id="8fead-127">No campo Data efetiva, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="8fead-127">In the Effective date field, enter a date.</span></span>
17. <span data-ttu-id="8fead-128">No campo Preço de custo, insira um número.</span><span class="sxs-lookup"><span data-stu-id="8fead-128">In the Cost price field, enter a number.</span></span>
    * <span data-ttu-id="8fead-129">Vários campos podem ser preenchidos, mas este é o mínimo necessário salvar o registro.</span><span class="sxs-lookup"><span data-stu-id="8fead-129">Multiple fields can be filled in, but this is the minimum needed to save the record.</span></span>  
18. <span data-ttu-id="8fead-130">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="8fead-130">Click Save.</span></span>
19. <span data-ttu-id="8fead-131">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8fead-131">Close the page.</span></span>
20. <span data-ttu-id="8fead-132">Vá para Gerenciamento e contabilidade de projeto > Configuração > Preços > Preço de venda (despesa).</span><span class="sxs-lookup"><span data-stu-id="8fead-132">Go to Project management and accounting > Setup > Prices > Sales price (expense).</span></span>
21. <span data-ttu-id="8fead-133">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="8fead-133">Click New.</span></span>
22. <span data-ttu-id="8fead-134">No campo Data efetiva, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="8fead-134">In the Effective date field, enter a date.</span></span>
23. <span data-ttu-id="8fead-135">No campo Válido para, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="8fead-135">In the Valid for field, select an option.</span></span>
24. <span data-ttu-id="8fead-136">No campo Definição de preços, insira um número.</span><span class="sxs-lookup"><span data-stu-id="8fead-136">In the Pricing field, enter a number.</span></span>
    * <span data-ttu-id="8fead-137">O preço de venda real, que é aplicado quando um trabalhador insere transações em um diário de despesas, é o preço de venda com o nível mais alto de detalhes.</span><span class="sxs-lookup"><span data-stu-id="8fead-137">The actual sales price, which is applied when a worker enters transactions in an expense journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="8fead-138">Por exemplo, se tanto o preço de venda geral quanto um preço de venda específico do trabalhador estiverem configurados, será usado o preço de venda específico do trabalhador.</span><span class="sxs-lookup"><span data-stu-id="8fead-138">For example, if both a general and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
25. <span data-ttu-id="8fead-139">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="8fead-139">Click Save.</span></span>


