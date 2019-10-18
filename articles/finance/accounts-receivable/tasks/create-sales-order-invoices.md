---
title: Criar faturas de ordem de venda
description: Este guia descreve a tarefa de uma ordem de venda, incluindo mescla de notas fiscais e processamento em lotes.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesEditLines,  SysQueryForm, SysRecurrence
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2a41524c773284812aa6eebddcd832c78bd29166
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176456"
---
# <a name="create-sales-order-invoices"></a><span data-ttu-id="f6e69-103">Criar faturas de ordem de venda</span><span class="sxs-lookup"><span data-stu-id="f6e69-103">Create sales order invoices</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f6e69-104">Este guia descreve a tarefa de uma ordem de venda, incluindo mescla de notas fiscais e processamento em lotes.</span><span class="sxs-lookup"><span data-stu-id="f6e69-104">This task guide describes invoicing a sales order, including merging invoices and batch processing.</span></span> <span data-ttu-id="f6e69-105">Este procedimento usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="f6e69-105">This procedure uses the USMF demo company.</span></span>


## <a name="create-an-invoice-from-a-sales-order"></a><span data-ttu-id="f6e69-106">Criar uma fatura de uma ordem de venda</span><span class="sxs-lookup"><span data-stu-id="f6e69-106">Create an invoice from a sales order</span></span>
1. <span data-ttu-id="f6e69-107">Vá para **Painel de navegação > Módulos > Contas a receber > Ordens > ordens de vendas enviadas, mas não faturadas**.</span><span class="sxs-lookup"><span data-stu-id="f6e69-107">Go to **Navigation pane > Modules > Accounts receivable > Orders > Shipped but not invoiced sales orders**.</span></span>
2. <span data-ttu-id="f6e69-108">Selecione uma ordem de venda na lista.</span><span class="sxs-lookup"><span data-stu-id="f6e69-108">Select a sales order in the list.</span></span> 
3. <span data-ttu-id="f6e69-109">No **Painel de Ação**, clique em **Fatura > Gerar > Fatura**.</span><span class="sxs-lookup"><span data-stu-id="f6e69-109">On the **Action Pane**, click **Invoice > Generate > Invoice**.</span></span> <span data-ttu-id="f6e69-110">Observe que a ordem de venda tem várias guias de remessa associadas a ela.</span><span class="sxs-lookup"><span data-stu-id="f6e69-110">Note that this sales order has multiple packing slips associated with it.</span></span> <span data-ttu-id="f6e69-111">Ela mostrará apenas a palavra <multiple>, em vez do número da guia de remessa.</span><span class="sxs-lookup"><span data-stu-id="f6e69-111">It will only show the word <multiple> instead of the packing slip number.</span></span>  
4. <span data-ttu-id="f6e69-112">Expanda a seção **Parâmetros**.</span><span class="sxs-lookup"><span data-stu-id="f6e69-112">Expand the **Parameters** section.</span></span>
    - <span data-ttu-id="f6e69-113">O lançamento deve ser definido como Sim para lançar a fatura.</span><span class="sxs-lookup"><span data-stu-id="f6e69-113">Posting must be set to Yes to post the invoice.</span></span> <span data-ttu-id="f6e69-114">Também é possível desativar o lançamento e imprimir apenas a nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="f6e69-114">You can also turn off posting and just print the invoice.</span></span> <span data-ttu-id="f6e69-115">No entanto, você pode realizar o mesmo resultado criando uma nota fiscal do formulário em vez de uma nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="f6e69-115">However, you can accomplish the same result by creating a proforma invoice instead of an invoice.</span></span>  
    - <span data-ttu-id="f6e69-116">Essa opção é usada para trabalhos em lotes.</span><span class="sxs-lookup"><span data-stu-id="f6e69-116">This option is used for batch jobs.</span></span> <span data-ttu-id="f6e69-117">A consulta será executada quando o trabalho em lotes for executado.</span><span class="sxs-lookup"><span data-stu-id="f6e69-117">The query is run when the batch job is run.</span></span>
5. <span data-ttu-id="f6e69-118">No campo **Imprimir**, selecione 'Depois'.</span><span class="sxs-lookup"><span data-stu-id="f6e69-118">In the **Print** field, select 'After'.</span></span>
6. <span data-ttu-id="f6e69-119">Selecione **Sim** para **Imprimir fatura**.</span><span class="sxs-lookup"><span data-stu-id="f6e69-119">Select **Yes** for **Print invoice**.</span></span> <span data-ttu-id="f6e69-120">O gerenciamento de impressão pode imprimir várias cópias de notas fiscais e também enviar a nota fiscal por email como um arquivo PDF.</span><span class="sxs-lookup"><span data-stu-id="f6e69-120">Print management can print  multiple copies of the invoice and also send the invoice via email as a PDF file.</span></span>  
7. <span data-ttu-id="f6e69-121">No campo **Imprimir encargos**, selecione 'Resumir'.</span><span class="sxs-lookup"><span data-stu-id="f6e69-121">In the **Print charges** field, select 'Summarize'.</span></span>
8. <span data-ttu-id="f6e69-122">No campo **Verificar limite de crédito**, selecione 'Saldo'.</span><span class="sxs-lookup"><span data-stu-id="f6e69-122">In the **Check credit limit** field, select 'Balance'.</span></span>
9. <span data-ttu-id="f6e69-123">Clique em **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="f6e69-123">Click **Cancel**.</span></span>

## <a name="combine-orders-into-a-single-invoice"></a><span data-ttu-id="f6e69-124">Combinar ordens em uma única nota fiscal</span><span class="sxs-lookup"><span data-stu-id="f6e69-124">Combine orders into a single invoice</span></span>
1. <span data-ttu-id="f6e69-125">Vá para **Painel de navegação > Módulos > Contas a receber > Ordens > Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="f6e69-125">Go to **Navigation pane > Modules > Accounts receivable > Orders > All sales orders**.</span></span>
2. <span data-ttu-id="f6e69-126">Localize um cliente que tem várias notas fiscais abertas.</span><span class="sxs-lookup"><span data-stu-id="f6e69-126">Locate a customer that has multiple invoices open.</span></span>
3. <span data-ttu-id="f6e69-127">Selecione várias ordens de venda abertas do mesmo cliente.</span><span class="sxs-lookup"><span data-stu-id="f6e69-127">Select multiple open sales orders from the same customer.</span></span>
4. <span data-ttu-id="f6e69-128">No **Painel de Ação**, clique em **Fatura > Gerar > Fatura**.</span><span class="sxs-lookup"><span data-stu-id="f6e69-128">On the **Action Pane**, click **Invoice > Generate > Invoice**.</span></span>
5. <span data-ttu-id="f6e69-129">Expanda a seção **Parâmetros**.</span><span class="sxs-lookup"><span data-stu-id="f6e69-129">Expand the **Parameters** section.</span></span>
6. <span data-ttu-id="f6e69-130">No campo **Quantidade**, selecione "Todas".</span><span class="sxs-lookup"><span data-stu-id="f6e69-130">In the **Quantity** field, select 'All'.</span></span> <span data-ttu-id="f6e69-131">Observe que há duas notas fiscais listadas na seção da visão geral.</span><span class="sxs-lookup"><span data-stu-id="f6e69-131">Note that there are two invoices listed in the overview section.</span></span> <span data-ttu-id="f6e69-132">Deixe-nos agora mescla-los em uma única nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="f6e69-132">Now let's merge them into a single invoice.</span></span>  
7. <span data-ttu-id="f6e69-133">No campo **Atualização resumida de**, selecione 'Conta de fatura'.</span><span class="sxs-lookup"><span data-stu-id="f6e69-133">In the **Summary update for** field, select 'Invoice account'.</span></span>
8. <span data-ttu-id="f6e69-134">Clique em **Organizar** para mesclar as ordens de venda em uma única fatura.</span><span class="sxs-lookup"><span data-stu-id="f6e69-134">Click **Arrange** to merge the sales orders into a single invoice.</span></span> <span data-ttu-id="f6e69-135">As dois ordens de venda são mescladas agora em uma única nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="f6e69-135">The two sales orders are now merged into a single invoice.</span></span>   
9. <span data-ttu-id="f6e69-136">Clique em **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="f6e69-136">Click **Cancel**.</span></span>
10. <span data-ttu-id="f6e69-137">Clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="f6e69-137">Click **Yes**.</span></span>

## <a name="post-invoices-in-a-batch"></a><span data-ttu-id="f6e69-138">Lançar notas fiscais em um lote</span><span class="sxs-lookup"><span data-stu-id="f6e69-138">Post invoices in a batch</span></span>
1. <span data-ttu-id="f6e69-139">Vá para **Painel de Navegação > Módulos > Contas a receber > Faturas > Faturamento em lote > Fatura**.</span><span class="sxs-lookup"><span data-stu-id="f6e69-139">Go to **Navigation pane > Modules > Accounts receivable > Invoices > Batch invoicing > Invoice**.</span></span>
2. <span data-ttu-id="f6e69-140">Clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="f6e69-140">Click **Select**.</span></span>
3. <span data-ttu-id="f6e69-141">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6e69-141">Click **OK**.</span></span>
4. <span data-ttu-id="f6e69-142">Clique em **Lote**.</span><span class="sxs-lookup"><span data-stu-id="f6e69-142">Click **Batch**.</span></span>
5. <span data-ttu-id="f6e69-143">Selecione **Sim** em **Processamento em lotes**.</span><span class="sxs-lookup"><span data-stu-id="f6e69-143">Select **Yes** in **Batch processing**.</span></span>
6. <span data-ttu-id="f6e69-144">Clique em **Recorrência**.</span><span class="sxs-lookup"><span data-stu-id="f6e69-144">Click **Recurrence**.</span></span>
7. <span data-ttu-id="f6e69-145">Selecione **Dias**.</span><span class="sxs-lookup"><span data-stu-id="f6e69-145">Select **Days**.</span></span>
8. <span data-ttu-id="f6e69-146">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6e69-146">Click **OK**.</span></span>
9. <span data-ttu-id="f6e69-147">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6e69-147">Click **OK**.</span></span>
10. <span data-ttu-id="f6e69-148">Clique em **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="f6e69-148">Click **Cancel**.</span></span>
11. <span data-ttu-id="f6e69-149">Clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="f6e69-149">Click **Yes**.</span></span>

