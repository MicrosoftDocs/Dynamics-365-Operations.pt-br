--- 
title: "Criar e editar cotações de venda"
description: "Este procedimento demonstrativos como criar e atualizar uma cotação de venda."
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesQuotationListPage, SalesCreateQuotation, SalesQuotationTable, SalesQuotationTotals, SalesQuotationPriceSimulation, SalesQuotationEditLines, SrsReportViewerForm, smmSetNumSeqIfManual, CustTable, SalesTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 5b5618a815aaff12dd366523920ed275801b3b16
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2018

---
# <a name="create-and-edit-sales-quotations"></a><span data-ttu-id="b8c92-103">Criar e editar cotações de venda</span><span class="sxs-lookup"><span data-stu-id="b8c92-103">Create and edit sales quotations</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b8c92-104">Este procedimento demonstrativos como criar e atualizar uma cotação de venda.</span><span class="sxs-lookup"><span data-stu-id="b8c92-104">This procedure demonstrates how to create and update a sales quotation.</span></span> <span data-ttu-id="b8c92-105">Você pode realizar esse procedimento em seus próprios dados ou na empresa USMF de dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="b8c92-105">You can run this procedure on your own data or in demo data company USMF.</span></span>


## <a name="create-a-sales-quotation"></a><span data-ttu-id="b8c92-106">Criar uma cotação de venda</span><span class="sxs-lookup"><span data-stu-id="b8c92-106">Create a sales quotation</span></span>
1. <span data-ttu-id="b8c92-107">Vá para Vendas e marketing > Cotações de venda > Todas as cotações.</span><span class="sxs-lookup"><span data-stu-id="b8c92-107">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
2. <span data-ttu-id="b8c92-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="b8c92-108">Click New.</span></span>
3. <span data-ttu-id="b8c92-109">No campo Tipo de conta, selecione 'Cliente potencial'.</span><span class="sxs-lookup"><span data-stu-id="b8c92-109">In the Account type field, select 'Prospect'.</span></span>
4. <span data-ttu-id="b8c92-110">No campo Cliente potencial, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b8c92-110">In the Prospect field, enter or select a value.</span></span>
5. <span data-ttu-id="b8c92-111">Expanda a seção Geral.</span><span class="sxs-lookup"><span data-stu-id="b8c92-111">Expand the General section.</span></span>
    * <span data-ttu-id="b8c92-112">Como você optou por criar uma cotação da área Vendas e Marketing, o tipo é automaticamente definido como Cotação de venda.</span><span class="sxs-lookup"><span data-stu-id="b8c92-112">Because you chose to create a quotation from the Sales and Marketing area, the type is automatically set to Sales quotation.</span></span> <span data-ttu-id="b8c92-113">Para criar uma cotação para um projeto, você deverá acessá-lo do módulo Gerenciamento e contabilidade de projeto.</span><span class="sxs-lookup"><span data-stu-id="b8c92-113">To create a quotation for a project you must access it from the Project management and accounting module.</span></span>   
6. <span data-ttu-id="b8c92-114">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b8c92-114">Click OK.</span></span>
    * <span data-ttu-id="b8c92-115">Os campos e as ações nas linhas da cotação são muito semelhantes aos das linhas de ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="b8c92-115">The fields and actions on the quotation lines are very similar to the ones on the sales order lines.</span></span>   <span data-ttu-id="b8c92-116">Como as ordens de venda, as cotações podem ser criadas para um item específico, ou quando o número do item não é conhecido ou não existe no momento da criação da cotação, as cotações podem ser criadas para uma categoria de vendas.</span><span class="sxs-lookup"><span data-stu-id="b8c92-116">Like sales orders, quotations can be created for a specific item or, when item number is not known or does not exist at the time of quotation creation, quotations can be created for a sales category.</span></span>  
7. <span data-ttu-id="b8c92-117">No campo Item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b8c92-117">In the Item field, enter or select a value.</span></span>
8. <span data-ttu-id="b8c92-118">No campo Item, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b8c92-118">In the Item field, type a value.</span></span>
9. <span data-ttu-id="b8c92-119">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b8c92-119">Close the page.</span></span>
10. <span data-ttu-id="b8c92-120">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="b8c92-120">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="b8c92-121">Se houver contratos comerciais válidos para o item selecionado na linha, o preço e os descontos aplicáveis serão copiados automaticamente para a linha de cotação.</span><span class="sxs-lookup"><span data-stu-id="b8c92-121">If there are valid trade agreements for the item selected on the line, the applicable price and discounts will be automatically copied to the quotation line.</span></span> <span data-ttu-id="b8c92-122">Certifique-se de que o campo Preço unitário contém um valor e você também pode inserir valores de desconto, se quiser.</span><span class="sxs-lookup"><span data-stu-id="b8c92-122">Make sure that the Unit price field contains a value and you can also enter discount values if you want to.</span></span>  
11. <span data-ttu-id="b8c92-123">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b8c92-123">Click Save.</span></span>
12. <span data-ttu-id="b8c92-124">No Painel de Ação, clique em Cotação de venda.</span><span class="sxs-lookup"><span data-stu-id="b8c92-124">On the Action Pane, click Sales quotation.</span></span>
13. <span data-ttu-id="b8c92-125">Clique em Totais.</span><span class="sxs-lookup"><span data-stu-id="b8c92-125">Click Totals.</span></span>
14. <span data-ttu-id="b8c92-126">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b8c92-126">Click OK.</span></span>
15. <span data-ttu-id="b8c92-127">Clique em Linha de cotação de venda.</span><span class="sxs-lookup"><span data-stu-id="b8c92-127">Click Sales quotation line.</span></span>
16. <span data-ttu-id="b8c92-128">Clique em Preços.</span><span class="sxs-lookup"><span data-stu-id="b8c92-128">Click Prices.</span></span>
    * <span data-ttu-id="b8c92-129">Na página Executar simulação de preço você pode tentar ajustar a receita esperada ou a lucratividade de sua cotação, com base no preço unitário, no valor do desconto, na porcentagem de desconto, no valor total, na margem ou no índice de contribuição.</span><span class="sxs-lookup"><span data-stu-id="b8c92-129">In the Run price simulation page you can experiment with adjusting the expected revenue or profitability of your quotation based on the desired unit price, discount amount, discount percentage, total amount, margin, or contribution ratio.</span></span>   <span data-ttu-id="b8c92-130">Quando estiver satisfeito com os números de destino, aplique a sugestão à linha de cotação e os campos relacionados ao preço serão atualizados adequadamente.</span><span class="sxs-lookup"><span data-stu-id="b8c92-130">When you are satisfied with the target figures, you apply the suggestion to the quotation line, and its price-related fields will be updated accordingly.</span></span>  
    * <span data-ttu-id="b8c92-131">Você pode criar quantas simulações de preço quiser.</span><span class="sxs-lookup"><span data-stu-id="b8c92-131">Y ou can create as many price simulations as you wish.</span></span> <span data-ttu-id="b8c92-132">Quando você clica em Novo, as condições de preço da linha da cotação atual serão copiadas para a página.</span><span class="sxs-lookup"><span data-stu-id="b8c92-132">When you click New, the price conditions from the current quotation line are copied to the page.</span></span> <span data-ttu-id="b8c92-133">Você poderá modificar os valores de quaisquer campos relacionados a preço para os de destino.</span><span class="sxs-lookup"><span data-stu-id="b8c92-133">You can then modify values in any of the price-related fields to the target ones.</span></span> <span data-ttu-id="b8c92-134">Uma alteração em um dos campos disparará o recálculo em todos os campos restantes.</span><span class="sxs-lookup"><span data-stu-id="b8c92-134">A change in one of the fields will trigger recalculation in all the other fields.</span></span> <span data-ttu-id="b8c92-135">Para que o sistema calcule o índice de margem de contribuição e de venda, o custo unitário do produto deve ser conhecido.</span><span class="sxs-lookup"><span data-stu-id="b8c92-135">In order for the system to calculate the sales margin and contribution ratio, the product's unit cost has to be known.</span></span> <span data-ttu-id="b8c92-136">Use a guia Preços simulados para obter uma exibição detalhada dos preços originais, das alterações propostas e seus efeitos nos totais da cotação.</span><span class="sxs-lookup"><span data-stu-id="b8c92-136">Use the Simulated prices tab for a detailed view of the original prices, proposed changes and their effect on the quotation totals.</span></span>   <span data-ttu-id="b8c92-137">Como regra geral, quando uma simulação que define um novo valor é aplicada à linha de cotação, o sistema recalcula e insere um novo valor no campo Preço unitário.</span><span class="sxs-lookup"><span data-stu-id="b8c92-137">As a general rule, when a simulation that sets a new amount is applied to the quotation line, the system recalculates and enters a new value in the Unit price field.</span></span> <span data-ttu-id="b8c92-138">Se a simulação for baseada em uma nova margem ou em um novo índice de contribuição, somente o campo Valor líquido será atualizado, e o Preço unitário ficará em branco.</span><span class="sxs-lookup"><span data-stu-id="b8c92-138">If the simulation is based on a new margin or a new contribution ratio, only the Net amount field is updated, and the Unit price is blank.</span></span> <span data-ttu-id="b8c92-139">Nos dois casos, quaisquer descontos que ocorreram na linha da cotação antes da simulação serão excluídos.</span><span class="sxs-lookup"><span data-stu-id="b8c92-139">In both cases, any discounts that were on the quotation line before simulation will be deleted.</span></span>  
17. <span data-ttu-id="b8c92-140">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b8c92-140">Close the page.</span></span>
18. <span data-ttu-id="b8c92-141">No Painel de Ação, clique em Cotação.</span><span class="sxs-lookup"><span data-stu-id="b8c92-141">On the Action Pane, click Quotation.</span></span>
19. <span data-ttu-id="b8c92-142">Clique em Enviar cotação.</span><span class="sxs-lookup"><span data-stu-id="b8c92-142">Click Send quotation.</span></span>
20. <span data-ttu-id="b8c92-143">Selecione Sim no campo Imprimir cotação.</span><span class="sxs-lookup"><span data-stu-id="b8c92-143">Select Yes in the Print quotation field.</span></span>
21. <span data-ttu-id="b8c92-144">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b8c92-144">Click OK.</span></span>
    * <span data-ttu-id="b8c92-145">O relatório pode levar um minuto para ser gerado.</span><span class="sxs-lookup"><span data-stu-id="b8c92-145">The report may take a minute to generate.</span></span> <span data-ttu-id="b8c92-146">Não feche a página até que isso ocorra.</span><span class="sxs-lookup"><span data-stu-id="b8c92-146">Don’t close the page until it does so.</span></span>  
22. <span data-ttu-id="b8c92-147">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b8c92-147">Close the page.</span></span>

## <a name="update-a-sales-quotation"></a><span data-ttu-id="b8c92-148">Atualizar uma cotação de venda</span><span class="sxs-lookup"><span data-stu-id="b8c92-148">Update a sales quotation</span></span>
1. <span data-ttu-id="b8c92-149">No Painel de Ação, clique em Acompanhamento.</span><span class="sxs-lookup"><span data-stu-id="b8c92-149">On the Action Pane, click Follow up.</span></span>
2. <span data-ttu-id="b8c92-150">Clique em Converter em cliente.</span><span class="sxs-lookup"><span data-stu-id="b8c92-150">Click Convert to customer.</span></span>
3. <span data-ttu-id="b8c92-151">No campo Conta de cliente, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="b8c92-151">In the Customer account field, type a value.</span></span>
4. <span data-ttu-id="b8c92-152">Clique em Verificar.</span><span class="sxs-lookup"><span data-stu-id="b8c92-152">Click Check.</span></span>
    * <span data-ttu-id="b8c92-153">Verifique se aparece uma mensagem indicando que o número de conta que você digitou está livre para uso.</span><span class="sxs-lookup"><span data-stu-id="b8c92-153">Make sure you see a message that the account number you typed in is free to use.</span></span>  
5. <span data-ttu-id="b8c92-154">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b8c92-154">Click OK.</span></span>
    * <span data-ttu-id="b8c92-155">O sistema agora criou uma nova conta de cliente para o cliente potencial da cotação.</span><span class="sxs-lookup"><span data-stu-id="b8c92-155">The system has now created a new customer account for the prospect on the quotation.</span></span>  
6. <span data-ttu-id="b8c92-156">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b8c92-156">Close the page.</span></span>
7. <span data-ttu-id="b8c92-157">No Painel de Ação, clique em Acompanhamento.</span><span class="sxs-lookup"><span data-stu-id="b8c92-157">On the Action Pane, click Follow up.</span></span>
8. <span data-ttu-id="b8c92-158">Clique em Confirmar.</span><span class="sxs-lookup"><span data-stu-id="b8c92-158">Click Confirm.</span></span>
9. <span data-ttu-id="b8c92-159">No campo Motivo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b8c92-159">In the Reason field, enter or select a value.</span></span>
10. <span data-ttu-id="b8c92-160">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b8c92-160">Click OK.</span></span>
11. <span data-ttu-id="b8c92-161">No Painel de Ação, clique em Geral.</span><span class="sxs-lookup"><span data-stu-id="b8c92-161">On the Action Pane, click General.</span></span>
12. <span data-ttu-id="b8c92-162">Clique em Ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="b8c92-162">Click Sales orders.</span></span>
13. <span data-ttu-id="b8c92-163">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b8c92-163">Close the page.</span></span>


