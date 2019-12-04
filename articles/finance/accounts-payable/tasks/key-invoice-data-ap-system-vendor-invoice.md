---
title: Dados principais de nota fiscal no sistema AP usando a nota fiscal de fornecedor
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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7abae6d680d899a0294ad3c298a4b0264ba01d0b
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189421"
---
# <a name="key-invoice-data-in-ap-system-using-vendor-invoice"></a><span data-ttu-id="48e40-103">Dados principais de nota fiscal no sistema AP usando a nota fiscal de fornecedor</span><span class="sxs-lookup"><span data-stu-id="48e40-103">Key invoice data in AP system using vendor invoice</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="48e40-104">Este guia de tarefas ajudará você a criar uma fatura de fornecedor a partir de uma ordem de compra e exibir os resultados da conciliação da ordem de compra, do recebimento e da fatura (conciliação tripla).</span><span class="sxs-lookup"><span data-stu-id="48e40-104">This task guide will help you create a vendor invoice from a purchase order and view the results of matching the purchase order, receipt, and invoice (3 way matching).</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="48e40-105">Criar uma ordem de compra</span><span class="sxs-lookup"><span data-stu-id="48e40-105">Create a purchase order</span></span>
1. <span data-ttu-id="48e40-106">No Painel de navegação, vá para **Módulos > Contas a pagar > Ordens de compra > Todas as ordens de compra**.</span><span class="sxs-lookup"><span data-stu-id="48e40-106">In the Navigation pane, go to **Modules > Accounts payable > Purchase orders > All purchase orders**.</span></span>
2. <span data-ttu-id="48e40-107">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="48e40-107">Click **New**.</span></span>
3. <span data-ttu-id="48e40-108">No campo **Conta de fornecedor**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="48e40-108">In the **Vendor account** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="48e40-109">Localize um fornecedor para selecionar.</span><span class="sxs-lookup"><span data-stu-id="48e40-109">Find a vendor to select.</span></span> <span data-ttu-id="48e40-110">Por exemplo, role para baixo ao US-104.</span><span class="sxs-lookup"><span data-stu-id="48e40-110">For example, scroll down to US-104.</span></span>
5. <span data-ttu-id="48e40-111">Selecionar fornecedor US-104.</span><span class="sxs-lookup"><span data-stu-id="48e40-111">Select vendor US-104.</span></span>
6. <span data-ttu-id="48e40-112">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="48e40-112">Click **OK**.</span></span>
7. <span data-ttu-id="48e40-113">No campo **Número do item**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="48e40-113">In the **Item number** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="48e40-114">Selecionar um item de estoque.</span><span class="sxs-lookup"><span data-stu-id="48e40-114">Select an inventory item.</span></span> <span data-ttu-id="48e40-115">Por exemplo, selecione número de item 1000.</span><span class="sxs-lookup"><span data-stu-id="48e40-115">For example, select item number 1000.</span></span>
9. <span data-ttu-id="48e40-116">Expanda a Guia Rápida **Detalhes da linha**.</span><span class="sxs-lookup"><span data-stu-id="48e40-116">Expand the **Line details** fastTab.</span></span>
10. <span data-ttu-id="48e40-117">Clique na guia **Configuração**. Você pode substituir a política de conciliação para usar nenhuma conciliação, conciliação dupla ou conciliação tripla.</span><span class="sxs-lookup"><span data-stu-id="48e40-117">Click the **Setup** tab. You can override the matching policy to use no matching, 2-way matching, or 3-way matching.</span></span>  
11. <span data-ttu-id="48e40-118">No Painel de Ação, clique em **Compra**.</span><span class="sxs-lookup"><span data-stu-id="48e40-118">On the Action Pane, click **Purchase**.</span></span>
12. <span data-ttu-id="48e40-119">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="48e40-119">Click **Confirm**.</span></span>

## <a name="receive-the-products"></a><span data-ttu-id="48e40-120">Receba os produtos</span><span class="sxs-lookup"><span data-stu-id="48e40-120">Receive the products</span></span>
1. <span data-ttu-id="48e40-121">No Painel de Ação, clique em **Receber**.</span><span class="sxs-lookup"><span data-stu-id="48e40-121">On the Action Pane, click **Receive**.</span></span>
2. <span data-ttu-id="48e40-122">Clique em **Recebimento de produtos**.</span><span class="sxs-lookup"><span data-stu-id="48e40-122">Click **Product receipt**.</span></span>
3. <span data-ttu-id="48e40-123">No campo **Recebimento de produtos**, insira o número de recebimento do produto.</span><span class="sxs-lookup"><span data-stu-id="48e40-123">In the **Product receipt** field, enter the product receipt number.</span></span> <span data-ttu-id="48e40-124">Por exemplo, insira PR123.</span><span class="sxs-lookup"><span data-stu-id="48e40-124">For example, enter PR123.</span></span>
4. <span data-ttu-id="48e40-125">Clique em **OK** para lançar o recebimento do produto.</span><span class="sxs-lookup"><span data-stu-id="48e40-125">Click **OK** to post the product receipt.</span></span>
5. <span data-ttu-id="48e40-126">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="48e40-126">Close the page.</span></span>

## <a name="create-a-vendor-invoice"></a><span data-ttu-id="48e40-127">Crie uma fatura de fornecedor</span><span class="sxs-lookup"><span data-stu-id="48e40-127">Create a vendor invoice</span></span>
1. <span data-ttu-id="48e40-128">No Painel de navegação, vá para **Módulos > Contas a pagar > Ordens de compra > Ordens de compra recebidas, mas não faturadas**.</span><span class="sxs-lookup"><span data-stu-id="48e40-128">In the Navigation pane, go to **Modules > Accounts payable > Purchase orders > Purchase orders received but not invoiced**.</span></span>
2. <span data-ttu-id="48e40-129">Selecione a ordem de compra que você criou.</span><span class="sxs-lookup"><span data-stu-id="48e40-129">Select the purchase order that you created.</span></span>
3. <span data-ttu-id="48e40-130">No Painel de Ação, clique em **Fatura**.</span><span class="sxs-lookup"><span data-stu-id="48e40-130">On the Action Pane, click **Invoice**.</span></span>
4. <span data-ttu-id="48e40-131">Clique em **Fatura**.</span><span class="sxs-lookup"><span data-stu-id="48e40-131">Click **Invoice**.</span></span>
5. <span data-ttu-id="48e40-132">No campo **Número**, insira o número da fatura.</span><span class="sxs-lookup"><span data-stu-id="48e40-132">In the **Number** field, enter the invoice number.</span></span>
6. <span data-ttu-id="48e40-133">No campo **Descrição da fatura**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="48e40-133">In the **Invoice description** field, type a value.</span></span>
7. <span data-ttu-id="48e40-134">No campo **Data da fatura**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="48e40-134">In the **Invoice date** field, enter a date.</span></span>
8. <span data-ttu-id="48e40-135">No campo **Preço unitário**, insira 1200.</span><span class="sxs-lookup"><span data-stu-id="48e40-135">In the **Unit price** field, enter 1200.</span></span>
9. <span data-ttu-id="48e40-136">Clique em **Adicionar linha**.</span><span class="sxs-lookup"><span data-stu-id="48e40-136">Click **Add line**.</span></span>
10. <span data-ttu-id="48e40-137">No campo **Número do item**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="48e40-137">In the **Item number** field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="48e40-138">Na lista, localize o número do item de encargos de instalação.</span><span class="sxs-lookup"><span data-stu-id="48e40-138">In the list, find the installation charge item number.</span></span> <span data-ttu-id="48e40-139">Por exemplo, S0001</span><span class="sxs-lookup"><span data-stu-id="48e40-139">For example, S0001</span></span>
12. <span data-ttu-id="48e40-140">Selecione o número de item de encargo de instalação.</span><span class="sxs-lookup"><span data-stu-id="48e40-140">Select the installation charge item number.</span></span> <span data-ttu-id="48e40-141">Observe que a conciliação não foi executada desde que você fez as alterações.</span><span class="sxs-lookup"><span data-stu-id="48e40-141">Note that matching has not been performed since you made the changes.</span></span>  
13. <span data-ttu-id="48e40-142">Clique em **Atualizar status de conciliação**.</span><span class="sxs-lookup"><span data-stu-id="48e40-142">Click **Update match status**.</span></span>
14. <span data-ttu-id="48e40-143">No Painel de Ação, clique em **Revisar**.</span><span class="sxs-lookup"><span data-stu-id="48e40-143">On the Action Pane, click **Review**.</span></span>
15. <span data-ttu-id="48e40-144">Clique em **Detalhes da conciliação**.</span><span class="sxs-lookup"><span data-stu-id="48e40-144">Click **Matching details**.</span></span> <span data-ttu-id="48e40-145">A nova linha com os serviços não precisa ser feita para que o status permaneça "Não realizado".</span><span class="sxs-lookup"><span data-stu-id="48e40-145">The new line with services does not need to be matched so the status stays "Not performed".</span></span>  
16. <span data-ttu-id="48e40-146">Selecione o recebimento de produto para o item de estoque que você recebeu.</span><span class="sxs-lookup"><span data-stu-id="48e40-146">Select the product receipt for the inventory item that you received.</span></span> <span data-ttu-id="48e40-147">A linha com o recebimento do produto foi conciliada, mas, como há uma diferença de quantidade ou de preço, ela falha.</span><span class="sxs-lookup"><span data-stu-id="48e40-147">The line with the product receipt was matched but there is a mismatch of quantity or price so it fails.</span></span>  
17. <span data-ttu-id="48e40-148">No campo **Preço unitário**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="48e40-148">In the **Unit price** field, enter a number.</span></span> <span data-ttu-id="48e40-149">Agora que o preço unitário foi conciliado, o status é atualizado para Aprovado.</span><span class="sxs-lookup"><span data-stu-id="48e40-149">Now that the unit price matches, the status is updated to Passed.</span></span> <span data-ttu-id="48e40-150">Se sua política permitir discrepâncias ou se a conciliação for apenas um aviso, você ainda poderá lançar a fatura.</span><span class="sxs-lookup"><span data-stu-id="48e40-150">If your policy allows discrepancies or if matching is only a warning, you can still post the invoice.</span></span>  
18. <span data-ttu-id="48e40-151">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="48e40-151">Close the page.</span></span>
19. <span data-ttu-id="48e40-152">Clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="48e40-152">Click **Post**.</span></span>
20. <span data-ttu-id="48e40-153">Feche o formulário.</span><span class="sxs-lookup"><span data-stu-id="48e40-153">Close the form.</span></span> <span data-ttu-id="48e40-154">Observe que a ordem de compra não está mais listada como recebida, mas como não faturada.</span><span class="sxs-lookup"><span data-stu-id="48e40-154">Note that the purchase order is no longer listed as received but not invoiced.</span></span>  
