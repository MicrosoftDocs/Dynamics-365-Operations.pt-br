---
title: Criar um novo contrato comercial
description: Este procedimento mostra como criar um contrato comercial no qual você registra um novo preço de venda de produtos que você combinou com um cliente específico.
author: omulvad
manager: tfehr
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TradeNonStockedConversion, TradeNonStockedConversionChangeWizard, TradeNonStockedConversionCheckWorksheet, TradeNonStockedConversionWizard, TradeNonStockedRegister
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c1e1b48531e7ef7d55774936cb71130d048cdab7
ms.sourcegitcommit: 54da65a7da0efd4f0d9760c5b14ff785b28751c4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "3830444"
---
# <a name="create-a-new-trade-agreement"></a><span data-ttu-id="1c584-103">Criar um novo contrato comercial</span><span class="sxs-lookup"><span data-stu-id="1c584-103">Create a new trade agreement</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1c584-104">Este procedimento mostra como criar um contrato comercial no qual você registra um novo preço de venda de produtos que você combinou com um cliente específico.</span><span class="sxs-lookup"><span data-stu-id="1c584-104">This procedure shows you how to create a trade agreement where you register a new product sales price that you've agreed with a specific customer.</span></span> <span data-ttu-id="1c584-105">Você pode executar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="1c584-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="1c584-106">Se você estiver usando seus próprios dados, antes de iniciar esse guia será preciso ter certeza de que um Nome de diário de contratos comerciais existe onde a Relação padrão está definida como "Preços (vendas)".</span><span class="sxs-lookup"><span data-stu-id="1c584-106">If you're using your own data, before you start this guide you need to make sure that a Trade agreement journal name exists where the Default relation is set to "Price (sales)".</span></span>


## <a name="create-and-post-a-new-trade-agreement-journal"></a><span data-ttu-id="1c584-107">Criar e lançar um novo diário de contratos comerciais.</span><span class="sxs-lookup"><span data-stu-id="1c584-107">Create and post a new trade agreement journal</span></span>
1. <span data-ttu-id="1c584-108">Vá para **Painel de navegação > Módulos > Vendas e marketing > Preços e descontos > Diários de contratos comerciais**.</span><span class="sxs-lookup"><span data-stu-id="1c584-108">Go to **Navigation pane > Modules > Sales and marketing > Prices and discounts > Trade agreement journals**.</span></span>
2. <span data-ttu-id="1c584-109">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="1c584-109">Click **New**.</span></span>
3. <span data-ttu-id="1c584-110">No campo **Nome**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="1c584-110">In the **Name** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="1c584-111">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="1c584-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="1c584-112">No **Painel de Ações**, clique em **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="1c584-112">On **Action Pane**, click **Lines**.</span></span>
6. <span data-ttu-id="1c584-113">No campo **Código da conta**, selecione 'Tabela'.</span><span class="sxs-lookup"><span data-stu-id="1c584-113">In the **Account code** field, select 'Table'.</span></span>
    
    <span data-ttu-id="1c584-114">Neste exemplo, você está atualizando o preço para um cliente específico, o que significa quem você precisa selecionar Tabela.</span><span class="sxs-lookup"><span data-stu-id="1c584-114">In this example, you're updating the price for a specific customer, which means you need to choose Table.</span></span> <span data-ttu-id="1c584-115">Se você estava atualizando o preço da lista de produtos, selecionaria 'Todos'; assim, o novo preço seria válido para todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="1c584-115">If you were updating the product's list price, you would select 'All', so that the new price is valid for all customers.</span></span> <span data-ttu-id="1c584-116">Se você estava diferenciando preços entre diferentes segmentos de clientes, então você deve selecionar Grupo.</span><span class="sxs-lookup"><span data-stu-id="1c584-116">If you were differentiating prices among different customer segments, then you would select Group.</span></span> <span data-ttu-id="1c584-117">Para selecionar Grupo, é necessário configurar Grupos de preços ao cliente.</span><span class="sxs-lookup"><span data-stu-id="1c584-117">To select Group, you must have set up Customer price groups.</span></span>  

7. <span data-ttu-id="1c584-118">No campo **Seleção de conta**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="1c584-118">In the **Account selection** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="1c584-119">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="1c584-119">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="1c584-120">No campo **Código do item**, selecione 'Tabela'.</span><span class="sxs-lookup"><span data-stu-id="1c584-120">In the **Item code** field, select 'Table'.</span></span>
    
    <span data-ttu-id="1c584-121">Quando você está inserindo um contrato comercial do tipo 'Preço (vendas)', deve selecionar apenas 'Tabela' no campo **Código do item**.</span><span class="sxs-lookup"><span data-stu-id="1c584-121">When you are entering a trade agreement of type 'Price (sales)', you must only select 'Table' in the **Item code** field.</span></span> <span data-ttu-id="1c584-122">Isso ocorre porque um preço é um valor absoluto e não pode ser o mesmo para todos os produtos ou para um grupo de produtos.</span><span class="sxs-lookup"><span data-stu-id="1c584-122">This is because a price is an absolute value and cannot be same for all products or a group of products.</span></span>
    
10. <span data-ttu-id="1c584-123">No campo **Relação do item**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="1c584-123">In the **Item relation** field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="1c584-124">Na lista, selecione o produto que deseja incluir no contrato.</span><span class="sxs-lookup"><span data-stu-id="1c584-124">In the list, select the product you want to include in the agreement.</span></span> <span data-ttu-id="1c584-125">Faça uma nota dos produtos que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="1c584-125">Make a note of which product you've selected.</span></span>  
12. <span data-ttu-id="1c584-126">No campo **De**, insira uma quantidade mínima.</span><span class="sxs-lookup"><span data-stu-id="1c584-126">In the **From** field, enter a minimum quantity.</span></span>
    - <span data-ttu-id="1c584-127">Se o cliente precisa solicitar uma quantidade mínima para se qualificar para o novo preço, especifique essa quantidade aqui.</span><span class="sxs-lookup"><span data-stu-id="1c584-127">If the customer has to order a minimum quantity before they can qualify for the new price, then you need to specify that quantity here.</span></span>  
    - <span data-ttu-id="1c584-128">Insira um valor no campo **Para** para especificar a quantidade máxima acima da qual o preço do contrato não será válido.</span><span class="sxs-lookup"><span data-stu-id="1c584-128">Enter a value in the **To** field to specify the maximum quantity above which the agreement's price will not be valid.</span></span> <span data-ttu-id="1c584-129">Se você oferecer preços e descontos com base em múltiplas divisões de quantidade, especifique cada faixa de quantidade como um par de quantidade mínima e máxima nos campos **De** e **Para**, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="1c584-129">If you offer prices and discounts based on multiple quantity breaks, then specify each quantity bracket as a pair of minimum and maximum quantity in the **From** and **To** fields respectively.</span></span>
13. <span data-ttu-id="1c584-130">No campo **Valor em moeda**, insira um preço.</span><span class="sxs-lookup"><span data-stu-id="1c584-130">In the **Amount in currency field**, enter a price.</span></span>
14. <span data-ttu-id="1c584-131">Na seção **Detalhes**, no campo **Data inicial**, insira uma data a partir da qual esse contrato será válido.</span><span class="sxs-lookup"><span data-stu-id="1c584-131">Under the **Details** section, in the **From date** field, enter a date from which this agreement will be valid.</span></span>
15. <span data-ttu-id="1c584-132">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="1c584-132">Click **Save**.</span></span>
16. <span data-ttu-id="1c584-133">Clique em **Validar**.</span><span class="sxs-lookup"><span data-stu-id="1c584-133">Click **Validate**.</span></span>
17. <span data-ttu-id="1c584-134">Clique em **Validar as linhas selecionadas**.</span><span class="sxs-lookup"><span data-stu-id="1c584-134">Click **Validate selected lines**.</span></span>
18. <span data-ttu-id="1c584-135">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1c584-135">Click **OK**.</span></span>
19. <span data-ttu-id="1c584-136">Clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="1c584-136">Click **Post**.</span></span>
20. <span data-ttu-id="1c584-137">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1c584-137">Click **OK**.</span></span>

## <a name="view-trade-agreements-for-a-product"></a><span data-ttu-id="1c584-138">Exibir contratos comerciais para um produto</span><span class="sxs-lookup"><span data-stu-id="1c584-138">View trade agreements for a product</span></span>
1. <span data-ttu-id="1c584-139">Vá para **Painel de Navegação > Módulos > Gerenciamento de informações do produto > Produtos > Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="1c584-139">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>
2. <span data-ttu-id="1c584-140">Na lista, localize e selecione o produto cujo preço você acabou de atualizar.</span><span class="sxs-lookup"><span data-stu-id="1c584-140">In the list, find and select the product whose price you have just updated.</span></span>
3. <span data-ttu-id="1c584-141">No **Painel de Ação**, clique em **Vender**.</span><span class="sxs-lookup"><span data-stu-id="1c584-141">On the **Action Pane**, click **Sell**.</span></span>
4. <span data-ttu-id="1c584-142">Clique em **Exibir contratos comerciais**.</span><span class="sxs-lookup"><span data-stu-id="1c584-142">Click **View trade agreements**.</span></span>
    
    <span data-ttu-id="1c584-143">Revise os detalhes do contrato comercial de preço que acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="1c584-143">Review the details of the price trade agreement you have just created.</span></span>    

5. <span data-ttu-id="1c584-144">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1c584-144">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1c584-145">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="1c584-145">Additional resources</span></span>
### <a name="community-blogs"></a><span data-ttu-id="1c584-146">Blogs da comunidade</span><span class="sxs-lookup"><span data-stu-id="1c584-146">Community blogs</span></span>
- [<span data-ttu-id="1c584-147">Preços de venda no Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="1c584-147">Sales prices in Dynamics 365 for Finance and Operations</span></span>](https://financefunction.tech/2018/11/14/sales-prices-in-dynamics-365-for-finance-and-operations/#sales_price_in_trade_agreements)
