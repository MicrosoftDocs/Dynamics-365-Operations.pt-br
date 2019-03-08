---
title: Preço base e contratos comerciais
description: Este procedimento orienta na criação de contratos comerciais de preço de venda específicos para o canal.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PriceDiscGroup, RetailStoreTable, RetailChannelPriceGroup, EcoResProductDetailsExtended, PriceDiscAdmTable, PriceDiscAdm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4830ac553318cfbb3cb74395d1662e74dff75290
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "320411"
---
# <a name="base-price-and-trade-agreements"></a><span data-ttu-id="8d0bc-103">Preço base e contratos comerciais</span><span class="sxs-lookup"><span data-stu-id="8d0bc-103">Base price and trade agreements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="8d0bc-104">Este procedimento orienta na criação de contratos comerciais de preço de venda específicos para o canal.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-104">This procedure walks through creating channel-specific sales price trade agreements.</span></span> <span data-ttu-id="8d0bc-105">Este procedimento usa a empresa de dados de demonstração USRT.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-105">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="8d0bc-106">Vá para Varejo e comércio > Preços e descontos > Grupos de preços > Todos os grupos de preços.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-106">Go to Retail and commerce > Pricing and discounts > Price groups > All price groups.</span></span>
    * <span data-ttu-id="8d0bc-107">Os grupos de preço são como os contratos comerciais são atribuídos a canais específicos.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-107">Price groups are how trade agreements are assigned to specific channels.</span></span> <span data-ttu-id="8d0bc-108">O uso de grupos de preços para atribuir contratos comerciais a um canal habilita a definição de preços específica para o canal.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-108">Using price groups to assign trade agreements to a channel enables channel-specific pricing.</span></span>  
2. <span data-ttu-id="8d0bc-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-109">Click New.</span></span>
3. <span data-ttu-id="8d0bc-110">No campo Grupos de preços, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-110">In the Price groups field, type a value.</span></span>
4. <span data-ttu-id="8d0bc-111">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="8d0bc-112">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-112">Click Save.</span></span>
6. <span data-ttu-id="8d0bc-113">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-113">Close the page.</span></span>
7. <span data-ttu-id="8d0bc-114">Vá para Varejo e comércio > Canais > Lojas de varejo > Todas as lojas de varejo.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-114">Go to Retail and commerce > Channels > Retail stores > All retail stores.</span></span>
8. <span data-ttu-id="8d0bc-115">Na lista, selecione 'Nova York'.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-115">In the list, select 'New York'</span></span>
9. <span data-ttu-id="8d0bc-116">No Painel de Ação, clique em Loja.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-116">On the Action Pane, click Store.</span></span>
10. <span data-ttu-id="8d0bc-117">Clique em Grupos de preços.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-117">Click Price groups.</span></span>
11. <span data-ttu-id="8d0bc-118">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-118">Click New.</span></span>
12. <span data-ttu-id="8d0bc-119">No campo Grupos de preços, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-119">In the Price groups field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="8d0bc-120">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-120">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="8d0bc-121">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-121">Click Save.</span></span>
15. <span data-ttu-id="8d0bc-122">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-122">Close the page.</span></span>
16. <span data-ttu-id="8d0bc-123">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-123">Close the page.</span></span>
17. <span data-ttu-id="8d0bc-124">Vá para Varejo e comércio > Produtos e categorias > Produtos liberados por categoria.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-124">Go to Retail and commerce > Products and categories > Released products by category.</span></span>
18. <span data-ttu-id="8d0bc-125">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-125">In the list, click the link in the selected row.</span></span>
19. <span data-ttu-id="8d0bc-126">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-126">Click Edit.</span></span>
20. <span data-ttu-id="8d0bc-127">Ative/desative a expansão da seção Vender.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-127">Toggle the expansion of the Sell section.</span></span>
21. <span data-ttu-id="8d0bc-128">No campo Preço, insira um número.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-128">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="8d0bc-129">Esse preço será usado se nenhum contrato comercial aplicável for encontrado.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-129">This price is used if no applicable trade agreements are found.</span></span>  
22. <span data-ttu-id="8d0bc-130">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-130">Click Save.</span></span>
23. <span data-ttu-id="8d0bc-131">No Painel de Ação, clique em Vender.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-131">On the Action Pane, click Sell.</span></span>
24. <span data-ttu-id="8d0bc-132">Criar em Criar contratos comerciais.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-132">Click Create trade agreements.</span></span>
25. <span data-ttu-id="8d0bc-133">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-133">Click New.</span></span>
26. <span data-ttu-id="8d0bc-134">No campo Nome, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-134">In the Name field, click the drop-down button to open the lookup.</span></span>
27. <span data-ttu-id="8d0bc-135">Na lista, selecione 'Varejo'.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-135">In the list, select 'Retail'.</span></span>
    * <span data-ttu-id="8d0bc-136">Nos dados de demonstração, o nome do diário 'Varejo' tem a relação de 'Preço (vendas)' padrão.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-136">In the demo data, the 'Retail' journal name has the default relation of 'Price (sales)'.</span></span> <span data-ttu-id="8d0bc-137">Isso significa que todas as novas linhas criadas assumirão como padrão os contratos comerciais de preço de venda.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-137">That means all new lines created will default to sales price trade agreements.</span></span>  
28. <span data-ttu-id="8d0bc-138">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-138">Click Lines.</span></span>
29. <span data-ttu-id="8d0bc-139">No campo Código da conta, selecione 'Grupo'.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-139">In the Account code field, select 'Group'.</span></span>
30. <span data-ttu-id="8d0bc-140">No campo Seleção de conta, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-140">In the Account selection field, click the drop-down button to open the lookup.</span></span>
31. <span data-ttu-id="8d0bc-141">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-141">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="8d0bc-142">Isso completará o link do canal com o grupo de preços com o contrato comercial.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-142">This will complete the link from Channel to Price group to Trade agreement.</span></span>  
32. <span data-ttu-id="8d0bc-143">No campo Relação de item, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-143">In the Item relation field, type a value.</span></span>
33. <span data-ttu-id="8d0bc-144">No campo Valor em moeda, insira um número.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-144">In the Amount in currency field, enter a number.</span></span>
34. <span data-ttu-id="8d0bc-145">Marque ou desmarque a caixa de seleção Localizar próximo.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-145">Check or uncheck the Find next checkbox.</span></span>
    * <span data-ttu-id="8d0bc-146">Quando Localizar próximo estiver definido como 'Sim', o mecanismo de definição de preços continuará a pesquisar por contratos comerciais aplicáveis com um preço de venda mais baixo.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-146">When Find next is set to 'Yes', the pricing engine will continue to search for applicable trade agreements with a lower sale price.</span></span> <span data-ttu-id="8d0bc-147">Quando Localizar próximo estiver definido como 'Não', o mecanismo de definição de preços para de pesquisar e usa o contrato comercial.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-147">When Find next is set to 'No', the price engine stops searching and uses the trade agreement.</span></span>  
35. <span data-ttu-id="8d0bc-148">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-148">Click Post.</span></span>
36. <span data-ttu-id="8d0bc-149">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-149">Click OK.</span></span>
37. <span data-ttu-id="8d0bc-150">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-150">Close the page.</span></span>
38. <span data-ttu-id="8d0bc-151">No Painel de Ação, clique em Vender.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-151">On the Action Pane, click Sell.</span></span>
39. <span data-ttu-id="8d0bc-152">Clique em Preço de venda.</span><span class="sxs-lookup"><span data-stu-id="8d0bc-152">Click Sales price.</span></span>

