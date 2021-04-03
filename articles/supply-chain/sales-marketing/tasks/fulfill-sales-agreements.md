---
title: Cumprir contratos de venda
description: Este procedimento mostra como atender a um contrato de venda associando ordens de venda a ele.
author: omulvad
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesAgreementListPage, SalesAgreement, SalesAgreementGenerateReleaseOrder, SalesTableListPage, SalesTable, AgreementLine, SalesCreateOrder,  SalesEditLines, SalesAgreementHistory
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 31c86ae556789ecf04dc303ddd9510458c1f6d01
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5260374"
---
# <a name="fulfill-sales-agreements"></a><span data-ttu-id="e503f-103">Cumprir contratos de venda</span><span class="sxs-lookup"><span data-stu-id="e503f-103">Fulfill sales agreements</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e503f-104">Este procedimento mostra como atender a um contrato de venda associando ordens de venda a ele.</span><span class="sxs-lookup"><span data-stu-id="e503f-104">This procedure shows you how to fulfill a sales agreement by associating sales orders with it.</span></span> <span data-ttu-id="e503f-105">Você pode executar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="e503f-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="e503f-106">Antes de iniciar esta guia, certifique-se de que tem um contrato de venda efetivo do tipo "Compromisso de valor do produto".</span><span class="sxs-lookup"><span data-stu-id="e503f-106">Before starting this guide, make sure you have an effective sales agreement of type "Product value commitment".</span></span> <span data-ttu-id="e503f-107">Como alternativa, você pode executar a guia de tarefas chamada "Criar contratos de venda".</span><span class="sxs-lookup"><span data-stu-id="e503f-107">Alternatively, you can run the task guide called "Create sales agreements".</span></span>  




## <a name="release-a-sales-order-from-the-agreement"></a><span data-ttu-id="e503f-108">Liberar uma ordem de venda do contrato</span><span class="sxs-lookup"><span data-stu-id="e503f-108">Release a sales order from the agreement</span></span>
1. <span data-ttu-id="e503f-109">Vá para Vendas e marketing > Contratos de venda > Contratos de venda.</span><span class="sxs-lookup"><span data-stu-id="e503f-109">Go to Sales and marketing > Sales agreements > Sales agreements.</span></span>
2. <span data-ttu-id="e503f-110">Na lista, abra o contrato com o qual você deseja liberar a ordem.</span><span class="sxs-lookup"><span data-stu-id="e503f-110">In the list, open the agreement against which you want to release the order.</span></span>
3. <span data-ttu-id="e503f-111">No Painel de Ação, clique em Contrato de venda.</span><span class="sxs-lookup"><span data-stu-id="e503f-111">On the Action Pane, click Sales agreement.</span></span>
4. <span data-ttu-id="e503f-112">Clique em Liberar ordem.</span><span class="sxs-lookup"><span data-stu-id="e503f-112">Click Release order.</span></span>
    * <span data-ttu-id="e503f-113">Como indica o texto na parte superior da pagina Criar ordem de liberação, os detalhes necessários para as linhas da ordem de venda serão diferentes, dependendo se o contrato é baseado em quantidade ou em valor.</span><span class="sxs-lookup"><span data-stu-id="e503f-113">As the text on top of the  Create release order page points out, the details required for the sales order lines will differ depending on whether the agreement is quantity- or value-based.</span></span>  
    * <span data-ttu-id="e503f-114">O contrato nessa guia é do tipo "Compromisso de valor do produto".</span><span class="sxs-lookup"><span data-stu-id="e503f-114">The agreement in this guide is of type "Product value commitment".</span></span> <span data-ttu-id="e503f-115">Este é o motivo pelo qual a seção Linhas desta página está em branco.</span><span class="sxs-lookup"><span data-stu-id="e503f-115">This is why the Lines section of this page is blank.</span></span> <span data-ttu-id="e503f-116">Se o compromisso fosse baseado na quantidade, as informações da linha seriam copiadas do contrato.</span><span class="sxs-lookup"><span data-stu-id="e503f-116">If the commitment was based on quantity, the line information would be copied from the agreement.</span></span>  
5. <span data-ttu-id="e503f-117">Clique em Criar.</span><span class="sxs-lookup"><span data-stu-id="e503f-117">Click Create.</span></span>
    * <span data-ttu-id="e503f-118">A mensagem informa que a ordem de vendas foi criada.</span><span class="sxs-lookup"><span data-stu-id="e503f-118">The message informs you that a sales order has been created.</span></span> <span data-ttu-id="e503f-119">Como a ordem não contém nenhuma linha, você deve adicionar os detalhes da linha da ordem para concluir o processo de liberação.</span><span class="sxs-lookup"><span data-stu-id="e503f-119">Since the order does not contain any lines, you must add order line details to complete the release process.</span></span>   
6. <span data-ttu-id="e503f-120">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="e503f-120">Close the page.</span></span>
7. <span data-ttu-id="e503f-121">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="e503f-121">Close the page.</span></span>
8. <span data-ttu-id="e503f-122">Vá para Vendas e marketing > Ordens de venda > Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="e503f-122">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
9. <span data-ttu-id="e503f-123">Na lista, localize e abra a ordem que foi criada como resultado da versão da ordem na tarefa anterior.</span><span class="sxs-lookup"><span data-stu-id="e503f-123">In the list, find and open the order that was created as the result of the order release in the previous task.</span></span>
10. <span data-ttu-id="e503f-124">Clique em Adicionar nova linha.</span><span class="sxs-lookup"><span data-stu-id="e503f-124">Click Add line.</span></span>
11. <span data-ttu-id="e503f-125">No campo Número de item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e503f-125">In the Item number field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="e503f-126">No campo Número do item, digite ou selecione o item que é especificado no contrato de venda associado.</span><span class="sxs-lookup"><span data-stu-id="e503f-126">In the Item number field, type or select the item that is specified on the associated sales agreement.</span></span>
13. <span data-ttu-id="e503f-127">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="e503f-127">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="e503f-128">Certifique-se de inserir uma quantidade que coloque o Valor líquido abaixo do valor do contrato de venda associado.</span><span class="sxs-lookup"><span data-stu-id="e503f-128">Make sure that you enter a quantity that brings the Net amount under the value of the associated sales agreement.</span></span>  
    * <span data-ttu-id="e503f-129">Observe que como a ordem de venda está vinculada ao contrato, a porcentagem de desconto negociada será aplicada à linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="e503f-129">Notice that because the sales order is linked to the agreement, the negotiated discount percent is applied to the order line.</span></span>  
14. <span data-ttu-id="e503f-130">Clique em Atualizar linha.</span><span class="sxs-lookup"><span data-stu-id="e503f-130">Click Update line.</span></span>
15. <span data-ttu-id="e503f-131">Clique em Anexado.</span><span class="sxs-lookup"><span data-stu-id="e503f-131">Click Attached.</span></span>
    * <span data-ttu-id="e503f-132">A página Contrato anexado mostra o ID e as condições do contrato dos quais a linha é liberada.</span><span class="sxs-lookup"><span data-stu-id="e503f-132">The Attached agreement page shows the ID and terms of the agreement from which the line is released.</span></span>  
16. <span data-ttu-id="e503f-133">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="e503f-133">Close the page.</span></span>
17. <span data-ttu-id="e503f-134">No Painel de Ação, clique em Geral.</span><span class="sxs-lookup"><span data-stu-id="e503f-134">On the Action Pane, click General.</span></span>
18. <span data-ttu-id="e503f-135">Clique em Contrato de venda anexado.</span><span class="sxs-lookup"><span data-stu-id="e503f-135">Click Attached sales agreement.</span></span>
19. <span data-ttu-id="e503f-136">Expanda a seção Detalhes da linha.</span><span class="sxs-lookup"><span data-stu-id="e503f-136">Expand the Line details section.</span></span>
20. <span data-ttu-id="e503f-137">Clique na guia Atendimento.</span><span class="sxs-lookup"><span data-stu-id="e503f-137">Click the Fulfillment tab.</span></span>
    * <span data-ttu-id="e503f-138">A guia Atendimento mostra um resumo de todas as linhas da ordem de venda associadas a esse compromisso, e o estado de atendimento, bem como o valor ou a quantidade que ainda não foram liberados.</span><span class="sxs-lookup"><span data-stu-id="e503f-138">The Fulfillment tab shows a summary of all the sales order lines that are associated with this commitment, and their fulfillment state, as well as the amount or quantity that has not yet been released.</span></span>   
21. <span data-ttu-id="e503f-139">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="e503f-139">Close the page.</span></span>
22. <span data-ttu-id="e503f-140">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="e503f-140">Close the page.</span></span>
23. <span data-ttu-id="e503f-141">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="e503f-141">Close the page.</span></span>

## <a name="apply-sales-agreement-in-the-order-process"></a><span data-ttu-id="e503f-142">Aplicar contrato de venda no processo de ordem</span><span class="sxs-lookup"><span data-stu-id="e503f-142">Apply sales agreement in the order process</span></span>
1. <span data-ttu-id="e503f-143">Vá para Vendas e marketing > Ordens de venda > Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="e503f-143">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="e503f-144">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="e503f-144">Click New.</span></span>
3. <span data-ttu-id="e503f-145">No campo Conta do cliente, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e503f-145">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="e503f-146">Na lista, localize e selecione o cliente especificado no contrato de venda.</span><span class="sxs-lookup"><span data-stu-id="e503f-146">In the list, find and select the customer specified on the sales agreement.</span></span>
5. <span data-ttu-id="e503f-147">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="e503f-147">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="e503f-148">Expanda a seção Geral.</span><span class="sxs-lookup"><span data-stu-id="e503f-148">Expand the General section.</span></span>
7. <span data-ttu-id="e503f-149">No campo ID do contrato de venda, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e503f-149">In the Sales agreement ID field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="e503f-150">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="e503f-150">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="e503f-151">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="e503f-151">Click Yes.</span></span>
10. <span data-ttu-id="e503f-152">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e503f-152">Click OK.</span></span>
11. <span data-ttu-id="e503f-153">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="e503f-153">In the list, mark the selected row.</span></span>
12. <span data-ttu-id="e503f-154">No campo Número de item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e503f-154">In the Item number field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="e503f-155">No campo Número do item, digite ou selecione o item que é especificado no contrato de venda associado.</span><span class="sxs-lookup"><span data-stu-id="e503f-155">In the Item number field, type or select the item that is specified on the associated sales agreement.</span></span>
14. <span data-ttu-id="e503f-156">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="e503f-156">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="e503f-157">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="e503f-157">Click Save.</span></span>
16. <span data-ttu-id="e503f-158">No Painel de Ação, clique em Separar e empacotar.</span><span class="sxs-lookup"><span data-stu-id="e503f-158">On the Action Pane, click Pick and pack.</span></span>
17. <span data-ttu-id="e503f-159">Clique em Lançar guia de remessa.</span><span class="sxs-lookup"><span data-stu-id="e503f-159">Click Post packing slip.</span></span>
18. <span data-ttu-id="e503f-160">Expanda a seção Parâmetros.</span><span class="sxs-lookup"><span data-stu-id="e503f-160">Expand the Parameters section.</span></span>
19. <span data-ttu-id="e503f-161">Selecione Sim no campo Lançamento.</span><span class="sxs-lookup"><span data-stu-id="e503f-161">Select Yes in the Posting field.</span></span>
20. <span data-ttu-id="e503f-162">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e503f-162">Click OK.</span></span>
21. <span data-ttu-id="e503f-163">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e503f-163">Click OK.</span></span>
22. <span data-ttu-id="e503f-164">No Painel de Ação, clique em Geral.</span><span class="sxs-lookup"><span data-stu-id="e503f-164">On the Action Pane, click General.</span></span>
23. <span data-ttu-id="e503f-165">Clique em Contrato de venda anexado.</span><span class="sxs-lookup"><span data-stu-id="e503f-165">Click Attached sales agreement.</span></span>
24. <span data-ttu-id="e503f-166">Clique na guia Atendimento.</span><span class="sxs-lookup"><span data-stu-id="e503f-166">Click the Fulfillment tab.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]