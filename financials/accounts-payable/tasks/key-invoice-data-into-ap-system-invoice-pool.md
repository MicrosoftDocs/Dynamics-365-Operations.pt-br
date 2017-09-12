--- 
title: Dados-chave de fatura no sistema de AP usando grupo de faturas
description: "Esta guia da tarefa mostrará como usar o registro de nota fiscal para criar notas fiscais."
author: abruer
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 96040b1c1ba130f773ba0defbf7bf1dcebedfc13
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="key-invoice-data-into-the-ap-system-using-invoice-pool"></a><span data-ttu-id="46aac-103">Dados-chave de fatura no sistema de AP usando grupo de faturas</span><span class="sxs-lookup"><span data-stu-id="46aac-103">Key invoice data into the AP system using invoice pool</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="46aac-104">Esta guia da tarefa mostrará como usar o registro de nota fiscal para criar notas fiscais.</span><span class="sxs-lookup"><span data-stu-id="46aac-104">This task guide will show you how to use the invoice register to create invoices.</span></span>  <span data-ttu-id="46aac-105">Use o grupo de notas fiscais para fazer a correspondência da nota fiscal para uma ordem de compra e finalizar as despesas na página da nota fiscal do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="46aac-105">Then use the invoice pool to match the invoice to a purchase order and finalize the expense in the vendor invoice page.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="46aac-106">Crie uma ordem de compra</span><span class="sxs-lookup"><span data-stu-id="46aac-106">Create a purchase order</span></span>
1. <span data-ttu-id="46aac-107">Vá para Contas a pagar > Ordens de compra > Ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="46aac-107">Go to Accounts payable > Purchase orders > Purchase orders.</span></span>
2. <span data-ttu-id="46aac-108">Clique em Novo para criar uma ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="46aac-108">Click New to create a purchase order.</span></span>
3. <span data-ttu-id="46aac-109">No campo Conta de fornecedor, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="46aac-109">In the Vendor account field, click the drop down button to open the lookup.</span></span>
4. <span data-ttu-id="46aac-110">Selecione o fornecedor na lista.</span><span class="sxs-lookup"><span data-stu-id="46aac-110">Select the vendor from the list.</span></span> <span data-ttu-id="46aac-111">Por exemplo, fornecedor 1001.</span><span class="sxs-lookup"><span data-stu-id="46aac-111">For example, vendor 1001.</span></span>
5. <span data-ttu-id="46aac-112">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="46aac-112">Click OK.</span></span>
6. <span data-ttu-id="46aac-113">No campo Número do item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="46aac-113">In the Item number field, click the drop down button to open the lookup.</span></span>
7. <span data-ttu-id="46aac-114">Localizar o número de item de serviço na lista.</span><span class="sxs-lookup"><span data-stu-id="46aac-114">Find the services item number in the list.</span></span> <span data-ttu-id="46aac-115">Por exemplo, selecione S0001.</span><span class="sxs-lookup"><span data-stu-id="46aac-115">For example, select S0001.</span></span>
8. <span data-ttu-id="46aac-116">Clique no número de item e o selecione.</span><span class="sxs-lookup"><span data-stu-id="46aac-116">Click on the item number and select it.</span></span>
    * <span data-ttu-id="46aac-117">O total líquido é 75,00.</span><span class="sxs-lookup"><span data-stu-id="46aac-117">The net amount is 75.00.</span></span>  <span data-ttu-id="46aac-118">Esse é o valor que esperaremos na nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="46aac-118">That is the amount that we will expect on the invoice.</span></span>  
9. <span data-ttu-id="46aac-119">No painel de ação, clique em Compra.</span><span class="sxs-lookup"><span data-stu-id="46aac-119">On the action pane, click Purchase.</span></span>
10. <span data-ttu-id="46aac-120">Clique em Confirmar.</span><span class="sxs-lookup"><span data-stu-id="46aac-120">Click Confirm.</span></span>

## <a name="create-and-post-and-invoice"></a><span data-ttu-id="46aac-121">Criar e lançar e faturar</span><span class="sxs-lookup"><span data-stu-id="46aac-121">Create and post and invoice</span></span>
1. <span data-ttu-id="46aac-122">Vá para Contas a pagar > Faturas > Registro de fatura.</span><span class="sxs-lookup"><span data-stu-id="46aac-122">Go to Accounts payable > Invoices > Invoice register.</span></span>
2. <span data-ttu-id="46aac-123">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="46aac-123">Click New.</span></span>
3. <span data-ttu-id="46aac-124">Abra a busca para selecionar o nome do registro de fatura que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="46aac-124">Open the lookup to select the name of the invoice register that you want to use.</span></span>
4. <span data-ttu-id="46aac-125">Selecione o nome do registro de fatura que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="46aac-125">Select the name of the invoice register that you want to use.</span></span>
5. <span data-ttu-id="46aac-126">Clique em em Linhas para abrir o registro e para inserir linhas de despesa.</span><span class="sxs-lookup"><span data-stu-id="46aac-126">Click on Lines to open the register and enter expense lines.</span></span>
6. <span data-ttu-id="46aac-127">Na busca, selecione um fornecedor.</span><span class="sxs-lookup"><span data-stu-id="46aac-127">In the lookup, select a vendor.</span></span> <span data-ttu-id="46aac-128">Por exemplo, clique em vendor 1001.</span><span class="sxs-lookup"><span data-stu-id="46aac-128">For example, click on vendor 1001.</span></span>
7. <span data-ttu-id="46aac-129">No campo Fatura, insira o número da fatura.</span><span class="sxs-lookup"><span data-stu-id="46aac-129">In the Invoice field, enter the invoice number.</span></span>
8. <span data-ttu-id="46aac-130">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="46aac-130">In the Description field, type a value.</span></span>
9. <span data-ttu-id="46aac-131">No campo Crédito, insira um número.</span><span class="sxs-lookup"><span data-stu-id="46aac-131">In the Credit field, enter a number.</span></span>
10. <span data-ttu-id="46aac-132">No campo Ordem de compra, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="46aac-132">In the Purchase order field, click the drop down button to open the lookup.</span></span>
11. <span data-ttu-id="46aac-133">Selecione a ordem de compra que você criou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="46aac-133">Select the purchase order that you created earlier.</span></span>
12. <span data-ttu-id="46aac-134">No campo Aprovado por, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="46aac-134">In the Approved by field, click the drop down button to open the lookup.</span></span>
13. <span data-ttu-id="46aac-135">Realce um aprovador e clique em selecionar para selecionar o aprovador.</span><span class="sxs-lookup"><span data-stu-id="46aac-135">Highlight an approver and click Select to select that approver.</span></span>
14. <span data-ttu-id="46aac-136">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="46aac-136">Click Post.</span></span>
15. <span data-ttu-id="46aac-137">Feche o formulário.</span><span class="sxs-lookup"><span data-stu-id="46aac-137">Close the form.</span></span>
16. <span data-ttu-id="46aac-138">Feche o formulário.</span><span class="sxs-lookup"><span data-stu-id="46aac-138">Close the form.</span></span>

## <a name="open-an-invoice-from-the-pool-and-match-it-to-a-purchase-order-to-complete-the-invoice-process"></a><span data-ttu-id="46aac-139">Abra uma fatura do grupo e corresponda-a a ordem de compra para concluir o processo de fatura</span><span class="sxs-lookup"><span data-stu-id="46aac-139">Open an invoice from the pool and match it to a purchase order to complete the invoice process</span></span>
1. <span data-ttu-id="46aac-140">Vá para Contas a pagar > Faturas > Grupo de fatura.</span><span class="sxs-lookup"><span data-stu-id="46aac-140">Go to Accounts payable > Invoices > Invoice pool.</span></span>
2. <span data-ttu-id="46aac-141">Clique em Ordem de compra para criar uma fatura de fornecedor da fatura no grupo.</span><span class="sxs-lookup"><span data-stu-id="46aac-141">Click Purchase order to create a vendor invoice from the invoice in the pool.</span></span>
3. <span data-ttu-id="46aac-142">Selecione a fatura que você deseja revisar.</span><span class="sxs-lookup"><span data-stu-id="46aac-142">Select the invoice that you want to review.</span></span>
4. <span data-ttu-id="46aac-143">Clique no status de correspondência de atualização para concluir a correspondência.</span><span class="sxs-lookup"><span data-stu-id="46aac-143">Click Update match status to complete the matching.</span></span>
5. <span data-ttu-id="46aac-144">No painel de ação, clique em Opções.</span><span class="sxs-lookup"><span data-stu-id="46aac-144">On the action pane, click Options.</span></span>
6. <span data-ttu-id="46aac-145">Clique em Alterar exibição.</span><span class="sxs-lookup"><span data-stu-id="46aac-145">Click Change view.</span></span>
7. <span data-ttu-id="46aac-146">Clique em Exibição de grade.</span><span class="sxs-lookup"><span data-stu-id="46aac-146">Click Grid view.</span></span>
8. <span data-ttu-id="46aac-147">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="46aac-147">Click Post.</span></span>
9. <span data-ttu-id="46aac-148">Feche o formulário.</span><span class="sxs-lookup"><span data-stu-id="46aac-148">Close the form.</span></span>
10. <span data-ttu-id="46aac-149">Vá para Contas a pagar > Fornecedores > Fornecedores.</span><span class="sxs-lookup"><span data-stu-id="46aac-149">Go to Accounts payable > Vendors > Vendors.</span></span>
11. <span data-ttu-id="46aac-150">Selecione o fornecedor que estava na ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="46aac-150">Select the vendor that was on the purchase order.</span></span> <span data-ttu-id="46aac-151">Por exemplo, selecione fornecedor 1001.</span><span class="sxs-lookup"><span data-stu-id="46aac-151">For example, select vendor 1001.</span></span>
12. <span data-ttu-id="46aac-152">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="46aac-152">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="46aac-153">No painel de ação, clique em Fornecedor.</span><span class="sxs-lookup"><span data-stu-id="46aac-153">On the action pane, click Vendor.</span></span>
14. <span data-ttu-id="46aac-154">Clique em Transações.</span><span class="sxs-lookup"><span data-stu-id="46aac-154">Click Transactions.</span></span>
15. <span data-ttu-id="46aac-155">Selecione a nota fiscal que você criou.</span><span class="sxs-lookup"><span data-stu-id="46aac-155">Select the invoice that you created.</span></span>
    * <span data-ttu-id="46aac-156">O acúmulo de registro de nota fiscal foi estornada e lançada na conta de despesas apropriada.</span><span class="sxs-lookup"><span data-stu-id="46aac-156">The invoice register accrual was reversed and posted to the appropriate expense account.</span></span>  


