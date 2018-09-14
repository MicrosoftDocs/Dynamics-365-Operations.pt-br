--- 
title: Confirmar ordens de venda
description: Este procedimento demonstra como confirmar ordens de venda.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesTableListPage, SalesTable, SalesEditLines,  SrsReportViewerForm, CustConfirmJournal, SysQueryForm, SysQueryFieldLookUp, SysLookup, SalesParmIdLookup
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: db475cf967bebec2d442aaa864800d920cf0ab81
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2018

---
# <a name="confirm-sales-orders"></a><span data-ttu-id="de0c5-103">Confirmar ordens de venda</span><span class="sxs-lookup"><span data-stu-id="de0c5-103">Confirm sales orders</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="de0c5-104">Este procedimento demonstra como confirmar ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="de0c5-104">This procedure demonstrates how to confirm sales orders.</span></span> <span data-ttu-id="de0c5-105">Será mostrado a você como confirmar uma única ordem, e como confirmar várias ordens de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="de0c5-105">You’ll be shown how to confirm a single order, and how to confirm multiple orders at once.</span></span> <span data-ttu-id="de0c5-106">Essas tarefas seriam normalmente realizadas por um processador de ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="de0c5-106">These tasks would typically be carried out by a sales order processor.</span></span> <span data-ttu-id="de0c5-107">Você pode usar esse procedimento na empresa de dados demonstrativos USMF ou nos seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="de0c5-107">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="de0c5-108">Antes de começar, verifique se existem várias ordens de venda em aberto para o mesmo cliente.</span><span class="sxs-lookup"><span data-stu-id="de0c5-108">Before you start, make sure there are several open sales orders for the same customer.</span></span> <span data-ttu-id="de0c5-109">Se você estiver usando USMF, é possível usar o cliente US-027.</span><span class="sxs-lookup"><span data-stu-id="de0c5-109">If you’re using USMF, you can use customer US-027.</span></span>


## <a name="confirm-a-single-sales-order"></a><span data-ttu-id="de0c5-110">Confirmar uma única ordem de venda</span><span class="sxs-lookup"><span data-stu-id="de0c5-110">Confirm a single sales order</span></span>
1. <span data-ttu-id="de0c5-111">Vá para Vendas e marketing > Ordens de venda > Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="de0c5-111">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="de0c5-112">Na lista, localize e selecione a ordem que você deseja confirmar.</span><span class="sxs-lookup"><span data-stu-id="de0c5-112">In the list, find and select the order that you want to confirm.</span></span>
3. <span data-ttu-id="de0c5-113">Clique no link no número da ordem de venda para abrir a ordem selecionada.</span><span class="sxs-lookup"><span data-stu-id="de0c5-113">Click the link on the sales order number to open the selected order.</span></span>
4. <span data-ttu-id="de0c5-114">No Painel de Ação, clique em Vender.</span><span class="sxs-lookup"><span data-stu-id="de0c5-114">On the Action Pane, click Sell.</span></span>
5. <span data-ttu-id="de0c5-115">Clique em Confirmar ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="de0c5-115">Click Confirm sales order.</span></span>
6. <span data-ttu-id="de0c5-116">Expanda e recolha a seção Parâmetros.</span><span class="sxs-lookup"><span data-stu-id="de0c5-116">Expand or collapse the Parameters section.</span></span>
    * <span data-ttu-id="de0c5-117">Verifique se o campo de Lançamento Sim está ativo.</span><span class="sxs-lookup"><span data-stu-id="de0c5-117">Make sure that the Posting Yes field is active.</span></span>  
7. <span data-ttu-id="de0c5-118">Defina a opção de confirmação Imprimir como Sim.</span><span class="sxs-lookup"><span data-stu-id="de0c5-118">Set the Print confirmation option to Yes.</span></span>
    * <span data-ttu-id="de0c5-119">O campo Verificar limite de crédito especifica o método usado para calcular o crédito restante de um cliente.</span><span class="sxs-lookup"><span data-stu-id="de0c5-119">The Check credit limit field specifies the method that’s used to calculate a customer's remaining credit.</span></span> <span data-ttu-id="de0c5-120">Por padrão, ele é copiado da página Parâmetros de contas a receber.</span><span class="sxs-lookup"><span data-stu-id="de0c5-120">By default, it’s copied from the Accounts receivable parameters page.</span></span> <span data-ttu-id="de0c5-121">Se desejar ignorar a verificação de limite de crédito ao confirmar uma ordem de venda específica, configure Verificar limite de crédito para Nenhum.</span><span class="sxs-lookup"><span data-stu-id="de0c5-121">If you want to skip the credit limit check when confirming a specific sales order, set the Check credit limit to None.</span></span> <span data-ttu-id="de0c5-122">No entanto, você deve estar ciente de que mesmo com este campo definido como Nenhum, a verificação de limite de crédito será executada se a opção Limite de crédito obrigatório estiver selecionada nos dados mestre do cliente.</span><span class="sxs-lookup"><span data-stu-id="de0c5-122">However, you should be aware that even with if this field is set to None, the credit limit check will still be performed if the Mandatory credit limit option is selected on the customer master data.</span></span>  
8. <span data-ttu-id="de0c5-123">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="de0c5-123">Click OK.</span></span>
9. <span data-ttu-id="de0c5-124">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="de0c5-124">Click Yes.</span></span>
10. <span data-ttu-id="de0c5-125">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="de0c5-125">Close the page.</span></span>
11. <span data-ttu-id="de0c5-126">No Painel de Ação, clique em Opções.</span><span class="sxs-lookup"><span data-stu-id="de0c5-126">On the Action Pane, click Options.</span></span>
12. <span data-ttu-id="de0c5-127">Clique em Alterar exibição.</span><span class="sxs-lookup"><span data-stu-id="de0c5-127">Click Change view.</span></span>
13. <span data-ttu-id="de0c5-128">Clique em Exibição do cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="de0c5-128">Click Header view.</span></span>
    * <span data-ttu-id="de0c5-129">Quando uma ordem é confirmada, o Status do documento será definido como Confirmação.</span><span class="sxs-lookup"><span data-stu-id="de0c5-129">When an order is confirmed, the Document status is set to Confirmation.</span></span>  
14. <span data-ttu-id="de0c5-130">No Painel de Ação, clique em Vender.</span><span class="sxs-lookup"><span data-stu-id="de0c5-130">On the Action Pane, click Sell.</span></span>
15. <span data-ttu-id="de0c5-131">Clique em Confirmação de ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="de0c5-131">Click Sales order confirmation.</span></span>
16. <span data-ttu-id="de0c5-132">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="de0c5-132">Close the page.</span></span>

## <a name="confirm-multiple-sales-orders-at-once"></a><span data-ttu-id="de0c5-133">Confirmar várias ordens de venda de uma vez</span><span class="sxs-lookup"><span data-stu-id="de0c5-133">Confirm multiple sales orders at once</span></span>
1. <span data-ttu-id="de0c5-134">Vá para Vendas e marketing > Ordens de venda > Confirmação de ordem > Confirmar ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="de0c5-134">Go to Sales and marketing > Sales orders > Order confirmation > Confirm sales order.</span></span>
2. <span data-ttu-id="de0c5-135">Clique em Selecionar.</span><span class="sxs-lookup"><span data-stu-id="de0c5-135">Click Select.</span></span>
3. <span data-ttu-id="de0c5-136">Na lista da aba Faixa, localize e selecione o registro que referencia o campo Conta de cliente.</span><span class="sxs-lookup"><span data-stu-id="de0c5-136">In the list on the Range tab, find and select the record that references the Customer account field.</span></span>
4. <span data-ttu-id="de0c5-137">No campo Critérios, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="de0c5-137">In the Criteria field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="de0c5-138">Na lista, localize e selecione a conta de cliente que contêm várias ordens que você deseja confirmar em massa.</span><span class="sxs-lookup"><span data-stu-id="de0c5-138">In the list, find and select the customer account that has multiple orders which you want to mass confirm.</span></span>
    * <span data-ttu-id="de0c5-139">Se você estiver usando USMF, é possível selecionar a conta US-027.</span><span class="sxs-lookup"><span data-stu-id="de0c5-139">If you’re using USMF, you can select account US-027.</span></span>  
6. <span data-ttu-id="de0c5-140">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="de0c5-140">Click OK.</span></span>
    * <span data-ttu-id="de0c5-141">A aba Visão geral exibe uma lista de ordens que correspondem aos critérios de consulta.</span><span class="sxs-lookup"><span data-stu-id="de0c5-141">The Overview tab displays a list of the orders that match the query criteria.</span></span> <span data-ttu-id="de0c5-142">Essas serão incluídas na confirmação.</span><span class="sxs-lookup"><span data-stu-id="de0c5-142">These will be included in the confirmation.</span></span>  
    * <span data-ttu-id="de0c5-143">O campo Atualização resumida para especifica o parâmetro pelo qual as diversas ordens devem ser resumidas em um documento de confirmação.</span><span class="sxs-lookup"><span data-stu-id="de0c5-143">The Summary update for field specifies the parameter by which multiple orders are to be summarized into one confirmation document.</span></span> <span data-ttu-id="de0c5-144">Por padrão, a opção é copiada da configuração Valores padrão para atualização resumida na página Parâmetro de contas a receber.</span><span class="sxs-lookup"><span data-stu-id="de0c5-144">By default, the option is copied from the Default values for summary update setting on the Accounts receivable parameters page.</span></span>  
7. <span data-ttu-id="de0c5-145">No campo Atualização resumida para, selecione 'Ordem'.</span><span class="sxs-lookup"><span data-stu-id="de0c5-145">In the Summary update for field, select 'Order'.</span></span>
    * <span data-ttu-id="de0c5-146">Os parâmetros mínimos requeridos para criar atualizações resumidas são Conta da fatura e Moeda.</span><span class="sxs-lookup"><span data-stu-id="de0c5-146">The minimum parameters that are required to create summary updates are Invoice account and Currency.</span></span> <span data-ttu-id="de0c5-147">Isso significa que atualizações resumidas que têm tanto contas de fatura como moedas diferentes não serão permitidas.</span><span class="sxs-lookup"><span data-stu-id="de0c5-147">This means that summary updates that have different invoice accounts and different currencies are not allowed.</span></span> <span data-ttu-id="de0c5-148">Parâmetros adicionais podem ser configurados na página Parâmetros da atualização resumida que pode ser acessada pela página Parâmetros de contas a receber.</span><span class="sxs-lookup"><span data-stu-id="de0c5-148">Additional parameters can be set up in the Summary update parameters page which is accessible from the Accounts receivable parameters page.</span></span>  
8. <span data-ttu-id="de0c5-149">No campo Ordem de venda, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="de0c5-149">In the Sales order field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="de0c5-150">Na lista, selecione o número da ordem que você deseja que seja a ordem resumida.</span><span class="sxs-lookup"><span data-stu-id="de0c5-150">In the list, select the order number that you want to be the summary order.</span></span>
10. <span data-ttu-id="de0c5-151">Clique em Organizar.</span><span class="sxs-lookup"><span data-stu-id="de0c5-151">Click Arrange.</span></span>
11. <span data-ttu-id="de0c5-152">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="de0c5-152">Click OK.</span></span>
12. <span data-ttu-id="de0c5-153">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="de0c5-153">Click OK.</span></span>


