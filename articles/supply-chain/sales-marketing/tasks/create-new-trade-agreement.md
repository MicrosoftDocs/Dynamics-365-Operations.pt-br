--- 
title: Criar um novo contrato comercial
description: "Este procedimento mostra como criar um contrato comercial no qual você registra um novo preço de venda de produtos que você combinou com um cliente específico."
author: omulvad
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 0d0e5c5d680fcbac5407883a1d6365a4f312dda9
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---
# <a name="create-a-new-trade-agreement"></a><span data-ttu-id="418f5-103">Criar um novo contrato comercial</span><span class="sxs-lookup"><span data-stu-id="418f5-103">Create a new trade agreement</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="418f5-104">Este procedimento mostra como criar um contrato comercial no qual você registra um novo preço de venda de produtos que você combinou com um cliente específico.</span><span class="sxs-lookup"><span data-stu-id="418f5-104">This procedure shows you how to create a trade agreement where you register a new product sales price that you've agreed with a specific customer.</span></span> <span data-ttu-id="418f5-105">Você pode executar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="418f5-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="418f5-106">Se você estiver usando seus próprios dados, antes de iniciar esse guia será preciso ter certeza de que um Nome de diário de contratos comerciais existe onde a Relação padrão está definida como 'Preços (vendas)'.</span><span class="sxs-lookup"><span data-stu-id="418f5-106">If you’re using your own data, before you start this guide you need to make sure that a Trade agreement journal name exists where the Default relation is set to “Price (sales)”.</span></span>


## <a name="create-and-post-a-new-trade-agreement-journal"></a><span data-ttu-id="418f5-107">Criar e lançar um novo diário de contratos comerciais.</span><span class="sxs-lookup"><span data-stu-id="418f5-107">Create and post a new trade agreement journal</span></span>
1. <span data-ttu-id="418f5-108">Vá para Vendas e marketing > Preços e descontos > Diários de contratos comerciais.</span><span class="sxs-lookup"><span data-stu-id="418f5-108">Go to Sales and marketing > Prices and discounts > Trade agreement journals.</span></span>
2. <span data-ttu-id="418f5-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="418f5-109">Click New.</span></span>
3. <span data-ttu-id="418f5-110">No campo Nome, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="418f5-110">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="418f5-111">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="418f5-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="418f5-112">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="418f5-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="418f5-113">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="418f5-113">Click Lines.</span></span>
7. <span data-ttu-id="418f5-114">No campo Código da conta, selecione 'Tabela'.</span><span class="sxs-lookup"><span data-stu-id="418f5-114">In the Account code field, select 'Table'.</span></span>
    * <span data-ttu-id="418f5-115">Neste exemplo, você está atualizando o preço para um cliente específico, o que significa quem você precisa selecionar Tabela.</span><span class="sxs-lookup"><span data-stu-id="418f5-115">In this example, you're updating the price for a specific customer, which means you need to choose Table.</span></span> <span data-ttu-id="418f5-116">Se você estava atualizando o preço da lista de produtos, você deve selecionar Todos, de modo que o novo preço seja válido para todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="418f5-116">If you were updating the product's list price, you would select All, so that the new price is valid for all customers.</span></span> <span data-ttu-id="418f5-117">Se você estava diferenciando preços entre diferentes segmentos de clientes, então você deve selecionar Grupo.</span><span class="sxs-lookup"><span data-stu-id="418f5-117">If you were differentiating prices among different customer segments, then you would select Group.</span></span> <span data-ttu-id="418f5-118">Para selecionar Grupo, é necessário configurar Grupos de preços ao cliente.</span><span class="sxs-lookup"><span data-stu-id="418f5-118">To select Group, you must have set up Customer price groups.</span></span>  
8. <span data-ttu-id="418f5-119">No campo Seleção de conta, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="418f5-119">In the Account selection field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="418f5-120">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="418f5-120">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="418f5-121">No campo Código do item, selecione 'Tabela'.</span><span class="sxs-lookup"><span data-stu-id="418f5-121">In the Item code field, select 'Table'.</span></span>
    * <span data-ttu-id="418f5-122">Quando você está inserindo um contrato comercial do tipo 'Preço (vendas)', você deve selecionar apenas 'Tabela' no campo de código do item.</span><span class="sxs-lookup"><span data-stu-id="418f5-122">When you are entering a trade agreement of type 'Price (sales)', you must only select 'Table' in the Item code field.</span></span> <span data-ttu-id="418f5-123">Isso ocorre porque um preço é um valor absoluto e não pode ser o mesmo para todos os produtos ou para um grupo de produtos.</span><span class="sxs-lookup"><span data-stu-id="418f5-123">This is because a price is an absolute value and cannot be same for all products or a group of products.</span></span>  
11. <span data-ttu-id="418f5-124">No campo Relação do item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="418f5-124">In the Item relation field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="418f5-125">Na lista, selecione o produto que deseja incluir no contrato.</span><span class="sxs-lookup"><span data-stu-id="418f5-125">In the list, select the product you want to include in the agreement.</span></span>
    * <span data-ttu-id="418f5-126">Faça uma nota dos produtos que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="418f5-126">Make a note of which product you've selected.</span></span>  
13. <span data-ttu-id="418f5-127">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="418f5-127">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="418f5-128">No campo De, insira uma quantidade mínima.</span><span class="sxs-lookup"><span data-stu-id="418f5-128">In the From field, enter a minimum quantity.</span></span>
    * <span data-ttu-id="418f5-129">Se o cliente tem que solicitar uma quantidade mínima antes de se qualificar para o novo preço, então você precisa especificar essa quantidade aqui.</span><span class="sxs-lookup"><span data-stu-id="418f5-129">If the customer has to order a minimum quantity  before they can qualify for the new price, then you need to specify that quantity here.</span></span>  
    * <span data-ttu-id="418f5-130">Insira um valor no campo Para para especificar a quantidade máxima acima da qual o preço do contrato não será válido.</span><span class="sxs-lookup"><span data-stu-id="418f5-130">Enter a value in the To field to specify the maximum quantity above which the agreement's price will not be valid.</span></span> <span data-ttu-id="418f5-131">Se você oferece preços e descontos com base em múltiplas divisões de quantidade, então especifique cada faixa de quantidade como um par de quantidade mínima e máxima nos campos 'De' e 'Para', respectivamente.</span><span class="sxs-lookup"><span data-stu-id="418f5-131">If you offer prices and discounts based on multiple quantity breaks, then specify each quantity bracket as a pair of minimum and maximum quantity in the 'From' and 'To' fields respectively.</span></span>  
15. <span data-ttu-id="418f5-132">No campo Valor em moeda, insira um preço.</span><span class="sxs-lookup"><span data-stu-id="418f5-132">In the Amount in currency field, enter a price.</span></span>
16. <span data-ttu-id="418f5-133">No campo A partir da data, insira uma data a partir da qual esse contrato será válido.</span><span class="sxs-lookup"><span data-stu-id="418f5-133">In the From date field, enter a date from which this agreement will be valid.</span></span>
17. <span data-ttu-id="418f5-134">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="418f5-134">Click Save.</span></span>
18. <span data-ttu-id="418f5-135">Clique em Validar.</span><span class="sxs-lookup"><span data-stu-id="418f5-135">Click Validate.</span></span>
19. <span data-ttu-id="418f5-136">Clique em Validar as linhas selecionadas.</span><span class="sxs-lookup"><span data-stu-id="418f5-136">Click Validate selected lines.</span></span>
20. <span data-ttu-id="418f5-137">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="418f5-137">Click OK.</span></span>
21. <span data-ttu-id="418f5-138">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="418f5-138">Click Post.</span></span>
22. <span data-ttu-id="418f5-139">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="418f5-139">Click OK.</span></span>

## <a name="view-trade-agreements-for-a-product"></a><span data-ttu-id="418f5-140">Exibir contratos comerciais para um produto</span><span class="sxs-lookup"><span data-stu-id="418f5-140">View trade agreements for a product</span></span>
1. <span data-ttu-id="418f5-141">Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="418f5-141">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="418f5-142">Na lista, localize e selecione o produto cujo preço você acabou de atualizar.</span><span class="sxs-lookup"><span data-stu-id="418f5-142">In the list, find and select the product whose price you have just updated.</span></span>
3. <span data-ttu-id="418f5-143">No Painel de Ação, clique em Vender.</span><span class="sxs-lookup"><span data-stu-id="418f5-143">On the Action Pane, click Sell.</span></span>
4. <span data-ttu-id="418f5-144">Clique em Exibir contratos comerciais.</span><span class="sxs-lookup"><span data-stu-id="418f5-144">Click View trade agreements.</span></span>
    * <span data-ttu-id="418f5-145">Revise os detalhes do contrato comercial de preço que acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="418f5-145">Review the details of the price trade agreement you have just created.</span></span>    
5. <span data-ttu-id="418f5-146">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="418f5-146">Close the page.</span></span>


