--- 
title: Dados-chave de fatura em contas a pagar usando uma fatura de fornecedor
description: "Este guia de tarefas ajudará você a criar uma fatura de fornecedor a partir de uma ordem de compra e exibir os resultados da conciliação da ordem de compra, do recebimento e da fatura (conciliação tripla)."
author: abruer
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: fcec579b295852a46723fb115a3a7bc356e5b80a
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---
# <a name="key-invoice-data-into-accounts-payable-using-a-vendor-invoice"></a><span data-ttu-id="f96cd-103">Dados-chave de fatura em contas a pagar usando uma fatura de fornecedor</span><span class="sxs-lookup"><span data-stu-id="f96cd-103">Key invoice data into accounts payable using a vendor invoice</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f96cd-104">Este guia de tarefas ajudará você a criar uma fatura de fornecedor a partir de uma ordem de compra e exibir os resultados da conciliação da ordem de compra, do recebimento e da fatura (conciliação tripla).</span><span class="sxs-lookup"><span data-stu-id="f96cd-104">This task guide will help you create a vendor invoice from a purchase order and view the results of matching the purchase order, receipt, and invoice (3 way matching).</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="f96cd-105">Crie uma ordem de compra</span><span class="sxs-lookup"><span data-stu-id="f96cd-105">Create a purchase order</span></span>
1. <span data-ttu-id="f96cd-106">Vá para Contas a pagar > Ordens de compra > Todas as ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="f96cd-106">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="f96cd-107">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="f96cd-107">Click New.</span></span>
3. <span data-ttu-id="f96cd-108">No campo Conta de fornecedor, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f96cd-108">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="f96cd-109">Localize um fornecedor para selecionar.</span><span class="sxs-lookup"><span data-stu-id="f96cd-109">Find a vendor to select.</span></span> <span data-ttu-id="f96cd-110">Por exemplo, role para baixo ao US-104.</span><span class="sxs-lookup"><span data-stu-id="f96cd-110">For example, scroll down to US-104.</span></span>
5. <span data-ttu-id="f96cd-111">Selecionar fornecedor US-104.</span><span class="sxs-lookup"><span data-stu-id="f96cd-111">Select vendor US-104.</span></span>
6. <span data-ttu-id="f96cd-112">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f96cd-112">Click OK.</span></span>
7. <span data-ttu-id="f96cd-113">No campo Número de item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f96cd-113">In the Item number field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="f96cd-114">Selecionar um item de estoque.</span><span class="sxs-lookup"><span data-stu-id="f96cd-114">Select an inventory item.</span></span> <span data-ttu-id="f96cd-115">Por exemplo, selecione número de item 1000.</span><span class="sxs-lookup"><span data-stu-id="f96cd-115">For example, select item number 1000.</span></span>
9. <span data-ttu-id="f96cd-116">Expandir ou recolher a seção Detalhes de linha.</span><span class="sxs-lookup"><span data-stu-id="f96cd-116">Expand or collapse the Line details section.</span></span>
10. <span data-ttu-id="f96cd-117">Clique na guia Configuração.</span><span class="sxs-lookup"><span data-stu-id="f96cd-117">Click the Setup tab.</span></span>
    * <span data-ttu-id="f96cd-118">Você pode substituir a política de conciliação para usar nenhuma conciliação, conciliação dupla ou conciliação tripla.</span><span class="sxs-lookup"><span data-stu-id="f96cd-118">You can override the matching policy to use no matching, 2-way matching, or 3-way matching.</span></span>  
11. <span data-ttu-id="f96cd-119">Expandir ou recolher a seção Detalhes de linha.</span><span class="sxs-lookup"><span data-stu-id="f96cd-119">Expand or collapse the Line details section.</span></span>
12. <span data-ttu-id="f96cd-120">No Painel de Ação, clique em Compra.</span><span class="sxs-lookup"><span data-stu-id="f96cd-120">On the Action Pane, click Purchase.</span></span>
13. <span data-ttu-id="f96cd-121">Clique em Confirmar.</span><span class="sxs-lookup"><span data-stu-id="f96cd-121">Click Confirm.</span></span>

## <a name="receive-the-products"></a><span data-ttu-id="f96cd-122">Receba os produtos</span><span class="sxs-lookup"><span data-stu-id="f96cd-122">Receive the products</span></span>
1. <span data-ttu-id="f96cd-123">No Painel de Ação, clique em Receber.</span><span class="sxs-lookup"><span data-stu-id="f96cd-123">On the Action Pane, click Receive.</span></span>
2. <span data-ttu-id="f96cd-124">Clique em Recebimento de produtos.</span><span class="sxs-lookup"><span data-stu-id="f96cd-124">Click Product receipt.</span></span>
3. <span data-ttu-id="f96cd-125">No campo Recebimento de produtos, insira o número de recebimento do produto.</span><span class="sxs-lookup"><span data-stu-id="f96cd-125">In the Product receipt field, enter the product receipt number.</span></span> <span data-ttu-id="f96cd-126">Por exemplo, insira PR123.</span><span class="sxs-lookup"><span data-stu-id="f96cd-126">For example, enter PR123.</span></span>
4. <span data-ttu-id="f96cd-127">Clique em OK para lançar o recebimento do produto.</span><span class="sxs-lookup"><span data-stu-id="f96cd-127">Click OK to post the product receipt.</span></span>
5. <span data-ttu-id="f96cd-128">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f96cd-128">Close the page.</span></span>

## <a name="create-a-vendor-invoice"></a><span data-ttu-id="f96cd-129">Crie uma fatura de fornecedor</span><span class="sxs-lookup"><span data-stu-id="f96cd-129">Create a vendor invoice</span></span>
1. <span data-ttu-id="f96cd-130">Ir para Contas a pagar > Ordens de compra > Ordens de compra recebidas, mas não faturadas.</span><span class="sxs-lookup"><span data-stu-id="f96cd-130">Go to Accounts payable > Purchase orders > Purchase orders received but not invoiced.</span></span>
2. <span data-ttu-id="f96cd-131">Selecione a ordem de compra que você criou.</span><span class="sxs-lookup"><span data-stu-id="f96cd-131">Select the purchase order that you created.</span></span>
3. <span data-ttu-id="f96cd-132">No Painel de Ação, clique em Fatura.</span><span class="sxs-lookup"><span data-stu-id="f96cd-132">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="f96cd-133">Clique em Fatura.</span><span class="sxs-lookup"><span data-stu-id="f96cd-133">Click Invoice.</span></span>
5. <span data-ttu-id="f96cd-134">No campo Número, insira o número da fatura.</span><span class="sxs-lookup"><span data-stu-id="f96cd-134">In the Number field, enter the invoice number.</span></span>
6. <span data-ttu-id="f96cd-135">No campo Descrição da fatura, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f96cd-135">In the Invoice description field, type a value.</span></span>
7. <span data-ttu-id="f96cd-136">No campo Data da fatura, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="f96cd-136">In the Invoice date field, enter a date.</span></span>
8. <span data-ttu-id="f96cd-137">No campo Preço unitários, insira 1200.</span><span class="sxs-lookup"><span data-stu-id="f96cd-137">In the Unit price field, enter 1200.</span></span>
9. <span data-ttu-id="f96cd-138">Clique em Adicionar nova linha.</span><span class="sxs-lookup"><span data-stu-id="f96cd-138">Click Add line.</span></span>
10. <span data-ttu-id="f96cd-139">No campo Número de item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f96cd-139">In the Item number field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="f96cd-140">Na lista, localize o número do item de encargos de instalação.</span><span class="sxs-lookup"><span data-stu-id="f96cd-140">In the list, find the installation charge item number.</span></span> <span data-ttu-id="f96cd-141">Por exemplo, S0001</span><span class="sxs-lookup"><span data-stu-id="f96cd-141">For example, S0001</span></span>
12. <span data-ttu-id="f96cd-142">Selecione o número de item de encargo de instalação.</span><span class="sxs-lookup"><span data-stu-id="f96cd-142">Select the installation charge item number.</span></span>
    * <span data-ttu-id="f96cd-143">Observe que a conciliação não foi executada desde que você fez as alterações.</span><span class="sxs-lookup"><span data-stu-id="f96cd-143">Note that matching has not been performed since you made the changes.</span></span>  
13. <span data-ttu-id="f96cd-144">Clique em Atualizar status de conciliação.</span><span class="sxs-lookup"><span data-stu-id="f96cd-144">Click Update match status.</span></span>
14. <span data-ttu-id="f96cd-145">No Painel de Ação, clique em Revisar.</span><span class="sxs-lookup"><span data-stu-id="f96cd-145">On the Action Pane, click Review.</span></span>
15. <span data-ttu-id="f96cd-146">Clique em Detalhes da conciliação.</span><span class="sxs-lookup"><span data-stu-id="f96cd-146">Click Matching details.</span></span>
    * <span data-ttu-id="f96cd-147">A nova linha com os serviços não precisa ser feita para que o status permaneça "Não realizado".</span><span class="sxs-lookup"><span data-stu-id="f96cd-147">The new line with services does not need to be matched so the status stays "Not performed".</span></span>  
16. <span data-ttu-id="f96cd-148">Selecione o recebimento de produto para o item de estoque que você recebeu.</span><span class="sxs-lookup"><span data-stu-id="f96cd-148">Select the product receipt for the inventory item that you received.</span></span>
    * <span data-ttu-id="f96cd-149">A linha com o recebimento do produto foi conciliada, mas, como há uma diferença de quantidade ou de preço, ela falha.</span><span class="sxs-lookup"><span data-stu-id="f96cd-149">The line with the product receipt was matched but there is a mismatch of quantity or price so it fails.</span></span>  
17. <span data-ttu-id="f96cd-150">No campo Preço unitário, insira um número.</span><span class="sxs-lookup"><span data-stu-id="f96cd-150">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="f96cd-151">Agora que o preço unitário foi conciliado, o status é atualizado para Aprovado.</span><span class="sxs-lookup"><span data-stu-id="f96cd-151">Now that the unit price matches, the status is updated to Passed.</span></span> <span data-ttu-id="f96cd-152">Se sua política permitir discrepâncias ou se a conciliação for apenas um aviso, você ainda poderá lançar a fatura.</span><span class="sxs-lookup"><span data-stu-id="f96cd-152">If your policy allows discrepancies or if matching is only a warning, you can still post the invoice.</span></span>  
18. <span data-ttu-id="f96cd-153">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f96cd-153">Close the page.</span></span>
19. <span data-ttu-id="f96cd-154">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="f96cd-154">Click Post.</span></span>
20. <span data-ttu-id="f96cd-155">Feche o formulário.</span><span class="sxs-lookup"><span data-stu-id="f96cd-155">Close the form.</span></span>
    * <span data-ttu-id="f96cd-156">Observe que a ordem de compra não está mais listada como recebida, mas como não faturada.</span><span class="sxs-lookup"><span data-stu-id="f96cd-156">Note that the purchase order is no longer listed as received but not invoiced.</span></span>  


