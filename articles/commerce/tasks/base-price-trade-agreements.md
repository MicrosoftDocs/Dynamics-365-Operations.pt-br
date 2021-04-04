---
title: Preço base e contratos comerciais
description: Este procedimento orienta na criação de contratos comerciais de preço de venda específicos para o canal.
author: josaw1
manager: AnnBe
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PriceDiscGroup, RetailStoreTable, RetailChannelPriceGroup, EcoResProductDetailsExtended, PriceDiscAdmTable, PriceDiscAdm
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bab25988a9d4aad4d4e36fd9bdffbbf52473435e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5259449"
---
# <a name="base-price-and-trade-agreements"></a><span data-ttu-id="7f57c-103">Preço base e contratos comerciais</span><span class="sxs-lookup"><span data-stu-id="7f57c-103">Base price and trade agreements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7f57c-104">Este procedimento orienta na criação de contratos comerciais de preço de venda específicos para o canal.</span><span class="sxs-lookup"><span data-stu-id="7f57c-104">This procedure walks through creating channel-specific sales price trade agreements.</span></span> <span data-ttu-id="7f57c-105">Este procedimento usa a empresa de dados de demonstração USRT.</span><span class="sxs-lookup"><span data-stu-id="7f57c-105">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="7f57c-106">No **Painel de navegação**, vá para **Módulos > Varejo e Comércio > Gerenciamento de preços e descontos > Grupos de preços > Todos os grupos de preços**.</span><span class="sxs-lookup"><span data-stu-id="7f57c-106">In the **Navigation pane**, go to **Modules > Retail and Commerce > Pricing and discounts management > Price groups > All price groups**.</span></span> <span data-ttu-id="7f57c-107">Os grupos de preço são como os contratos comerciais são atribuídos a canais específicos.</span><span class="sxs-lookup"><span data-stu-id="7f57c-107">Price groups are how trade agreements are assigned to specific channels.</span></span> <span data-ttu-id="7f57c-108">O uso de grupos de preços para atribuir contratos comerciais a um canal habilita a definição de preços específica para o canal.</span><span class="sxs-lookup"><span data-stu-id="7f57c-108">Using price groups to assign trade agreements to a channel enables channel-specific pricing.</span></span>  
2. <span data-ttu-id="7f57c-109">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="7f57c-109">Click **New**.</span></span>
3. <span data-ttu-id="7f57c-110">No campo **Grupos de preços**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7f57c-110">In the **Price groups** field, type a value.</span></span>
4. <span data-ttu-id="7f57c-111">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7f57c-111">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="7f57c-112">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7f57c-112">Click **Save**.</span></span>
6. <span data-ttu-id="7f57c-113">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7f57c-113">Close the page.</span></span>
7. <span data-ttu-id="7f57c-114">No **Painel de navegação**, acesse **Módulos > Varejo e Comércio > Canais > Lojas > Todas as lojas**.</span><span class="sxs-lookup"><span data-stu-id="7f57c-114">In the **Navigation pane**, go to **Modules > Retail and Commerce > Channels > Stores > All stores**.</span></span>
8. <span data-ttu-id="7f57c-115">Na lista, selecione 'Nova York'.</span><span class="sxs-lookup"><span data-stu-id="7f57c-115">In the list, select 'New York'</span></span>
9. <span data-ttu-id="7f57c-116">No Painel de Ações, clique em **Loja**.</span><span class="sxs-lookup"><span data-stu-id="7f57c-116">On the Action Pane, click **Store**.</span></span>
10. <span data-ttu-id="7f57c-117">Clique em **Grupos de preços**.</span><span class="sxs-lookup"><span data-stu-id="7f57c-117">Click **Price groups**.</span></span>
11. <span data-ttu-id="7f57c-118">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="7f57c-118">Click **New**.</span></span>
12. <span data-ttu-id="7f57c-119">No campo **Grupos de preços**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7f57c-119">In the **Price groups** field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="7f57c-120">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="7f57c-120">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="7f57c-121">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7f57c-121">Click **Save**.</span></span>
15. <span data-ttu-id="7f57c-122">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7f57c-122">Close the page.</span></span>
16. <span data-ttu-id="7f57c-123">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7f57c-123">Close the page.</span></span>
17. <span data-ttu-id="7f57c-124">No **Painel de navegação**, vá para **Módulos > Varejo e Comércio > Produtos e categorias > Produtos lançados por categoria**.</span><span class="sxs-lookup"><span data-stu-id="7f57c-124">In the **Navigation pane**, go to **Modules > Retail and Commerce > Products and categories > Released products by category**.</span></span>
18. <span data-ttu-id="7f57c-125">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7f57c-125">In the list, click the link in the selected row.</span></span>
19. <span data-ttu-id="7f57c-126">Clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7f57c-126">Click **Edit**.</span></span>
20. <span data-ttu-id="7f57c-127">Expanda a Guia Rápida **Vender**.</span><span class="sxs-lookup"><span data-stu-id="7f57c-127">Expand the **Sell** fastTab.</span></span>
21. <span data-ttu-id="7f57c-128">No campo **Preço**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="7f57c-128">In the **Price** field, enter a number.</span></span> <span data-ttu-id="7f57c-129">Esse preço será usado se nenhum contrato comercial aplicável for encontrado.</span><span class="sxs-lookup"><span data-stu-id="7f57c-129">This price is used if no applicable trade agreements are found.</span></span>  
22. <span data-ttu-id="7f57c-130">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7f57c-130">Click **Save**.</span></span>
23. <span data-ttu-id="7f57c-131">No **Painel de Ações**, clique em **Vender**.</span><span class="sxs-lookup"><span data-stu-id="7f57c-131">On the **Action Pane**, click **Sell**.</span></span>
24. <span data-ttu-id="7f57c-132">Criar em **Criar contratos comerciais**.</span><span class="sxs-lookup"><span data-stu-id="7f57c-132">Click **Create trade agreements**.</span></span>
25. <span data-ttu-id="7f57c-133">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="7f57c-133">Click **New**.</span></span>
26. <span data-ttu-id="7f57c-134">No campo **Nome**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7f57c-134">In the **Name** field, click the drop-down button to open the lookup.</span></span>
27. <span data-ttu-id="7f57c-135">Na lista, selecione **Comércio**.</span><span class="sxs-lookup"><span data-stu-id="7f57c-135">In the list, select **Commerce**.</span></span> <span data-ttu-id="7f57c-136">Nos dados de demonstração, o nome do diário **Comércio** tem a relação de **Preço (vendas)** padrão.</span><span class="sxs-lookup"><span data-stu-id="7f57c-136">In the demo data, the **Commerce** journal name has the default relation of **Price (sales)**.</span></span> <span data-ttu-id="7f57c-137">Isso significa que todas as novas linhas criadas assumirão como padrão os contratos comerciais de preço de venda.</span><span class="sxs-lookup"><span data-stu-id="7f57c-137">That means all new lines created will default to sales price trade agreements.</span></span>  
28. <span data-ttu-id="7f57c-138">No **Painel de ação**, clique em **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="7f57c-138">On the **Action pane**, click **Lines**.</span></span>
29. <span data-ttu-id="7f57c-139">No campo **Tipo de código de participante**, selecione "Grupo".</span><span class="sxs-lookup"><span data-stu-id="7f57c-139">In the **Party code type** field, select 'Group'.</span></span>
30. <span data-ttu-id="7f57c-140">No campo **Seleção de conta**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7f57c-140">In the **Account selection** field, click the drop-down button to open the lookup.</span></span>
31. <span data-ttu-id="7f57c-141">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="7f57c-141">In the list, find and select the desired record.</span></span> <span data-ttu-id="7f57c-142">Isso completará o link do canal com o grupo de preços com o contrato comercial.</span><span class="sxs-lookup"><span data-stu-id="7f57c-142">This will complete the link from Channel to Price group to Trade agreement.</span></span>  
32. <span data-ttu-id="7f57c-143">No campo **Relação de item**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7f57c-143">In the **Item relation** field, type a value.</span></span>
33. <span data-ttu-id="7f57c-144">No campo **Valor em moeda**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="7f57c-144">In the **Amount in currency** field, enter a number.</span></span>
34. <span data-ttu-id="7f57c-145">Na Guia Rápida **Detalhes**, marque ou desmarque caixa de seleção **Localizar próximo**.</span><span class="sxs-lookup"><span data-stu-id="7f57c-145">In the **Details** fastTab, check or uncheck the **Find next** checkbox.</span></span> <span data-ttu-id="7f57c-146">Quando **Localizar próximo** estiver definido como "Sim", o mecanismo de definição de preços continuará a pesquisar por contratos comerciais aplicáveis com um preço de venda mais baixo.</span><span class="sxs-lookup"><span data-stu-id="7f57c-146">When **Find next** is set to 'Yes', the pricing engine will continue to search for applicable trade agreements with a lower sale price.</span></span> <span data-ttu-id="7f57c-147">Quando **Localizar próximo** estiver definido como "Não", o mecanismo de definição de preços para de pesquisar e usa o contrato comercial.</span><span class="sxs-lookup"><span data-stu-id="7f57c-147">When **Find next** is set to 'No', the price engine stops searching and uses the trade agreement.</span></span>  
35. <span data-ttu-id="7f57c-148">Clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="7f57c-148">Click **Post**.</span></span>
36. <span data-ttu-id="7f57c-149">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="7f57c-149">Click **OK**.</span></span>
37. <span data-ttu-id="7f57c-150">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7f57c-150">Close the page.</span></span>
38. <span data-ttu-id="7f57c-151">No **Painel de Ações**, clique em Vender.</span><span class="sxs-lookup"><span data-stu-id="7f57c-151">On the **Action Pane**, click Sell.</span></span>
39. <span data-ttu-id="7f57c-152">Clique em **Preço de venda**.</span><span class="sxs-lookup"><span data-stu-id="7f57c-152">Click **Sales price**.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]