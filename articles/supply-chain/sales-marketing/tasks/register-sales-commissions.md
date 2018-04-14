--- 
title: "Registrar comissões de vendas"
description: "Este procedimento mostra como comissões de vendas são calculadas e registradas."
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: d21f9047dcea0af59c24339ebb57e8eabe3950d4
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---
# <a name="register-sales-commissions"></a><span data-ttu-id="da113-103">Registrar comissões de vendas</span><span class="sxs-lookup"><span data-stu-id="da113-103">Register sales commissions</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="da113-104">Este procedimento mostra como comissões de vendas são calculadas e registradas.</span><span class="sxs-lookup"><span data-stu-id="da113-104">This procedure shows you how sales commissions are calculated and registered.</span></span> <span data-ttu-id="da113-105">Você pode executar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="da113-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="da113-106">Antes de iniciar este guia, faça o guia chamado "Configurar regras de comissão de venda" para se certificar de que você tem toda a configuração de cálculo de comissões necessária.</span><span class="sxs-lookup"><span data-stu-id="da113-106">Before starting this guide, run the guide called "Set up sales commission rules" to make sure that you have all the necessary commission calculation setup.</span></span>

<span data-ttu-id="da113-107">Anote os números de cliente e item que você escolheu para o processo de comissão e use-os quando for solicitada a criação de uma ordem de venda neste guia.</span><span class="sxs-lookup"><span data-stu-id="da113-107">Take note of the customer and item numbers that you have chosen for the commission process and use them when asked to create a sales order in this guide.</span></span>


## <a name="invoice-a-sales-order-that-qualifies-a-salesperson-for-a-commission"></a><span data-ttu-id="da113-108">Faturar uma ordem de venda que qualifique um vendedor para uma comissão</span><span class="sxs-lookup"><span data-stu-id="da113-108">Invoice a sales order that qualifies a salesperson for a commission</span></span>
1. <span data-ttu-id="da113-109">Vá para Vendas e marketing > Ordens de venda > Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="da113-109">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="da113-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="da113-110">Click New.</span></span>
3. <span data-ttu-id="da113-111">No campo Conta do cliente, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="da113-111">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="da113-112">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="da113-112">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="da113-113">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="da113-113">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="da113-114">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="da113-114">Click OK.</span></span>
7. <span data-ttu-id="da113-115">No Painel de Ação, clique em Opções.</span><span class="sxs-lookup"><span data-stu-id="da113-115">On the Action Pane, click Options.</span></span>
8. <span data-ttu-id="da113-116">Clique em Alterar exibição.</span><span class="sxs-lookup"><span data-stu-id="da113-116">Click Change view.</span></span>
9. <span data-ttu-id="da113-117">Clique em Exibição do cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="da113-117">Click Header view.</span></span>
10. <span data-ttu-id="da113-118">Expandir a seção Instalação.</span><span class="sxs-lookup"><span data-stu-id="da113-118">Expand the Setup section.</span></span>
    * <span data-ttu-id="da113-119">O valor no campo Grupo de vendas representa um grupo com um ou mais representantes de vendas atribuídos a ele.</span><span class="sxs-lookup"><span data-stu-id="da113-119">The value in the Sales group field represents a group with one or more sales representatives assigned to it.</span></span> <span data-ttu-id="da113-120">As pessoas no grupo são aquelas que receberão comissões quando a ordem é faturada, conforme distribuição e taxas predefinidas.</span><span class="sxs-lookup"><span data-stu-id="da113-120">The people in the group are the ones who will receive commissions when the order is invoiced, as per predefined rates and distribution.</span></span>   <span data-ttu-id="da113-121">O valor é copiado do cartão Cliente, mas você pode alterá-lo se desejar.</span><span class="sxs-lookup"><span data-stu-id="da113-121">The value is copied from the Customer card, but you can change it if you wish.</span></span>  <span data-ttu-id="da113-122">O grupo de vendas também é copiado na linha da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="da113-122">The Sales group is also copied to the sales order line.</span></span> <span data-ttu-id="da113-123">Você pode alterá-lo para que ele possa ser diferente daquele no cabeçalho e/ou entre linhas.</span><span class="sxs-lookup"><span data-stu-id="da113-123">You can change it so that it can differ from the one in the header and/or between lines.</span></span>  
    * <span data-ttu-id="da113-124">O valor no campo Grupo de comissões representa um grupo que você criou para um ou mais clientes com o objetivo de rastrear comissões.</span><span class="sxs-lookup"><span data-stu-id="da113-124">The value in the Commission group field represents a group that you have created for one or more customers with the purpose of tracking commissions.</span></span>   <span data-ttu-id="da113-125">O valor é copiado do cartão Cliente, mas você pode alterá-lo se desejar.</span><span class="sxs-lookup"><span data-stu-id="da113-125">The value is copied from the Customer card, but you can change it if you wish.</span></span>   
11. <span data-ttu-id="da113-126">No Painel de Ação, clique em Opções.</span><span class="sxs-lookup"><span data-stu-id="da113-126">On the Action Pane, click Options.</span></span>
12. <span data-ttu-id="da113-127">Clique em Alterar exibição.</span><span class="sxs-lookup"><span data-stu-id="da113-127">Click Change view.</span></span>
13. <span data-ttu-id="da113-128">Clique em Exibição em linha.</span><span class="sxs-lookup"><span data-stu-id="da113-128">Click Line view.</span></span>
14. <span data-ttu-id="da113-129">No campo Número de item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="da113-129">In the Item number field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="da113-130">Na lista, selecione o item que você definiu para comissões.</span><span class="sxs-lookup"><span data-stu-id="da113-130">In the list, select the item you have set up for commissions.</span></span> 
16. <span data-ttu-id="da113-131">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="da113-131">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="da113-132">Anote o valor líquido da linha.</span><span class="sxs-lookup"><span data-stu-id="da113-132">Take note of the line's Net amount.</span></span> <span data-ttu-id="da113-133">Ele representa a receita de vendas, que, nesse exemplo, é a base para o cálculo de comissões.</span><span class="sxs-lookup"><span data-stu-id="da113-133">It represents the sales revenue, which in this example is the basis for commission calculation.</span></span>  
17. <span data-ttu-id="da113-134">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="da113-134">Click Save.</span></span>
18. <span data-ttu-id="da113-135">No Painel de Ação, clique em Fatura.</span><span class="sxs-lookup"><span data-stu-id="da113-135">On the Action Pane, click Invoice.</span></span>
19. <span data-ttu-id="da113-136">Clique em Fatura.</span><span class="sxs-lookup"><span data-stu-id="da113-136">Click Invoice.</span></span>
20. <span data-ttu-id="da113-137">Expanda a seção Parâmetros.</span><span class="sxs-lookup"><span data-stu-id="da113-137">Expand the Parameters section.</span></span>
21. <span data-ttu-id="da113-138">No campo Quantidade, selecione 'Tudo'.</span><span class="sxs-lookup"><span data-stu-id="da113-138">In the Quantity field, select 'All'.</span></span>
22. <span data-ttu-id="da113-139">Selecione Sim no campo Lançamento.</span><span class="sxs-lookup"><span data-stu-id="da113-139">Select Yes in the Posting field.</span></span>
23. <span data-ttu-id="da113-140">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="da113-140">Click OK.</span></span>
24. <span data-ttu-id="da113-141">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="da113-141">Click OK.</span></span>
    * <span data-ttu-id="da113-142">Pode levar um minuto ou mais para lançar a transação.</span><span class="sxs-lookup"><span data-stu-id="da113-142">It may take a minute or so to post the transaction.</span></span> <span data-ttu-id="da113-143">Deixe que o processo seja concluído e não feche a página.</span><span class="sxs-lookup"><span data-stu-id="da113-143">Allow the processing to complete and don’t close the page.</span></span>  

## <a name="review-the-registered-sales-commissions"></a><span data-ttu-id="da113-144">Revisar as comissões de vendas registradas</span><span class="sxs-lookup"><span data-stu-id="da113-144">Review the registered sales commissions</span></span>
1. <span data-ttu-id="da113-145">No Painel de Ação, clique em Fatura.</span><span class="sxs-lookup"><span data-stu-id="da113-145">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="da113-146">Clique em Fatura.</span><span class="sxs-lookup"><span data-stu-id="da113-146">Click Invoice.</span></span>
3. <span data-ttu-id="da113-147">No Painel de Ação, clique em Fatura.</span><span class="sxs-lookup"><span data-stu-id="da113-147">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="da113-148">Clique em Transações de comissão.</span><span class="sxs-lookup"><span data-stu-id="da113-148">Click Commission transactions.</span></span>
    * <span data-ttu-id="da113-149">A guia Visão geral exibe linhas que representam os valores de comissões a serem pagos aos representantes de venda que estão associados com a ordem de venda faturada.</span><span class="sxs-lookup"><span data-stu-id="da113-149">The Overview tab displays lines representing the commission amounts payable to sales representatives who are associated with the invoiced sales order.</span></span> <span data-ttu-id="da113-150">Vamos revisar os detalhes.</span><span class="sxs-lookup"><span data-stu-id="da113-150">Let's review the details.</span></span>     
    * <span data-ttu-id="da113-151">Se você usou o guia "Configurar regras de comissão de venda" para configurar o grupo de vendas por comissão, dois vendedores receberão comissões de vendas, e a comissão é dividida igualmente entre eles.</span><span class="sxs-lookup"><span data-stu-id="da113-151">If you used the "Set up sales commission rules" guide to set up the Commission sales group, there are two sales people to receive a sales commissions, and the commission is split equally between them.</span></span>  
    * <span data-ttu-id="da113-152">Nesse exemplo, o valor total da comissão é calculado como uma porcentagem da receita de vendas (o valor líquido da linha da ordem).</span><span class="sxs-lookup"><span data-stu-id="da113-152">In this example, the total amount of the commission is calculated as a percentage of the sales revenue (the net amount of order line).</span></span>   
5. <span data-ttu-id="da113-153">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="da113-153">Close the page.</span></span>
6. <span data-ttu-id="da113-154">Clique em Comprovante.</span><span class="sxs-lookup"><span data-stu-id="da113-154">Click Voucher.</span></span>
    * <span data-ttu-id="da113-155">Você pode revisar as transações do comprovante quanto aos valores de comissão que foram lançados na despesa de comissão predefinida e nas contas de comissão a pagar.</span><span class="sxs-lookup"><span data-stu-id="da113-155">You can review the voucher transactions for the commission amounts that have been posted to the predefined commission expense and commission payable accounts.</span></span>  


