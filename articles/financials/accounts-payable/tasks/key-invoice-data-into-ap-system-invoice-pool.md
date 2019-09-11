---
title: Dados-chave de fatura no sistema de AP usando grupo de faturas
description: Este tópico descreve como usar o registro de fatura para criar faturas.
author: abruer
manager: AnnBe
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f7d72c1d98100d1313109e8b5e55df02e2163174
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867693"
---
# <a name="key-invoice-data-into-the-ap-system-using-invoice-pool"></a><span data-ttu-id="dda33-103">Dados-chave de fatura no sistema de AP usando grupo de faturas</span><span class="sxs-lookup"><span data-stu-id="dda33-103">Key invoice data into the AP system using invoice pool</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="dda33-104">Este tópico descreve como usar o registro de fatura para criar faturas.</span><span class="sxs-lookup"><span data-stu-id="dda33-104">This topic describes how to use the invoice register to create invoices.</span></span> <span data-ttu-id="dda33-105">Use o grupo de notas fiscais para fazer a correspondência da nota fiscal para uma ordem de compra e finalizar as despesas na página da nota fiscal do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="dda33-105">Then use the invoice pool to match the invoice to a purchase order and finalize the expense in the vendor invoice page.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="dda33-106">Criar uma ordem de compra</span><span class="sxs-lookup"><span data-stu-id="dda33-106">Create a purchase order</span></span>
1. <span data-ttu-id="dda33-107">No painel de navegação, vá para **Módulos > Contas a pagar > Ordens de compra > Ordens de compra**.</span><span class="sxs-lookup"><span data-stu-id="dda33-107">In the navigation pane, go to **Modules > Accounts payable > Purchase orders > Purchase orders**.</span></span>
2. <span data-ttu-id="dda33-108">Selecione **Novo** para criar uma ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="dda33-108">Select **New** to create a purchase order.</span></span>
3. <span data-ttu-id="dda33-109">No campo **Conta do fornecedor**, selecione um fornecedor da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="dda33-109">In the **Vendor account** field, select a vendor for the drop-down list.</span></span> <span data-ttu-id="dda33-110">Por exemplo, selecione o fornecedor **1001**.</span><span class="sxs-lookup"><span data-stu-id="dda33-110">For example, select vendor **1001**.</span></span>
4. <span data-ttu-id="dda33-111">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="dda33-111">Select **OK**.</span></span>
5. <span data-ttu-id="dda33-112">No campo **Número do item**, selecione o número do item de serviços na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="dda33-112">In the **Item number** field, select the services item number in the drop-down list.</span></span> <span data-ttu-id="dda33-113">Por exemplo, selecione **S0001**.</span><span class="sxs-lookup"><span data-stu-id="dda33-113">For example, select **S0001**.</span></span> <span data-ttu-id="dda33-114">O total líquido é 75,00.</span><span class="sxs-lookup"><span data-stu-id="dda33-114">The net amount is 75.00.</span></span>  <span data-ttu-id="dda33-115">Esse é o valor que esperaremos na nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="dda33-115">That is the amount that we will expect on the invoice.</span></span>  
6. <span data-ttu-id="dda33-116">No painel de ação, selecione **Compra**.</span><span class="sxs-lookup"><span data-stu-id="dda33-116">On the action pane, select **Purchase**.</span></span>
7. <span data-ttu-id="dda33-117">Selecione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="dda33-117">Select **Confirm**.</span></span>

## <a name="create-and-post-and-invoice"></a><span data-ttu-id="dda33-118">Criar e lançar e faturar</span><span class="sxs-lookup"><span data-stu-id="dda33-118">Create and post and invoice</span></span>
1. <span data-ttu-id="dda33-119">No painel de navegação, vá para **Módulos > Contas a pagar > Faturas > Registro de faturas**.</span><span class="sxs-lookup"><span data-stu-id="dda33-119">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice register**.</span></span>
2. <span data-ttu-id="dda33-120">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="dda33-120">Select **New**.</span></span>
3. <span data-ttu-id="dda33-121">Abra a busca para selecionar o nome do registro de fatura que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="dda33-121">Open the lookup to select the name of the invoice register that you want to use.</span></span>
4. <span data-ttu-id="dda33-122">Selecione o nome do registro de fatura que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="dda33-122">Select the name of the invoice register that you want to use.</span></span>
5. <span data-ttu-id="dda33-123">Selecione **Linhas** para abrir o registro e inserir as linhas de despesa.</span><span class="sxs-lookup"><span data-stu-id="dda33-123">Select **Lines** to open the register and enter expense lines.</span></span>
6. <span data-ttu-id="dda33-124">Na busca, selecione um fornecedor.</span><span class="sxs-lookup"><span data-stu-id="dda33-124">In the lookup, select a vendor.</span></span> <span data-ttu-id="dda33-125">Por exemplo, selecione o fornecedor **1001**.</span><span class="sxs-lookup"><span data-stu-id="dda33-125">For example, select vendor **1001**.</span></span>
7. <span data-ttu-id="dda33-126">No campo **Fatura**, insira o número da fatura.</span><span class="sxs-lookup"><span data-stu-id="dda33-126">In the **Invoice** field, enter the invoice number.</span></span>
8. <span data-ttu-id="dda33-127">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="dda33-127">In the **Description** field, type a value.</span></span>
9. <span data-ttu-id="dda33-128">No campo **Crédito**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="dda33-128">In the **Credit** field, enter a number.</span></span>
10. <span data-ttu-id="dda33-129">No campo **Ordem de compra**, abra a lista suspensa para selecionar a ordem de compra criada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="dda33-129">In the **Purchase order** field, open the drop-down list to select the purchase order that you created earlier.</span></span>
11. <span data-ttu-id="dda33-130">No campo **Aprovado por**, realce um aprovador na lista suspensa e clique em **Selecionar** para selecionar esse aprovador.</span><span class="sxs-lookup"><span data-stu-id="dda33-130">In the **Approved by** field, highlight an approver in the drop-down list and click **Select** to select that approver.</span></span>
12. <span data-ttu-id="dda33-131">Selecione **Lançar**.</span><span class="sxs-lookup"><span data-stu-id="dda33-131">Select **Post**.</span></span>

## <a name="open-an-invoice-from-the-pool-and-match-it-to-a-purchase-order-to-complete-the-invoice-process"></a><span data-ttu-id="dda33-132">Abra uma fatura do grupo e corresponda-a a ordem de compra para concluir o processo de fatura</span><span class="sxs-lookup"><span data-stu-id="dda33-132">Open an invoice from the pool and match it to a purchase order to complete the invoice process</span></span>
1. <span data-ttu-id="dda33-133">No painel de navegação, vá para **Módulos > Contas a pagar > Faturas > Grupo de faturas**.</span><span class="sxs-lookup"><span data-stu-id="dda33-133">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice pool**.</span></span>
2. <span data-ttu-id="dda33-134">Selecione **Ordem de compra** para criar uma fatura de fornecedor usando a fatura do grupo.</span><span class="sxs-lookup"><span data-stu-id="dda33-134">Select **Purchase order** to create a vendor invoice from the invoice in the pool.</span></span>
3. <span data-ttu-id="dda33-135">Selecione a fatura que você deseja revisar.</span><span class="sxs-lookup"><span data-stu-id="dda33-135">Select the invoice that you want to review.</span></span>
4. <span data-ttu-id="dda33-136">Selecione **Atualizar status de conciliação** para concluir a conciliação.</span><span class="sxs-lookup"><span data-stu-id="dda33-136">Select **Update match status** to complete the matching.</span></span>
5. <span data-ttu-id="dda33-137">No painel de ações, selecione **Opções**.</span><span class="sxs-lookup"><span data-stu-id="dda33-137">On the action pane, select **Options**.</span></span>
6. <span data-ttu-id="dda33-138">Selecione **Alterar exibição**.</span><span class="sxs-lookup"><span data-stu-id="dda33-138">Select **Change view**.</span></span>
7. <span data-ttu-id="dda33-139">Selecione **Exibição de grade**.</span><span class="sxs-lookup"><span data-stu-id="dda33-139">Select **Grid view**.</span></span>
8. <span data-ttu-id="dda33-140">Selecione **Lançar**.</span><span class="sxs-lookup"><span data-stu-id="dda33-140">Select **Post**.</span></span>
9. <span data-ttu-id="dda33-141">Feche o formulário.</span><span class="sxs-lookup"><span data-stu-id="dda33-141">Close the form.</span></span>
10. <span data-ttu-id="dda33-142">No painel de navegação, vá para **Módulos > Contas a pagar > Fornecedores > Fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="dda33-142">In the navigation pane, go to **Modules > Accounts payable > Vendors > Vendors**.</span></span>
11. <span data-ttu-id="dda33-143">Selecione o fornecedor que estava na ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="dda33-143">Select the vendor that was on the purchase order.</span></span> <span data-ttu-id="dda33-144">Por exemplo, selecione o fornecedor **1001**.</span><span class="sxs-lookup"><span data-stu-id="dda33-144">For example, select vendor **1001**.</span></span>
12. <span data-ttu-id="dda33-145">No painel de ação, selecione **Fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="dda33-145">On the action pane, select **Vendor**.</span></span>
13. <span data-ttu-id="dda33-146">Selecione **Transações**.</span><span class="sxs-lookup"><span data-stu-id="dda33-146">Select **Transactions**.</span></span>
14. <span data-ttu-id="dda33-147">Selecione a nota fiscal que você criou.</span><span class="sxs-lookup"><span data-stu-id="dda33-147">Select the invoice that you created.</span></span> <span data-ttu-id="dda33-148">O acúmulo de registro de nota fiscal foi estornada e lançada na conta de despesas apropriada.</span><span class="sxs-lookup"><span data-stu-id="dda33-148">The invoice register accrual was reversed and posted to the appropriate expense account.</span></span>  

