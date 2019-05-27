---
title: Criar um modelo de fatura de texto livre
description: Este procedimento demonstra como criar um modelo de fatura de texto livre.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/29/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 91f2ec2f8ab21616c6a1b886ee89d6faf84023e4
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1559494"
---
# <a name="create-a-free-text-invoice-template"></a><span data-ttu-id="c67c2-103">Criar um modelo de fatura de texto livre</span><span class="sxs-lookup"><span data-stu-id="c67c2-103">Create a free text invoice template</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c67c2-104">Para este passo a passo, use a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="c67c2-104">For this walkthrough, use the USMF demo company.</span></span> <span data-ttu-id="c67c2-105">Este procedimento é direcionado para o usuário responsável por gerenciar e processar faturas A/R.</span><span class="sxs-lookup"><span data-stu-id="c67c2-105">This procedure is intended for the user who is responsible for managing and processing A/R invoices.</span></span>

## <a name="create-a-template"></a><span data-ttu-id="c67c2-106">Criar um modelo</span><span class="sxs-lookup"><span data-stu-id="c67c2-106">Create a template</span></span>

1. <span data-ttu-id="c67c2-107">Vá para Contas a receber > Faturas > Faturas recorrentes > Modelos de fatura de texto livre.</span><span class="sxs-lookup"><span data-stu-id="c67c2-107">Go to Accounts receivable > Invoices > Recurring invoices > Free text invoice templates.</span></span>
    * <span data-ttu-id="c67c2-108">Use este formulário para criar modelos de fatura de texto livre que podem incluir linhas da fatura, encargos, um modelo de distribuição contábil e informações da conta contábil.</span><span class="sxs-lookup"><span data-stu-id="c67c2-108">Use this form to create free text invoice templates that can include invoice lines, charges, an accounting distribution template, and ledger account information.</span></span>  
2. <span data-ttu-id="c67c2-109">Clique em 'Novo' para criar um novo modelo de fatura de texto livre.</span><span class="sxs-lookup"><span data-stu-id="c67c2-109">Click 'New' to create a new free text invoice template.</span></span>
3. <span data-ttu-id="c67c2-110">No campo Nome de modelo, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c67c2-110">In the Template name field, type a value.</span></span>
    * <span data-ttu-id="c67c2-111">Especialmente 'Nome do modelo' identifica um modelo de fatura de texto livre.</span><span class="sxs-lookup"><span data-stu-id="c67c2-111">‘Template name’ uniquely identifies a free text invoice template.</span></span> <span data-ttu-id="c67c2-112">Nenhum do dois modelos pode ter o mesmo 'Nome do modelo'.</span><span class="sxs-lookup"><span data-stu-id="c67c2-112">No two templates can have the same ‘Template name’.</span></span>  
4. <span data-ttu-id="c67c2-113">No campo Descrição, insira uma descrição do modelo.</span><span class="sxs-lookup"><span data-stu-id="c67c2-113">In the Description field, enter a description of the template.</span></span>
5. <span data-ttu-id="c67c2-114">Expanda a guia nas linhas da nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="c67c2-114">Expand the Invoice lines tab.</span></span>
6. <span data-ttu-id="c67c2-115">No campo Descrição, insira uma descrição da linha de fatura.</span><span class="sxs-lookup"><span data-stu-id="c67c2-115">In the Description field, enter a description of the invoice line.</span></span>
7. <span data-ttu-id="c67c2-116">No campo Conta principal, selecione uma conta de receita.</span><span class="sxs-lookup"><span data-stu-id="c67c2-116">In the Main account field, select a revenue account.</span></span>
    * <span data-ttu-id="c67c2-117">Você pode selecionar a conta da transação de contrapartida de um crédito de cliente para o valor total da fatura na página Perfis de lançamento de cliente.</span><span class="sxs-lookup"><span data-stu-id="c67c2-117">You can select the offset transaction account of a customer credit for the total invoice amount in the Customer posting profiles page.</span></span>  
8. <span data-ttu-id="c67c2-118">No campo Grupo de imposto, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c67c2-118">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="c67c2-119">O grupo de impostos para a linha da fatura atual, que é o grupo de impostos padrão para a conta do cliente.</span><span class="sxs-lookup"><span data-stu-id="c67c2-119">The sales tax group for the current invoice line is the default sales tax group for the customer account.</span></span>  
9. <span data-ttu-id="c67c2-120">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c67c2-120">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="c67c2-121">No campo Grupo de taxa de item, selecione o grupo de impostos de item para a linha de fatura atual.</span><span class="sxs-lookup"><span data-stu-id="c67c2-121">In the Item tax group field, select the item sales tax group for the current invoice line.</span></span>
11. <span data-ttu-id="c67c2-122">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c67c2-122">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="c67c2-123">No campo Preço de unidade, insira ou exiba o preço por unidade para a linha de fatura</span><span class="sxs-lookup"><span data-stu-id="c67c2-123">In the Unit price field, enter or view the price per unit for the invoice line</span></span>
    * <span data-ttu-id="c67c2-124">Esse valor é multiplicado pelo campo Quantidade para determinar o valor da linha da fatura.</span><span class="sxs-lookup"><span data-stu-id="c67c2-124">This amount is multiplied by the Quantity field to determine the invoice line amount.</span></span>  
13. <span data-ttu-id="c67c2-125">Adicione uma nova linha ao modelo de fatura de texto livre.</span><span class="sxs-lookup"><span data-stu-id="c67c2-125">Add a new line to free text invoice template.</span></span>
14. <span data-ttu-id="c67c2-126">No campo Descrição, insira uma descrição da linha de fatura.</span><span class="sxs-lookup"><span data-stu-id="c67c2-126">In the Description field, enter a description of the invoice line.</span></span>
15. <span data-ttu-id="c67c2-127">No campo Conta principal, selecione uma conta de receita.</span><span class="sxs-lookup"><span data-stu-id="c67c2-127">In the Main account field, select a revenue account.</span></span>
    * <span data-ttu-id="c67c2-128">Você pode selecionar a conta da transação de contrapartida de um crédito de cliente para o valor total da fatura na página Perfis de lançamento de cliente.</span><span class="sxs-lookup"><span data-stu-id="c67c2-128">You can select the offset transaction account of a customer credit for the total invoice amount in the Customer posting profiles page.</span></span>  
16. <span data-ttu-id="c67c2-129">No campo Grupo de imposto, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c67c2-129">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="c67c2-130">O grupo de impostos para a linha da fatura atual, que é o grupo de impostos padrão para a conta do cliente.</span><span class="sxs-lookup"><span data-stu-id="c67c2-130">The sales tax group for the current invoice line is the default sales tax group for the customer account.</span></span>  
17. <span data-ttu-id="c67c2-131">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c67c2-131">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="c67c2-132">No campo Grupo de imposto do item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c67c2-132">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="c67c2-133">O grupo de impostos do item para a linha de fatura atual.</span><span class="sxs-lookup"><span data-stu-id="c67c2-133">The item sales tax group for the current invoice line.</span></span>  
19. <span data-ttu-id="c67c2-134">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c67c2-134">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="c67c2-135">Insira ou exiba o número de unidades da linha da fatura</span><span class="sxs-lookup"><span data-stu-id="c67c2-135">Enter or view the number of units for the invoice line</span></span>
    * <span data-ttu-id="c67c2-136">Esse número é multiplicado pelo valor no campo Preço unitário para determinar o valor da linha da fatura.</span><span class="sxs-lookup"><span data-stu-id="c67c2-136">This number is multiplied by the value in the Unit price field to determine the invoice line amount.</span></span>  
21. <span data-ttu-id="c67c2-137">Insira ou exiba o preço unitário para a linha de fatura.</span><span class="sxs-lookup"><span data-stu-id="c67c2-137">Enter or view the price per unit for the invoice line.</span></span> 
    * <span data-ttu-id="c67c2-138">Esse valor é multiplicado pelo valor no campo Quantidade para determinar o valor da linha da fatura.</span><span class="sxs-lookup"><span data-stu-id="c67c2-138">This amount is multiplied by the value in the Quantity field to determine the invoice line amount.</span></span>  
22. <span data-ttu-id="c67c2-139">Exiba e modifique as distribuições contábeis para uma linha individual e todas as linhas descendentes.</span><span class="sxs-lookup"><span data-stu-id="c67c2-139">View and modify the accounting distributions for an individual line and any child lines.</span></span>
    * <span data-ttu-id="c67c2-140">As distribuições contábeis definem como um valor será contabilizado, assim como a receita, os impostos ou os encargos serão contabilizados em uma fatura de texto livre.</span><span class="sxs-lookup"><span data-stu-id="c67c2-140">Accounting distributions define how an amount will be accounted for, such as how the revenue, tax, or charges will be accounted for on a free text invoice.</span></span>  
23. <span data-ttu-id="c67c2-141">Atualizar as distribuições contábeis para a linha de fatura selecionada.</span><span class="sxs-lookup"><span data-stu-id="c67c2-141">Update the accounting distributions for the selected invoice line.</span></span>
24. <span data-ttu-id="c67c2-142">Clique em Fechar.</span><span class="sxs-lookup"><span data-stu-id="c67c2-142">Click Close.</span></span>

## <a name="save-a-free-text-invoice-as-a-template"></a><span data-ttu-id="c67c2-143">Salvar uma fatura de texto livre como modelo</span><span class="sxs-lookup"><span data-stu-id="c67c2-143">Save a free text invoice as a template</span></span>
<span data-ttu-id="c67c2-144">Você também pode salvar uma fatura de texto livre existente como um modelo.</span><span class="sxs-lookup"><span data-stu-id="c67c2-144">You can also save an existing free text invoice as a template.</span></span> <span data-ttu-id="c67c2-145">Quando selecionar Salvar no modelo na guia Fatura, forneça um nome e uma descrição para o modelo.</span><span class="sxs-lookup"><span data-stu-id="c67c2-145">When you select Save to template from the Invoice tab, provide a name and a description for the template.</span></span> <span data-ttu-id="c67c2-146">Se um modelo com o nome já existir, uma notificação de que um modelo com esse nome já existe será exibida.</span><span class="sxs-lookup"><span data-stu-id="c67c2-146">If a template with the name already exists, you will see a notification that a template with that name already exists.</span></span> <span data-ttu-id="c67c2-147">Você ainda poderá clicar em OK para substituí-lo.</span><span class="sxs-lookup"><span data-stu-id="c67c2-147">You can still click on Ok to replace it.</span></span> 
