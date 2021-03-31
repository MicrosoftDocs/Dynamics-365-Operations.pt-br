---
title: Dados principais de fatura no AP usando uma fatura de fornecedor
description: Este guia de tarefas ajudará você a criar uma fatura de fornecedor a partir de uma ordem de compra e exibir os resultados da conciliação da ordem de compra, do recebimento e da fatura (conciliação tripla).
author: abruer
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines, VendEditInvoice, InventItemIdLookupSimple, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 20a058eb17bcab11056c91ab3570d6cd5b84b631
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5227199"
---
# <a name="key-invoice-data-in-ap-using-a-vendor-invoice"></a><span data-ttu-id="de215-103">Dados principais de fatura no AP usando uma fatura de fornecedor</span><span class="sxs-lookup"><span data-stu-id="de215-103">Key invoice data in AP using a vendor invoice</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="de215-104">Este guia de tarefas ajudará você a criar uma fatura de fornecedor a partir de uma ordem de compra e exibir os resultados da conciliação da ordem de compra, do recebimento e da fatura (conciliação tripla).</span><span class="sxs-lookup"><span data-stu-id="de215-104">This task guide will help you create a vendor invoice from a purchase order and view the results of matching the purchase order, receipt, and invoice (3 way matching).</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="de215-105">Criar uma ordem de compra</span><span class="sxs-lookup"><span data-stu-id="de215-105">Create a purchase order</span></span>
1. <span data-ttu-id="de215-106">No Painel de navegação, vá para **Módulos > Contas a pagar > Ordens de compra > Todas as ordens de compra**.</span><span class="sxs-lookup"><span data-stu-id="de215-106">In the Navigation pane, go to **Modules > Accounts payable > Purchase orders > All purchase orders**.</span></span>
2. <span data-ttu-id="de215-107">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="de215-107">Click **New**.</span></span>
3. <span data-ttu-id="de215-108">No campo **Conta de fornecedor**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="de215-108">In the **Vendor account** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="de215-109">Localize um fornecedor para selecionar.</span><span class="sxs-lookup"><span data-stu-id="de215-109">Find a vendor to select.</span></span> <span data-ttu-id="de215-110">Por exemplo, role para baixo ao US-104.</span><span class="sxs-lookup"><span data-stu-id="de215-110">For example, scroll down to US-104.</span></span>
5. <span data-ttu-id="de215-111">Selecionar fornecedor US-104.</span><span class="sxs-lookup"><span data-stu-id="de215-111">Select vendor US-104.</span></span>
6. <span data-ttu-id="de215-112">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="de215-112">Click **OK**.</span></span>
7. <span data-ttu-id="de215-113">No campo **Número do item**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="de215-113">In the **Item number** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="de215-114">Selecionar um item de estoque.</span><span class="sxs-lookup"><span data-stu-id="de215-114">Select an inventory item.</span></span> <span data-ttu-id="de215-115">Por exemplo, selecione número de item 1000.</span><span class="sxs-lookup"><span data-stu-id="de215-115">For example, select item number 1000.</span></span>
9. <span data-ttu-id="de215-116">Expanda a Guia Rápida **Detalhes da linha**.</span><span class="sxs-lookup"><span data-stu-id="de215-116">Expand the **Line details** fastTab.</span></span>
10. <span data-ttu-id="de215-117">Clique na guia **Configuração**. Você pode substituir a política de conciliação para usar nenhuma conciliação, conciliação dupla ou conciliação tripla.</span><span class="sxs-lookup"><span data-stu-id="de215-117">Click the **Setup** tab. You can override the matching policy to use no matching, 2-way matching, or 3-way matching.</span></span>  
11. <span data-ttu-id="de215-118">No Painel de Ação, clique em **Compra**.</span><span class="sxs-lookup"><span data-stu-id="de215-118">On the Action Pane, click **Purchase**.</span></span>
12. <span data-ttu-id="de215-119">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="de215-119">Click **Confirm**.</span></span>

## <a name="receive-the-products"></a><span data-ttu-id="de215-120">Receba os produtos</span><span class="sxs-lookup"><span data-stu-id="de215-120">Receive the products</span></span>
1. <span data-ttu-id="de215-121">No Painel de Ação, clique em **Receber**.</span><span class="sxs-lookup"><span data-stu-id="de215-121">On the Action Pane, click **Receive**.</span></span>
2. <span data-ttu-id="de215-122">Clique em **Recebimento de produtos**.</span><span class="sxs-lookup"><span data-stu-id="de215-122">Click **Product receipt**.</span></span>
3. <span data-ttu-id="de215-123">No campo **Recebimento de produtos**, insira o número de recebimento do produto.</span><span class="sxs-lookup"><span data-stu-id="de215-123">In the **Product receipt** field, enter the product receipt number.</span></span> <span data-ttu-id="de215-124">Por exemplo, insira PR123.</span><span class="sxs-lookup"><span data-stu-id="de215-124">For example, enter PR123.</span></span>
4. <span data-ttu-id="de215-125">Clique em **OK** para lançar o recebimento do produto.</span><span class="sxs-lookup"><span data-stu-id="de215-125">Click **OK** to post the product receipt.</span></span>
5. <span data-ttu-id="de215-126">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="de215-126">Close the page.</span></span>

## <a name="create-a-vendor-invoice"></a><span data-ttu-id="de215-127">Crie uma fatura de fornecedor</span><span class="sxs-lookup"><span data-stu-id="de215-127">Create a vendor invoice</span></span>
1. <span data-ttu-id="de215-128">No Painel de navegação, vá para **Módulos > Contas a pagar > Ordens de compra > Ordens de compra recebidas, mas não faturadas**.</span><span class="sxs-lookup"><span data-stu-id="de215-128">In the Navigation pane, go to **Modules > Accounts payable > Purchase orders > Purchase orders received but not invoiced**.</span></span>
2. <span data-ttu-id="de215-129">Selecione a ordem de compra que você criou.</span><span class="sxs-lookup"><span data-stu-id="de215-129">Select the purchase order that you created.</span></span>
3. <span data-ttu-id="de215-130">No Painel de Ação, clique em **Fatura**.</span><span class="sxs-lookup"><span data-stu-id="de215-130">On the Action Pane, click **Invoice**.</span></span>
4. <span data-ttu-id="de215-131">Clique em **Fatura**.</span><span class="sxs-lookup"><span data-stu-id="de215-131">Click **Invoice**.</span></span>
5. <span data-ttu-id="de215-132">No campo **Número**, insira o número da fatura.</span><span class="sxs-lookup"><span data-stu-id="de215-132">In the **Number** field, enter the invoice number.</span></span>
6. <span data-ttu-id="de215-133">No campo **Descrição da fatura**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="de215-133">In the **Invoice description** field, type a value.</span></span>
7. <span data-ttu-id="de215-134">No campo **Data da fatura**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="de215-134">In the **Invoice date** field, enter a date.</span></span>
8. <span data-ttu-id="de215-135">No campo **Preço unitário**, insira 1200.</span><span class="sxs-lookup"><span data-stu-id="de215-135">In the **Unit price** field, enter 1200.</span></span>
9. <span data-ttu-id="de215-136">Clique em **Adicionar linha**.</span><span class="sxs-lookup"><span data-stu-id="de215-136">Click **Add line**.</span></span>
10. <span data-ttu-id="de215-137">No campo **Número do item**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="de215-137">In the **Item number** field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="de215-138">Na lista, localize o número do item de encargos de instalação.</span><span class="sxs-lookup"><span data-stu-id="de215-138">In the list, find the installation charge item number.</span></span> <span data-ttu-id="de215-139">Por exemplo, S0001</span><span class="sxs-lookup"><span data-stu-id="de215-139">For example, S0001</span></span>
12. <span data-ttu-id="de215-140">Selecione o número de item de encargo de instalação.</span><span class="sxs-lookup"><span data-stu-id="de215-140">Select the installation charge item number.</span></span> <span data-ttu-id="de215-141">Observe que a conciliação não foi executada desde que você fez as alterações.</span><span class="sxs-lookup"><span data-stu-id="de215-141">Note that matching has not been performed since you made the changes.</span></span>  
13. <span data-ttu-id="de215-142">Clique em **Atualizar status de conciliação**.</span><span class="sxs-lookup"><span data-stu-id="de215-142">Click **Update match status**.</span></span>
14. <span data-ttu-id="de215-143">No Painel de Ação, clique em **Revisar**.</span><span class="sxs-lookup"><span data-stu-id="de215-143">On the Action Pane, click **Review**.</span></span>
15. <span data-ttu-id="de215-144">Clique em **Detalhes da conciliação**.</span><span class="sxs-lookup"><span data-stu-id="de215-144">Click **Matching details**.</span></span> <span data-ttu-id="de215-145">A nova linha com os serviços não precisa ser feita para que o status permaneça "Não realizado".</span><span class="sxs-lookup"><span data-stu-id="de215-145">The new line with services does not need to be matched so the status stays "Not performed".</span></span>  
16. <span data-ttu-id="de215-146">Selecione o recebimento de produto para o item de estoque que você recebeu.</span><span class="sxs-lookup"><span data-stu-id="de215-146">Select the product receipt for the inventory item that you received.</span></span> <span data-ttu-id="de215-147">A linha com o recebimento do produto foi conciliada, mas, como há uma diferença de quantidade ou de preço, ela falha.</span><span class="sxs-lookup"><span data-stu-id="de215-147">The line with the product receipt was matched but there is a mismatch of quantity or price so it fails.</span></span>  
17. <span data-ttu-id="de215-148">No campo **Preço unitário**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="de215-148">In the **Unit price** field, enter a number.</span></span> <span data-ttu-id="de215-149">Agora que o preço unitário foi conciliado, o status é atualizado para Aprovado.</span><span class="sxs-lookup"><span data-stu-id="de215-149">Now that the unit price matches, the status is updated to Passed.</span></span> <span data-ttu-id="de215-150">Se sua política permitir discrepâncias ou se a conciliação for apenas um aviso, você ainda poderá lançar a fatura.</span><span class="sxs-lookup"><span data-stu-id="de215-150">If your policy allows discrepancies or if matching is only a warning, you can still post the invoice.</span></span>  
18. <span data-ttu-id="de215-151">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="de215-151">Close the page.</span></span>
19. <span data-ttu-id="de215-152">Clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="de215-152">Click **Post**.</span></span>
20. <span data-ttu-id="de215-153">Feche o formulário.</span><span class="sxs-lookup"><span data-stu-id="de215-153">Close the form.</span></span> <span data-ttu-id="de215-154">Observe que a ordem de compra não está mais listada como recebida, mas como não faturada.</span><span class="sxs-lookup"><span data-stu-id="de215-154">Note that the purchase order is no longer listed as received but not invoiced.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]