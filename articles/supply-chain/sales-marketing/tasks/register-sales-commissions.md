---
title: Registrar comissões de vendas
description: Este tópico explica como comissões de vendas são calculadas e registradas.
author: omulvad
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  CustInvoiceJournal, CommissionTrans, LedgerTransVoucher
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: db27255c74c55b10680594ad23424253e4c3f79e
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867044"
---
# <a name="register-sales-commissions"></a><span data-ttu-id="d9d02-103">Registrar comissões de vendas</span><span class="sxs-lookup"><span data-stu-id="d9d02-103">Register sales commissions</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d9d02-104">Este tópico explica como comissões de vendas são calculadas e registradas.</span><span class="sxs-lookup"><span data-stu-id="d9d02-104">This topic explains how sales commissions are calculated and registered.</span></span> <span data-ttu-id="d9d02-105">Você pode executar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="d9d02-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="d9d02-106">Antes de iniciar este guia, faça o guia chamado "Configurar regras de comissão de venda" para se certificar de que você tem toda a configuração de cálculo de comissões necessária.</span><span class="sxs-lookup"><span data-stu-id="d9d02-106">Before starting this guide, run the guide called "Set up sales commission rules" to make sure that you have all the necessary commission calculation setup.</span></span>

<span data-ttu-id="d9d02-107">Anote os números de cliente e item que você escolheu para o processo de comissão e use-os quando for solicitada a criação de uma ordem de venda neste guia.</span><span class="sxs-lookup"><span data-stu-id="d9d02-107">Take note of the customer and item numbers that you have chosen for the commission process and use them when asked to create a sales order in this guide.</span></span>


## <a name="invoice-a-sales-order-that-qualifies-a-salesperson-for-a-commission"></a><span data-ttu-id="d9d02-108">Faturar uma ordem de venda que qualifique um vendedor para uma comissão</span><span class="sxs-lookup"><span data-stu-id="d9d02-108">Invoice a sales order that qualifies a salesperson for a commission</span></span>
1. <span data-ttu-id="d9d02-109">No painel de navegação, acesse **Módulos > Vendas e marketing > Ordens de venda > Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="d9d02-109">In the navigation pane, go to **Modules > Sales and marketing > Sales orders > All sales orders**.</span></span>
2. <span data-ttu-id="d9d02-110">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="d9d02-110">Select **New**.</span></span>
3. <span data-ttu-id="d9d02-111">No campo **Conta do cliente**, selecione o registro desejado no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="d9d02-111">In the **Customer account** field, select the desired record from the drop-down menu.</span></span>
4. <span data-ttu-id="d9d02-112">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="d9d02-112">Select **OK**.</span></span>
5. <span data-ttu-id="d9d02-113">No Painel de Ações, selecione **Opções**.</span><span class="sxs-lookup"><span data-stu-id="d9d02-113">On the Action Pane, select **Options**.</span></span>
6. <span data-ttu-id="d9d02-114">Selecione **Alterar exibição**.</span><span class="sxs-lookup"><span data-stu-id="d9d02-114">Select **Change view**.</span></span>
7. <span data-ttu-id="d9d02-115">Selecione **Exibição do cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="d9d02-115">Select **Header view**.</span></span>
8. <span data-ttu-id="d9d02-116">Expanda a seção **Instalação**.</span><span class="sxs-lookup"><span data-stu-id="d9d02-116">Expand the **Setup** section.</span></span>

    - <span data-ttu-id="d9d02-117">O valor no campo **Grupo de vendas** representa um grupo com um ou mais representantes de vendas atribuídos a ele.</span><span class="sxs-lookup"><span data-stu-id="d9d02-117">The value in the **Sales group** field represents a group with one or more sales representatives assigned to it.</span></span> <span data-ttu-id="d9d02-118">As pessoas no grupo são aquelas que receberão comissões quando a ordem é faturada, conforme distribuição e taxas predefinidas.</span><span class="sxs-lookup"><span data-stu-id="d9d02-118">The people in the group are the ones who will receive commissions when the order is invoiced, as per predefined rates and distribution.</span></span>   
    - <span data-ttu-id="d9d02-119">O valor é copiado do cartão Cliente, mas você pode alterá-lo se desejar.</span><span class="sxs-lookup"><span data-stu-id="d9d02-119">The value is copied from the Customer card, but you can change it if you wish.</span></span>  
    - <span data-ttu-id="d9d02-120">O grupo de vendas também é copiado na linha da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="d9d02-120">The Sales group is also copied to the sales order line.</span></span> <span data-ttu-id="d9d02-121">Você pode alterá-lo para que ele possa ser diferente daquele no cabeçalho e/ou entre linhas.</span><span class="sxs-lookup"><span data-stu-id="d9d02-121">You can change it so that it can differ from the one in the header and/or between lines.</span></span>  
    - <span data-ttu-id="d9d02-122">O valor no campo **Grupo de comissões** representa um grupo que você criou para um ou mais clientes com o objetivo de rastrear comissões.</span><span class="sxs-lookup"><span data-stu-id="d9d02-122">The value in the **Commission group** field represents a group that you have created for one or more customers with the purpose of tracking commissions.</span></span>   
    - <span data-ttu-id="d9d02-123">O valor é copiado do cartão Cliente, mas você pode alterá-lo se desejar.</span><span class="sxs-lookup"><span data-stu-id="d9d02-123">The value is copied from the Customer card, but you can change it if you wish.</span></span>   

9. <span data-ttu-id="d9d02-124">No Painel de Ações, selecione **Opções**.</span><span class="sxs-lookup"><span data-stu-id="d9d02-124">On the Action Pane, select **Options**.</span></span>
10. <span data-ttu-id="d9d02-125">Selecione **Alterar exibição**.</span><span class="sxs-lookup"><span data-stu-id="d9d02-125">Select **Change view**.</span></span>
11. <span data-ttu-id="d9d02-126">Selecione **Exibição de linha**.</span><span class="sxs-lookup"><span data-stu-id="d9d02-126">Select **Line view**.</span></span>
12. <span data-ttu-id="d9d02-127">No menu suspenso do campo **Número do item**, selecione o item que você configurou em comissões.</span><span class="sxs-lookup"><span data-stu-id="d9d02-127">In the drop down menu of the **Item number** field, select the item you have set up for commissions.</span></span> 
13. <span data-ttu-id="d9d02-128">No campo **Quantidade.**, insira um número</span><span class="sxs-lookup"><span data-stu-id="d9d02-128">In the **Quantity** field, enter a number.</span></span> <span data-ttu-id="d9d02-129">Anote o valor líquido da linha.</span><span class="sxs-lookup"><span data-stu-id="d9d02-129">Take note of the line's Net amount.</span></span> <span data-ttu-id="d9d02-130">Ele representa a receita de vendas, que, nesse exemplo, é a base para o cálculo de comissões.</span><span class="sxs-lookup"><span data-stu-id="d9d02-130">It represents the sales revenue, which in this example is the basis for commission calculation.</span></span>  
14. <span data-ttu-id="d9d02-131">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d9d02-131">Select **Save**.</span></span>
15. <span data-ttu-id="d9d02-132">No Painel de Ação, selecione **Fatura**.</span><span class="sxs-lookup"><span data-stu-id="d9d02-132">On the Action Pane, select **Invoice**.</span></span>
16. <span data-ttu-id="d9d02-133">Selecione **Fatura**.</span><span class="sxs-lookup"><span data-stu-id="d9d02-133">Select **Invoice**.</span></span>
17. <span data-ttu-id="d9d02-134">Expanda a seção **Parâmetros**.</span><span class="sxs-lookup"><span data-stu-id="d9d02-134">Expand the **Parameters** section.</span></span>
18. <span data-ttu-id="d9d02-135">No campo **Quantidade**, selecione **Todas**.</span><span class="sxs-lookup"><span data-stu-id="d9d02-135">In the **Quantity** field, select **All**.</span></span>
19. <span data-ttu-id="d9d02-136">Selecione **Sim** no campo **Lançamento**.</span><span class="sxs-lookup"><span data-stu-id="d9d02-136">Select **Yes** in the **Posting** field.</span></span>
20. <span data-ttu-id="d9d02-137">Selecione **OK** e depois **OK** no próximo painel.</span><span class="sxs-lookup"><span data-stu-id="d9d02-137">Select **OK**, then select **OK** in the next pane.</span></span> <span data-ttu-id="d9d02-138">Pode levar um minuto ou mais para lançar a transação.</span><span class="sxs-lookup"><span data-stu-id="d9d02-138">It may take a minute or so to post the transaction.</span></span> <span data-ttu-id="d9d02-139">Deixe que o processo seja concluído e não feche a página.</span><span class="sxs-lookup"><span data-stu-id="d9d02-139">Allow the processing to complete and don’t close the page.</span></span>  

## <a name="review-the-registered-sales-commissions"></a><span data-ttu-id="d9d02-140">Revisar as comissões de vendas registradas</span><span class="sxs-lookup"><span data-stu-id="d9d02-140">Review the registered sales commissions</span></span>
1. <span data-ttu-id="d9d02-141">No painel de ações, selecione **Fatura** e depois **Fatura** novamente.</span><span class="sxs-lookup"><span data-stu-id="d9d02-141">On the Action Pane, select **Invoice**, then select **Invoice** again.</span></span>
2. <span data-ttu-id="d9d02-142">No painel de ações, selecione **Fatura** e depois **Transações de comissão**.</span><span class="sxs-lookup"><span data-stu-id="d9d02-142">On the Action Pane, select **Invoice**, then select **Commission transactions**.</span></span>

    - <span data-ttu-id="d9d02-143">A guia **Visão geral** exibe linhas que representam os valores de comissões a serem pagos aos representantes de venda que estão associados com a ordem de venda faturada.</span><span class="sxs-lookup"><span data-stu-id="d9d02-143">The **Overview** tab displays lines representing the commission amounts payable to sales representatives who are associated with the invoiced sales order.</span></span> <span data-ttu-id="d9d02-144">Vamos revisar os detalhes.</span><span class="sxs-lookup"><span data-stu-id="d9d02-144">Let's review the details.</span></span>  
    - <span data-ttu-id="d9d02-145">Se você usou o guia "Configurar regras de comissão de venda" para configurar o grupo de **vendas por comissão**, dois vendedores receberão comissões de vendas, e a comissão é dividida igualmente entre eles.</span><span class="sxs-lookup"><span data-stu-id="d9d02-145">If you used the "Set up sales commission rules" guide to set up the **Commission sales** group, there are two sales people to receive a sales commissions, and the commission is split equally between them.</span></span>  
    - <span data-ttu-id="d9d02-146">Nesse exemplo, o valor total da comissão é calculado como uma porcentagem da receita de vendas (o valor líquido da linha da ordem).</span><span class="sxs-lookup"><span data-stu-id="d9d02-146">In this example, the total amount of the commission is calculated as a percentage of the sales revenue (the net amount of order line).</span></span>  
3. <span data-ttu-id="d9d02-147">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d9d02-147">Close the page.</span></span>
4. <span data-ttu-id="d9d02-148">Selecione **Comprovante**.</span><span class="sxs-lookup"><span data-stu-id="d9d02-148">Select **Voucher**.</span></span> <span data-ttu-id="d9d02-149">Você pode revisar as transações do comprovante quanto aos valores de comissão que foram lançados na despesa de comissão predefinida e nas contas de comissão a pagar.</span><span class="sxs-lookup"><span data-stu-id="d9d02-149">You can review the voucher transactions for the commission amounts that have been posted to the predefined commission expense and commission payable accounts.</span></span>  

